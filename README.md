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
