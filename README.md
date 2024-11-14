# Wed_Hawks_DisasterPredictionManagementSystem
The Disaster Management Database enables rapid response, preparedness, and mitigation for natural disasters. It centralizes real-time and historical data on disasters and weather, using predictive models to aid decision-making.


PHASE TWO: Business Process Modeling



SCOPE

The project scope focuses on creating a centralised disaster management database to assist in disaster prediction, forecasting, preparedness, and response. This aligns with the MIS framework by streamlining real-time data collection and analysis to improve decision-making in disaster scenarios. The objectives are:
Enable Real-Time Data Processing to support timely disaster alerts and mitigation measures.
Enhance Disaster Preparedness and Response by providing actionable insights to governments, humanitarian agencies, and response teams.
Facilitate Global Collaboration through standardised data sharing and a centralised information system.
Expected Outcomes:
Enhanced accuracy in disaster predictions and risk assessments.
Increased efficiency in coordinating and managing disaster response efforts.
Data-driven support for making informed decisions during disaster events.

IDENTIFY KEY ENTITIES

In the disaster management database, the key entities and their roles within the process include:

Users (Emergency Planners, Data Analysts, Field Responders):
Role: These users interact with the database to input, analyse, and access information related to disasters. Emergency planners use the data to prepare for disasters, analysts predict potential disaster events, and field responders access up-to-date information to guide their actions.
Interaction: They interact directly with the system, both inputting raw data (e.g., current weather conditions) and retrieving processed insights (e.g., predicted disaster risks).
Departments (Government Agencies, Humanitarian Organisations, Weather Stations):
Role: Each department provides critical data (e.g., weather reports, historical disaster data) and uses the database insights for situational awareness and response planning.
Interaction: Departments supply real-time data to the database and use processed data for decision-making. For example, weather stations continuously update the database with current environmental conditions.
Information Systems (Database Management System, Predictive Modeling Software, Data Collection Tools):
Role: This MIS component stores and manages large volumes of data from various sources, enabling predictive modelling and reporting.
Interaction: The information systems allow users and departments to access, process, and analyze data. Predictive models within the system assess risk levels based on input data and historical patterns.
Data Elements (Disaster Type, Location, Weather Conditions, Risk Level):
Role: These are the specific data points stored and analysed within the system, forming the basis for predictive models and decision-making.
Interaction: Data elements are continuously updated by users and departments, while predictive algorithms analyse and update them as necessary. For instance, “Risk Level” is a data element that changes dynamically based on real-time inputs from “Weather Conditions.”
External Data Sources (Satellite Data, Global Disaster Networks):
Role: External sources contribute supplemental data, providing global and region-specific data feeds, including satellite imagery and other remote-sensing data.
Interaction: These sources supply the primary information systems with essential data points, enhancing predictive accuracy and allowing for more comprehensive disaster assessments.

Swimlane Diagram to outline the processes in the Disaster Management Database. 

This figure will include a swimlane for each of the key actors or departments in the process: Users, Departments, Information Systems, and External Data Sources.

Swim lane components: Each swimlane is used in explaining the participation of every member or sector in disaster management. The flow in every lane indicates the duties and activities of each member while the junction of lanes indicates the point where two or more members interact with each other by exchanging communication or data.
Swimlane 1: 
Users (Emergency Planners, Data Analysts, Field Responders) 
Identify Disaster Event: Avail a window of opportunity for the input of alerts whether preliminary in nature or real-time disasters.
 Request Data Analysis: Make a call to the system on duty to carry out some data period analysis or forecasting.
 Review Prediction Results: Study the outcome, which entails disaster, its impact, and the area covered by each risk level. 
Coordination: Liaisons with pertinent units (sister agencies) for recommendations and initiation of preparedness or response measures. 
Disaster Status Update: Filing of information that deals with changes or updates during and after the disaster occurrence to minimise impact of forecast deafness in the future. 
Swimlane 2: 
Departments Government Agencies, Humanitarian Organisations, Weather Stations 
Provide Current Data Update on the present status of the atmosphere, any exterior change and any catastrophes in progress. 
Check Data Accuracy Assure that the information given is available and exact to the needs of the prediction models. 
Make Decisions Based on Processed Data: Get processed information that shows the level of risks and forecasted impact for planning or strategizing. 
Distribute Warnings: Work with end-users to distribute appropriate forward warnings to people who are at risk. 
Conduct Preparedness Actions: Execute proactive steps such as ordering evacuations based on what the system forecasts.
Swimlane 3: 
Information Systems - DBMS, Predictive Models and Data Collection methods
Collect Data: Get primary objective data from both remote sites and inland departments.
Store Data: Store safely disaster data along with historical and ongoing data.
Run Predictive Models: Keep records and predict incoming data to calculate levels of risks involved and the degree of likely disasters.
Output Results: Return users/departments' requests in a decision-making manner.
Data Integrity: Update the estimate files with fresh numbers to enhance the reliability of the estimates.
Swimlane 4: 
Satellite Data Global Disaster Networks External Data Feeds 
Data Analysis and Collection: Collect data from various external sources, such as satellite images and seismic events.
Forward the Data to Information System: Feed data into the hosting partner's repository.
Allow Real Time Updates: Incentivize the interventions to let the data move without any hindrance, in order to maximise the processing and analysis of such data as seamlessly as possible.
Collaboration for Standardised Data: Work with the respective departments to find out if all the data will have uniform measures and formats for a complete integration.
Process Mapping with BPMN with Explanations
Following are some of the key BPMN elements that can be used for disaster management processes:
Pools and Swimlanes: Usually segregated into four lanes, representing Users, Departments, Information Systems, and External Data Sources.
Start and End Events: Represent the start and the end of a particular process using circles.
Tasks (Activities): Located inside the rectangle, each is labeled on the tag, for example, "Collect Data," "Run Predictive Models," … etc.
Data Objects: Inputs/outputs are represented with the use of a document icon called Data Object, which means data is being processed therein. 
Sequence Flows: Arrows in the form of dashes show how activities or tasks flow on any project in terms of sequence. 
Gateways or Decisions: This is represented in a form of diamond shape and represents instances where a decision has to be made, for example, if data is accurate at the said level.

Links for references: https://demo.bpmn.io/new, 
1. Start Event (Users)
Element: Start Event (Circle)
The process begins with the Users initiating a disaster event.
Task: "Identify Disaster Event"
Element: Activity (Rectangle)
Action: Users input preliminary or real-time data related to disaster alerts.
2. Data Collection from External Sources (External Data Sources)
Task: "Data Analysis and Collection"
Element: Activity (Rectangle)
Action: External Data Sources collect data, such as satellite images or weather reports.
Sequence Flow: Connects from the Start Event to this task, indicating that data is now being collected.
3. Forward Data to Information System (External Data Sources)
Task: "Forward Data to Information System"
Element: Activity (Rectangle)
Action: External data is fed into the Information System.
4. Data Storage and Processing (Information Systems)
Task: "Store Data"
Element: Activity (Rectangle)
Action: Information Systems store raw and historical data securely.
Task: "Run Predictive Models"
Element: Activity (Rectangle)
Action: Predictive models run forecasts, assessing risk levels based on stored data.
Task: "Output Results"
Element: Activity (Rectangle)
Action: Processed data and prediction results are made available to Users and Departments.
5. Data Accuracy Check (Departments)
Gateway: Data Validation Check
Element: Gateway (Diamond)
Action: Departments verify the accuracy and relevance of the processed data.
Decision Flow:
If Accurate: Continue to the next steps in Users and Departments.
If Inaccurate: Data is re-evaluated and processed again in the Information Systems.
6. Analyze and Act on Predictions (Users)
Task: "Review Prediction Results"
Element: Activity (Rectangle)
Action: Users assess prediction results and identify potential areas impacted by the disaster.
Task: "Coordinate Response Measures"
Element: Activity (Rectangle)
Action: Users coordinate with other departments for a structured response.
7. Preparedness and Response (Departments)
Task: "Provide Current Data Update"
Element: Activity (Rectangle)
Action: Departments supply real-time updates to the Information System.
Task: "Make Decisions Based on Processed Data"
Element: Activity (Rectangle)
Action: Departments analyze processed data to make informed decisions.
Task: "Distribute Warnings"
Element: Activity (Rectangle)
Action: Warnings are issued to the public or targeted at-risk groups.
Task: "Conduct Preparedness Actions"
Element: Activity (Rectangle)
Action: Departments prepare and implement response measures, like ordering evacuations.
8. End Event (Users)
Task: "Update Disaster Status"
Element: Activity (Rectangle)
Action: Users update the disaster status to refine predictive algorithms and response strategies for future events.
End Event:
Element: End Event (Circle)
Marks the conclusion of the process flow, with updated disaster data feeding into future predictive efforts.
AIM OF DATABASE
The MIS-based disaster management process model aims to address high levels of response, real-time efficient decision-making, and coordination between departments. Each swimlane illustrates an alternate entity in the partnership for disaster management: 

Users - Emergency Planners, Data Analysts-Initiate processes to detect the occurrence of disaster events and analyze predictive results
Departments - Government Agencies, Humanitarian Organizations - Implement response actions at the level of ensuring data integrity
Information Systems - Core in storing data, predictive modeling, and providing results to users to support their decision-making.
These external sources provide the fundamental real-time data on weather and environmental conditions that are needed for accurate prediction. Significance of the Process in Relation to MIS This process has given an indication of how MIS will benefit by ensuring there is centralization of data management and integrity as well as more informed decision-making in disaster management.
 The model further clearly denotes workflows and decision points to enable: 
Informed Decision Making: Real-time data and predictive analytics augment emergency preparedness.
Organisational Goal Alignment: Aligning the department and data flow in the MIS process facilitates the goals of lessening disaster events impact, raising public safety levels, and improving interagency coordination.

 Logical Data Model Design
In the design below, we clearly represent entities, their attributes, and relationships between them, including:
Entities and Attributes: Each key entity has specific attributes (fields) and an identified primary key.
Relationships: Define the logical connections between entities with foreign keys to maintain referential integrity.
Constraints: Outline constraints like primary keys, foreign keys, and unique or not-null constraints where applicable.
2. Detailed Entity Descriptions
Based on Phase 1, here are the main entities and their attributes:
Disaster
Attributes:
Disaster_ID (Primary Key)
Disaster_Type
Date
Magnitude
Location_ID (Foreign Key referencing Location)
Constraints:
Disaster_ID: Unique, Not Null
Location_ID: Foreign Key referencing Location(Location_ID)
CREATE TABLE Disaster (
    Disaster_ID INT PRIMARY KEY,
    Disaster_Type VARCHAR2(50) NOT NULL,
    Disaster_Date DATE NOT NULL,
    Magnitude NUMBER(5, 2),
    Location_ID INT NOT NULL,
    CONSTRAINT fk_Location_ID FOREIGN KEY (Location_ID) REFERENCES Location(Location_ID)
);

Location
Attributes:
Location_ID (Primary Key)
Country
State
City

CREATE TABLE Location (
    Location_ID INT PRIMARY KEY,
    Country VARCHAR(50) NOT NULL,
    State VARCHAR(50),
    City VARCHAR(50),
    );
Prediction
Attributes:
Prediction_ID (Primary Key)
Disaster_Type
Predicted_Date
Risk_Level
Predicted_Location_ID (Foreign Key referencing Location)
Prediction_Method
Constraints:
Predicted_Location_ID: Foreign Key referencing Location(Location_ID)



CREATE TABLE Prediction (
    Prediction_ID INT PRIMARY KEY,
    Disaster_Type VARCHAR2(50) NOT NULL,
    Predicted_Date DATE NOT NULL,
    Risk_Level VARCHAR2(20),
    Predicted_Location_ID INT NOT NULL,
    Prediction_Method VARCHAR2(100),
    CONSTRAINT fk_Predicted_Location_ID FOREIGN KEY (Predicted_Location_ID) REFERENCES Location(Location_ID)
);
Weather_Condition
Attributes:
Condition_ID (Primary Key)
Location_ID (Foreign Key referencing Location)
Temperature
Rainfall
Date
Constraints:
Location_ID: Foreign Key referencing Location(Location_ID)
CREATE TABLE Weather_Condition (
    Condition_ID INT PRIMARY KEY,
    Location_ID INT NOT NULL,
    Temperature NUMBER(5, 2),
    Rainfall NUMBER(5, 2),
    Weather_Date DATE NOT NULL,
    CONSTRAINT fk_Weather_Location_ID FOREIGN KEY (Location_ID) REFERENCES Location(Location_ID)
);
Preparedness_Measure
Attributes:
Measure_ID (Primary Key)
Disaster_ID (Foreign Key referencing Disaster)
Measure_Description
Measure_Type (e.g., Evacuation, Flood Barriers)
Start_Date
End_Date
Constraints:
Disaster_ID: Foreign Key referencing Disaster(Disaster_ID)
CREATE TABLE Preparedness_Measure ( 
    Measure_ID INT PRIMARY KEY,
    Disaster_ID INT NOT NULL,
    Measure_Description VARCHAR2(4000), -- Use VARCHAR2 for text-like data
    Measure_Type VARCHAR2(50),
    Start_Date DATE,
    End_Date DATE,
    CONSTRAINT fk_Preparedness_Disaster_ID FOREIGN KEY (Disaster_ID) REFERENCES Disaster(Disaster_ID)
);
Historical_Disaster_Data
Attributes:
HistoricalData_ID (Primary Key)
Disaster_ID (Foreign Key referencing Disaster)
Location_ID (Foreign Key referencing Location)
Date
Impact_Level (Scale of destruction)
Response_Time
Constraints:
HistoricalData_ID: Unique, Not Null
Disaster_ID: Foreign Key referencing Disaster(Disaster_ID)
Location_ID: Foreign Key referencing Location(Location_ID)
CREATE TABLE Historical_Disaster_Data (
    HistoricalData_ID INT PRIMARY KEY,
    Disaster_ID INT NOT NULL,
    Location_ID INT NOT NULL,
    Date DATE NOT NULL,
    Impact_Level VARCHAR(20),
    Response_Time DECIMAL(5, 2),
    CONSTRAINT HistoricalData_ID_Unique UNIQUE (HistoricalData_ID),
    CONSTRAINT fk_Historical_Disaster_ID FOREIGN KEY (Disaster_ID) REFERENCES Disaster(Disaster_ID),
    CONSTRAINT fk_Historical_Location_ID FOREIGN KEY (Location_ID) REFERENCES Location(Location_ID)
);




3. Entity-Relationship Diagram (ERD)
Disaster to Location: Disaster is linked to Location with a one-to-many relationship, as multiple disasters can occur in the same location.
Prediction to Location: Prediction is linked to Location with a many-to-one relationship, as predictions are made for specific locations.
Weather_Condition to Location: Weather_Condition has a many-to-one relationship with Location, as weather data is specific to each location.
Preparedness_Measure to Disaster: Preparedness_Measure has a one-to-many relationship with Disaster, as multiple preparedness actions can be associated with one disaster.
Historical_Disaster_Data to Disaster and Location: Historical_Disaster_Data is linked to both Disaster and Location in a many-to-many relationship, as historical data could pertain to various disaster events across multiple locations.
4. Handling Data Scenarios
This logical model can handle scenarios such as:
Real-time disaster predictions by storing recent weather data and linking predictions to specific locations.
Historical data tracking by maintaining disaster records and past response effectiveness.
Decision-making support by centralising data on locations, preparedness actions, and disaster severity for effective emergency planning.


