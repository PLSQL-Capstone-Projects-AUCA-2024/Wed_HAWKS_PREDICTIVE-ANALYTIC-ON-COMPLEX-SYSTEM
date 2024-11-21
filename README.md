![image](https://github.com/user-attachments/assets/5923131f-057e-4d21-b1ae-ddc8ff475e7c)
                                               
  **# Wed_Hawks_DisasterPredictionManagementSystem**
                                               
  **The Disaster Management Database enables rapid response, preparedness, and mitigation for natural disasters**
                        **It centralizes real-time and historical data on disasters and weather, using predictive models to aid decision-making**.


**PHASE TWO: Business Process Modeling**


**Project Scope**

Vision for System encompasses major items including, 
-    **Real-Time Data Processing:** Facilitate timely alerts and mitigation of disasters.
-    **Enhanced Preparedness and Response:** It can therefore offer useful information to the emergency teams and even government bodies.
-    **International Collaboration:** Encourage harmonized sharing of data between the countries so as to come up with a common approach in dealing with disasters.

**Expected Outcomes**
- More accuracy in disaster predictions and related impacts.
- Better capability for management and coordination of the responses to disasters.
- Benefit from the evidence used within the course of disaster management.

**IDENTIFY KEY ENTITIES**

**Key Stakeholders and Their Responsibilities**
1. **Users**
Responsibilities: Emergency management specialists, data evaluators, and on-site responders make use of the database for entering, processing and retrieval of the information related to disasters.
Engagement: Entail and extract information pertaining to disaster occurrences, potential risks as well as projections.
2. **Departments**
Responsibilities: Provide and collect data as well as information through utilization of the system in government institutions, relief agencies and meteorological stations.
Engagement: Includes the provision of on-line data, access to situation analysis, and response strategy development in real time.
3. **Information Systems**
Responsibilities : These include the data base management system (DBMS), predictive models, and health facilities data all integrated to collect and analyze information from different sources.
Engagement: There are predictive models which help to determine the risks and help in alerting the users on the possible occurrence of a disaster.
4. **External Data Sources**
Responsibilities: Feeding in external data such as satellite imageries, disaster watch alerts, etc.
Engagement: To help the information system acquire data so that it can effectively forecast disasters.

 **Process Modeling Using Swimlane Diagram**

Swim Lanes Components.
-  **Swimlane 1:** The users called the emergency planners who carry out the functions of disaster event identification, data analyses requests, assessment of prediction outputs, and the response calls.
-  **Swimlane 2** - Departments: Governmental institutions and the humanitarian sector deliver data, maintain its integrity and allow for the ability to pre-work on the impact of the disaster in advance.
-  **Swimlane 3** Information Systems: Major activities include data gathering, storage, and processing to develop predictive output.
-  **Swimlane 4**-External Data Sources: Gather information from various sources such as satellite imagery, weather channels, and other different networks in various parts of the world and forward the information by aggregation.

![Screenshot 2024-11-13 130214](https://github.com/user-attachments/assets/e81fb6eb-dd19-4bf8-98b0-b4c981055ce8)


**BPMN Process Mapping**

Following BPMN elements have been used to show the essential activities in disaster management:

-  **Start Event:** User triggers an accident of a disaster in providing preliminary or actual data.
-  **Data Collection** – The external actors like satellites collect and provide information.
-  **Data Storage and Processing:** Information systems store and process information, producing forecasts.
-  **Data Quality Control** - Provenance information in support of all data domains and policies of each department and unit.
-  **Disseminate Response Predictions, Analysis, and Action** – Predictions are accessed by users and relevant departments for appropriate response actions.
-  **Preparedness Strategies** – Departments relay information, issue warnings, and carry out preparedness strategies. 
-  **End Event** - data is updated which will eventually be used in predicting systems further improving the system.

![Screenshot (18)](https://github.com/user-attachments/assets/c9e618e8-1875-44a7-b3d9-f149f6878838)

Link for references: https://demo.bpmn.io/new, 

 **PHASE 3**
 
 **Logical Data Model Design**
 
In the design below, we clearly represent entities, their attributes, and relationships between them, including:
Entities and Attributes: Each key entity has specific attributes (fields) and an identified primary key.
Relationships: Define the logical connections between entities with foreign keys to maintain referential integrity.
Constraints: Outline constraints like primary keys, foreign keys, and unique or not-null constraints where applicable.

**Entity Descriptions**
1. **Disaster**
Attributes: Disaster_ID, Disaster_Type, Date, Magnitude, Location_ID
2. **Location**
Attributes: Location_ID, Country, State, City
3. **Prediction**
Attributes: Prediction_ID, Disaster_Type, Predicted_Date, Risk_Level, Predicted_Location_ID, Prediction_Method
4. **Weather Condition**
Attributes: Condition_ID, Location_ID, Temperature, Rainfall, Date
5. **Preparedness Measure**
Attributes: Measure_ID, Disaster_ID, Measure_Description, Measure_Type, Start_Date, End_Date
6. **Historical Disaster Data**
Attributes: HistoricalData_ID, Disaster_ID, Location_ID, Date, Impact_Level, Response_Time

**Entity-Relationship Diagram (ERD)**
The ERD represents relationships between entities:

- **Disaster to Location**: One-to-many relationship.
- **Prediction to Location**: Many-to-one relationship.
- **Weather Condition to Location**: Many-to-one relationship.
- **Preparedness Measure to Disaster**: One-to-many relationship.
- **Historical Disaster Data to Disaster and Location**: Many-to-many relationship.

![Screenshot (19)](https://github.com/user-attachments/assets/ce78ab05-0c4c-4924-ac80-3e874adad01f)

**Situations Presided Over By The Database**
The architecture of the database will enable the system to capture some critical disaster management scenarios, such as:

   - Real-time forecasting by associating weather patterns with the occurrence of disasters.
   - The monitoring of disaster consequences and actions taken over a period.
   - Consolidated information is therefore allowed for rapid strategic responses and planning of emergency management.



### Hawks Group Task Assignment

1. **Project Name & Description**:
   - **Assigned to:** *Mayanja Leon Sengendo, Mugabekazi Liliane, Iriza Gatera Merveille*
   - **Task:** Collaborate to write a brief description and name for the project.

2. **Installation**:
   - **Assigned to:** *Mugabekazi Liliane, Mireille Elyse Kubwayo, Sano Chris Armel*
   - **Task:** Outline steps for setting up and installing necessary tools/software.

3. **Usage**:
   - **Assigned to:** *Iriza Gatera Merveille, Sabour Yacoub Mahamat, IRADUKUNDA Boris*
   - **Task:** Create usage instructions and examples for running the project.

4. **Contributing**:
   - **Assigned to:** *Mireille Elyse Kubwayo, Sano Chris Armel, Ishimwe Joyeuse*
   - **Task:** Write guidelines on how others can contribute to the project.

5. **License**:
   - **Assigned to:** *Sano Chris Armel, Nsengiyumva Egide, Ange Kimberly Mukeshimana*
   - **Task:** Select and include a license for the project.

6. **Authors and Acknowledgment**:
   - **Assigned to:** *Sabour Yacoub Mahamat, IRADUKUNDA Boris, Ishimwe Joyeuse*
   - **Task:** List authors and any acknowledgments.

7. **Versioning**:
   - **Assigned to:** *IRADUKUNDA Boris, Ishimwe Joyeuse, Nsengiyumva Egide*
   - **Task:** Specify versioning information and how to update it.

8. **Contact Information**:
   - **Assigned to:** *Ishimwe Joyeuse, Nsengiyumva Egide, Ange Kimberly Mukeshimana*
   - **Task:** Provide contact information for project queries.

9. **FAQs (if applicable)**:
   - **Assigned to:** *Nsengiyumva Egide, Ange Kimberly Mukeshimana, Namahoro Sandrine Marie Merci*
   - **Task:** Compile a list of common questions and answers.

10. **Dependencies**:
    - **Assigned to:** *Ange Kimberly Mukeshimana, Namahoro Sandrine Marie Merci, Mayanja Leon Sengendo*
    - **Task:** List all dependencies and their installation methods.

11. **Code Structure / Folder Structure**:
    - **Assigned to:** *Namahoro Sandrine Marie Merci, Mayanja Leon Sengendo, Mugabekazi Liliane*
    - **Task:** Document the project’s file and folder structure.




# Disaster Management Database System: README Phase 4,5 and 6.

## **Project Overview**
The Disaster Management Database System shall support the efficiency and effectiveness of managing disaster data, enabling disaster prediction, monitoring, preparedness, and response planning using an Oracle Pluggable Database, PDB. This project will outline designing, creating, and interacting with a relational database system suited to disaster management needs.

---
 
## **Phase 4: Database Creation and Naming**

 
### **Physical Database Structure**
With the logical database model, translation to a physical structure yields the following tables:

1. **Created Tables**: 
   - `Location`: Geographical data is stored here. 
   - `Disaster`: It stores the details of disasters. 
   - `Prediction`: Maintains disaster predictions. 
   - `Weather_Condition`: The weather-related data is tracked. 
   - `Preparedness_Measure`: It lists measures taken against disaster preparedness.
- `Historical_Disaster_Data`: Archives historical disaster details.

2. **Relationships Established**:
   - Foreign key constraints ensure referential integrity between tables, e.g., `Disaster.Location_ID` references `Location.Location_ID`.

3. **Constraints Applied**:
   - Primary keys, foreign keys, unique constraints, and data types are enforced to ensure data integrity.



### **Oracle Enterprise Manager (OEM)**
Oracle Enterprise Manager is configured to monitor and manage the database. Screenshots demonstrating progress, including:
- Database creation
- Table implementation
- Execution of queries 
are uploaded as a part of the reporting process.

## **Phase 5: Table Implementation and Data Insertion**

### **Table Creation**
The logical model is implemented by creating the following tables in Oracle:
- `Location`
- `Disaster`
- `Prediction`
- `Weather_Condition`
- `Preparedness_Measure`
- `Historical_Disaster_Data`

### **Data Insertion**
Insert meaningful and realistic data into tables for test and demo purposes. Example:
- **Location Table**:
 ```sql
 INSERT INTO Location (Location_ID, Country, State, City)
VALUES (1, 'Rwanda', 'Northern Province', 'Musanze');
```
- **Disaster Table:**
```sql
INSERT INTO Disaster (Disaster_ID, Disaster_Type, Disaster_Date, Magnitude, Location_ID) 
VALUES (1, 'Imitingito', TO_DATE('2024-12-05', 'YYYY-MM-DD'), 7.5, 1);
```

### **Data Integrity**
Data are checked against the problem statement for validity. Queries and operations are used to validate the correctness and relevance of the inserted data.

---

## **Phase 6: Database Interaction and Transactions**

### **Database Operations**
Different join operations are performed to fetch information. These include the following:

1. **Cross Join**:
   ```sql
   SELECT Disaster.Disaster_Type, Location.Country, Location.City 
   FROM Disaster CROSS JOIN Location;
   ```
2. **Inner Join**:
   ```sql
   SELECT Disaster.Disaster_Type, Location.Country, Location.City 
   FROM Disaster 
   INNER JOIN Location 
   ON Disaster.Location_ID = Location.Location_ID;
   ```
3. **Outer Join**:
   ```sql
SELECT Prediction.Prediction_ID, Prediction.Disaster_Type, Location.Country 
   FROM Prediction 
   LEFT OUTER JOIN Location 
   ON Prediction.Predicted_Location_ID = Location.Location_ID;
   ```
### **Transaction Management**
Transactions assure consistency and robustness:
1. **Insert Disaster and Preparedness Measure in the Same Transaction**:
   ```sql
   BEGIN;
   INSERT INTO Disaster (Disaster_ID, Disaster_Type, Disaster_Date, Magnitude, Location_ID)
VALUES (6, 'Landslide', TO_DATE('2024-12-05', 'YYYY-MM-DD'), 5.1, 3);
   INSERT INTO Preparedness_Measure (Measure_ID, Disaster_ID, Measure_Description, Measure_Type, Start_Date, End_Date)
   VALUES (6, 6, 'Slope stabilization measures.', 'Infrastructure', TO_DATE('2024-11-01', 'YYYY-MM-DD'), TO_DATE('2024-12-01', 'YYYY-MM-DD'));
   COMMIT;
   ```

2. **Rollback on Error**:
   ```sql
   BEGIN;
   INSERT INTO Prediction (Prediction_ID, Disaster_Type, Predicted_Date, Risk_Level, Predicted_Location_ID, Prediction_Method)
VALUES (6, 'Flood', TO_DATE('2024-12-15', 'YYYY-MM-DD'), 'High', 99, 'Rainfall Analysis');
   ROLLBACK;
   ```
