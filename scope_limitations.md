# Scope and Limitations
This document outlines the scope and limitations of the key features implemented in the Predictive Analytics in Complex Environment database system. These features include triggers, cursors, functions, packages, and auditing mechanisms.

## 1. Triggers
### Scope:
- **Purpose:** Automate workflows and enforce business rules (e.g., data validation, logging changes).
- **Types:** BEFORE, AFTER, and INSTEAD OF triggers.
- **Use Cases:**
  - Automatically update disaster status when a new incident is reported.
  - Log changes to sensitive data in audit tables.
### Limitations:
- **Performance Impact:** Triggers can introduce latency, especially with complex operations on large datasets.
- **Debugging Difficulty:** Errors within triggers are harder to trace compared to procedural code.
- **Cascading Risks:** Multiple triggers on a table may cause cascading effects or infinite loops if not carefully managed.
## 2. Cursors
### Scope:
- **Purpose:** Facilitate row-by-row processing for complex queries.
- **Types:** Explicit and implicit cursors.
- **Use Cases:**
  - Processing large result sets in disaster management reporting.
  - Handling sequential data operations that require conditional checks.
### Limitations:
- **Resource Consumption:** Cursors consume more memory and processing power, which can degrade performance on large datasets.
- **Complexity:** Increases code complexity and potential for logical errors.
- **Alternative:** Whenever possible, set-based SQL operations should be preferred over cursors for efficiency.
## 3. Functions
### Scope:
- **Purpose:** Encapsulate reusable logic for modular and efficient code.
- **Types:** Scalar functions, table functions.
- **Use Cases:**
  - Calculate disaster risk levels based on multiple factors.
  - Format output data for reporting dashboards.
### Limitations:
- **Restrictions:** Cannot perform DML operations (INSERT, UPDATE, DELETE) inside functions.
- **Nesting Limits:** Deeply nested functions can be challenging to debug and maintain.
- **Performance:** Overuse of functions in queries can impact execution time.
## 4. Packages
### Scope:
- **Purpose:** Group related functions, procedures, and variables into a single logical unit.
- **Benefits:** Improved code organization, security, and reusability.
- **Use Cases:**
  - Package disaster prediction algorithms.
  - Group database utilities for data validation.
### Limitations:
- **Maintenance Overhead:** Packages can become large and difficult to manage if not properly modularized.
- **Loading Time:** The first call to a package may incur a performance hit as it loads into memory.
- **Versioning Issues:** Changes to package specifications require recompilation of dependent objects.
## 5. Auditing Mechanisms
### Scope:
- **Purpose:** Track changes to sensitive data, monitor user activity, and ensure compliance.
- **Techniques:**
  - Table-based auditing with triggers.
  - System-level auditing using database logs.
- **Use Cases:**
  - Log user activities during disaster response operations.
  - Track modifications to critical tables (e.g., disaster reports).
### Limitations:
- **Performance Impact:** Excessive logging can degrade system performance and increase storage needs.
- **Data Overload:** Too much audit data can be overwhelming and difficult to analyze without proper filtering.
- **Privacy Concerns:** Ensure compliance with privacy regulations when logging user data.



Sure! Let me develop the activities for your **Disaster Management System** step by step. I will be preparing the creation of **audits**, **triggers**, **cursors**, **functions**, and **packages**, along with the **problem statement justification** in script format and explanation.

### Step 1: **Problem Statement Justification**
Here is the summary of a problem statement:
The Disaster Management System should be designed to provide mechanisms for maintaining data integrity, workflow automation, and auditing sensitive records related to disasters. In doing so, this system enhances functionality, reliability, and security through utilizing a range of PL/SQL programming features like triggers, cursors, functions, packages, and auditing for more sophisticated real-world disaster management scenarios."

---
### Step 2: **Implementation of Triggers**

#### a) After Trigger (AFTER INSERT)
**Purpose:** To record all the new disaster events in the database.

```sql
CREATE OR REPLACE TRIGGER trg_log_disaster_insert
AFTER INSERT ON disaster_events
FOR EACH ROW
BEGIN
    INSERT INTO disaster_audit (
        action_time,
        action_type,
        disaster_id,
        user_id
    ) VALUES (
        SYSDATE,
'INSERT',
        :NEW.disaster_id,
        USER
    );
END;
/
```

---

#### b) Compound Trigger (For Complex Scenarios)
**Purpose:** Track changes to disaster records and prevent updates that exceed a severity threshold.

```sql
CREATE OR REPLACE TRIGGER trg_disaster_severity
FOR UPDATE ON disaster_events
COMPOUND TRIGGER
    -- Variables to track
TYPE t_disaster_log IS TABLE OF disaster_audit%ROWTYPE;
    v_log t_disaster_log := t_disaster_log();

    BEFORE EACH ROW IS
    BEGIN
        IF :NEW.severity_level > 10 THEN
            RAISE_APPLICATION_ERROR(-20001, 'Severity level cannot exceed 10.');
END BEFORE EACH ROW;

    AFTER EACH ROW IS
    BEGIN
        v_log.EXTEND;
        v_log(v_log.LAST) := disaster_audit(
            action_time => SYSDATE,
            action_type => 'UPDATE',
disaster_id => :NEW.disaster_id,
            user_id     => USER
        );
    END AFTER EACH ROW;

    AFTER STATEMENT IS
    BEGIN
FOR i IN 1. v_log.COUNT LOOP
            INSERT INTO disaster_audit VALUES v_log(i);
        END LOOP;
    END AFTER STATEMENT;
END;
/
```

---

### Step 3: **Cursor Implementation**

**Scenario:** Process disaster data row by row to calculate and update the total number of casualties for each region.

```sql
DECLARE
CURSOR disaster_cursor IS
        SELECT region_id, SUM(casualties) AS total_casualties
        FROM disaster_events
        GROUP BY region_id;

    v_region_id disaster_events.region_id%TYPE;
    v_total_casualties NUMBER;
BEGIN
    OPEN disaster_cursor;
    LOOP
        FETCH disaster_cursor INTO v_region_id, v_total_casualties;
EXIT WHEN disaster_cursor%NOTFOUND;

        UPDATE disaster_regions
        SET total_casualties = v_total_casualties
        WHERE region_id = v_region_id;
    END LOOP;
    CLOSE disaster_cursor;
END;
/
```

---

### Step 4: **Attributes and Functions**

#### a) Function to Calculate Severity Index
**Purpose:** Modularize disaster severity calculation logic.

```sql
CREATE OR REPLACE FUNCTION calculate_severity (
    casualties NUMBER,
    affected_area NUMBER
) RETURN NUMBER IS
BEGIN
    RETURN (casualties * 0.7) + (affected_area * 0.3);
END;
/
```

#### b) Usage of `%TYPE` and `%ROWTYPE`
```sql
DECLARE
    v_event disaster_events%ROWTYPE;
    v_severity NUMBER;
BEGIN
    SELECT * INTO v_event FROM disaster_events WHERE disaster_id = 101;
    v_severity := calculate_severity(v_event.casualties, v_event.affected_area);
DBMS_OUTPUT.PUT_LINE('Calculated Severity: ' || v_severity);
END;
/
```

---

### Step 5: **Package Development**

**Purpose:** Group related procedures for better organization.

```sql
CREATE OR REPLACE PACKAGE disaster_pkg IS
    PROCEDURE log_action(p_action_type VARCHAR2, p_disaster_id NUMBER);
    FUNCTION get_disaster_summary RETURN VARCHAR2;
END disaster_pkg;
/

CREATE OR REPLACE PACKAGE BODY disaster_pkg IS
    PROCEDURE log_action(p_action_type VARCHAR2, p_disaster_id NUMBER) IS
    BEGIN
INSERT INTO disaster_audit (
            action_time, action_type, disaster_id, user_id
        ) VALUES (
            SYSDATE, p_action_type, p_disaster_id, USER
        );

FUNCTION get_disaster_summary RETURN VARCHAR2 IS
        v_summary VARCHAR2(4000);
    BEGIN
        SELECT LISTAGG('Region ' || region_id || ': ' || total_casualties, ', ')
        INTO v_summary
        FROM disaster_regions;
        RETURN v_summary;
END get_disaster_summary;
END disaster_pkg;
/
```

---

### Step 6: **Auditing with Restrictions and Tracking**

#### a) Auditing Log Table
```sql
CREATE TABLE disaster_audit (
    audit_id NUMBER GENERATED BY DEFAULT AS IDENTITY PRIMARY KEY,
    action_time DATE,
    action_type VARCHAR2(50),
    disaster_id NUMBER,
    user_id VARCHAR2(30)
);
```

#### b) Restriction via Roles
**Purpose:** Only allow specific users to update disaster data.

```sql
CREATE OR REPLACE TRIGGER trg_restrict_disaster_update
BEFORE UPDATE ON disaster_events
FOR EACH ROW
BEGIN
    IF NOT USER IN ('AdminUser', 'DisasterManager') THEN
        RAISE_APPLICATION_ERROR(-20002, 'You do not have permission to update disaster data.');
    END IF;
END;
/
```

---

### Step 7: **Scope and Limitations**

#### Scope:
- Enforcing data integrity through triggers.
- Modularizing logic with functions and packages.
- Enhancing security with auditing and restrictions.
- Processing data efficiently with cursors.

#### Limitations:
- Auditing can increase storage requirements.
- Complex triggers may add overhead to large datasets.
- Cursor-based row-by-row processing may be slower for large datasets compared to bulk operations.



## Conclusion:
Understanding the scope and limitations of these features is crucial for optimizing system performance, maintaining data integrity, and ensuring efficient disaster management operations. Proper planning and best practices should guide their implementation to mitigate the identified constraints.
