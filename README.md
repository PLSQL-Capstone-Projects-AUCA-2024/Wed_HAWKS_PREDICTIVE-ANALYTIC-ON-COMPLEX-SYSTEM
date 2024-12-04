![image](https://github.com/user-attachments/assets/5923131f-057e-4d21-b1ae-ddc8ff475e7c)

                                      
## WED_HAWKS_PREDICTIVE ANALYTIC ON COMPLEX SYSTEM

The **PREDICTIVE ANALYTIC IN COMPLEX ENVIRONMENT (Disaster Management) Database System** can be used to speed up the response, preparedness, and mitigation against natural disasters. Centralizing disaster and weather data in real time, this system applies predictive models in order to enrich decision-making and support rescue teams and government agencies in disaster management more effectively.

## Table of Contents

1. [PHASE 2: Business Process Modeling](#phase-2-business-process-modelling)
2. [PHASE 3: Logical Data Model Design](#phase-3-logical-data-model-design)
3. [PHASE 4: Creating and Naming the Database](#phase-4-creating-and-naming-the-database)
3. [PHASE 5: Table Implementation and Data Insertion](#phase-5-table-implementation-and-data-insertion)
3. [PHASE 6: Interaction with the Database and Transactions](#phase-6-interaction-with-the-database-and-transactions)

---
## PHASE 2: Business Process Modelling

### Project Scope
The system shall:
- **Process Real-Time Data:** Allow for efficient alerts and mitigation of disasters.
Enhance preparedness by availing workable insights to emergency teams and government bodies.
Allow for international collaboration by sharing data across borders for harmonized disaster management approaches.
### Expected Outputs
 
a. More accurate disaster predictions
b. Better coordination of response and  disaster management.
c. Evidence-based decision-making in disaster situations.
 
---
### Identifying Key Stakeholders
#### Key Stakeholder and Their Responsibilities 
1. **Users**
- Roles: Disaster planners, data evaluators, and on-site responders utilize the system for disaster-related data processing.  
- Engagement: Handle information on disaster risks, occurrences, and predictions.  

2. **Departments**  
- Responsibilities: Government institutions, relief agencies, and meteorological stations provide and access data.  
- Engagement: Facilitate situation analysis and real-time response strategy development.

3. **Information Systems** 
- Responsibilities: Integrate predictive models and databases to analyze and forecast disasters. 
- Engagement: Process data from various sources to issue warnings and recommendations.

4. **External Data Sources** 
- Responsibilities: Supply satellite imagery, weather alerts, and other relevant data.
- Engagement: Aggregate and supply external data for system use.

---

**Process Modeling Using Swimlane Diagram**
The swimlane diagram details the main processes involved:
- **Swimlane 1:** Identification of disaster events by users, request for data, and appraisal of model output. 
- **Swimlane 2:** Data supply is ensured by different departments; they ensure data integrity and response planning.
- **Swimlane 3:** Information Systems collects, stores, and processes data to generate predictions.
- **Swimlane 4:** External Data Sources providing satellite images and weather forecasts in raw forms.

---
### BPMN Process Mapping
The following BPMN diagram visualizes disaster management processes: 
- **Start Event:** Users start disaster reporting.  
- **Data Collection:** Disaster-related data will be obtained from external sources.  
- **Data Storage and Processing:** The systems store and analyze the data for forecasts.  
- **Data Quality Control:** Check the accuracy of data and conformance to policy.  
- **Response Predictions:** Predictions in response to active activities by departments and users.
- **Preparedness Strategies:** Departments disseminate warnings and execute strategies.  
- **End Event:** Data updates enhance future predictions.

![Screenshot (18)](https://github.com/user-attachments/assets/c9e618e8-1875-44a7-b3d9-f149f6878838)

Link for references:(https://demo.bpmn.io/new)

---

## PHASE 3: Logical Data Model Design

### Entity Descriptions
1. **Disaster**: Tracks disaster details (e.g., type, magnitude, location).  
2. **Location**: Stores geographical data (e.g., country, state, city).  
3. **Prediction**: Logs disaster predictions (e.g., type, risk level).  
4. **Weather Condition**: Records weather-related data (e.g., temperature, rainfall).
5. **Preparedness Measure**: Explains strategies against disasters.  
6. **Historical Disaster Data**: Maintains past disaster history records.

### Entity-Relationship Diagram (ERD)
The ER diagram will map the following types of relationships: 
- One-to-many relationships between disasters and locations.  
- Many-to-one relationships between predictions and locations.  
- Many-to-many relationships between historical data, disasters, and locations.

![17322208214512830804362206652270](https://github.com/user-attachments/assets/5d605017-ab79-4484-84c2-cff2a665a27b)

---
## PHASE 4: Creating and Naming the Database

- **Username:** `wed_hawks`  
- **Password:** `hawks`  

### Physical Database Structure
1. **Tables Created**: Location, Disaster, Prediction, Weather_Condition, Preparedness_Measure, Historical_Disaster_Data. 
2. **Relationships**: Tables are related with foreign keys to maintain referential integrity. 
3. **Constraints**: Primary keys, foreign keys, and unique keys are imposed. 

---
## PHASE 5: Table Implementation and Data Insertion

### Table Creation
SQL commands to create tables look like this:
```sql
CREATE TABLE Location (
   Location_ID INT PRIMARY KEY,
   Country VARCHAR(50),
   State VARCHAR(50),
   City VARCHAR(50)
);
```

**Inserting Data**
Sample data:
```sql
INSERT INTO Location (Location_ID, Country, State, City) 
VALUES (1, 'Rwanda', 'Northern Province', 'Musanze');
INSERT INTO Disaster (Disaster_ID, Disaster_Type, Disaster_Date, Magnitude, Location_ID)
VALUES (1, 'Earthquake', TO_DATE('2024-11-15', 'YYYY-MM-DD'), 7.8, 1);
```

---
## PHASE 6: Interaction with the Database and Transactions
### Operations on the Database
Examples of some join operations:
- **Cross Join**:
 ```sql
 SELECT Disaster.Disaster_Type, Location.Country FROM Disaster CROSS JOIN Location;
 ```
- **Inner Join**:
 ```sql
 SELECT Disaster.Disaster_Type, Location.City FROM Disaster
INNER JOIN Location ON Disaster.Location_ID = Location.Location_ID;
  ```
- **Outer Join**:
  ```sql
  SELECT Prediction.Predicted_Date, Location.Country FROM Prediction 
  LEFT OUTER JOIN Location ON Prediction.Predicted_Location_ID = Location.Location_ID;
  ```

### Transaction Management
- **Insert with Commit**:
  ```sql
  BEGIN;
  INSERT INTO Disaster (Disaster_ID, Disaster_Type) VALUES (2, 'Flood');
  INSERT INTO Preparedness_Measure (Measure_ID, Disaster_ID) VALUES (1, 2);
  COMMIT;
  ```
- **Rollback on Error**:
  ```sql
   BEGIN;
  INSERT INTO Prediction (Prediction_ID, Disaster_Type) VALUES (3, 'Hurricane');
  ROLLBACK;


<!-- Contribution: Reviewed and added comments for better readability -->


