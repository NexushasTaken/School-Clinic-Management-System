Scopes and Objectives
Project Name and Description
Project Name: School Clinic Patient and Medicine Inventory Management System
Project Description
The School Clinic Patient and Medicine Inventory Management System is an integrated system designed to record, monitor, and manage student clinic consultations and first-aid medicine inventory. It allows clinic staff, nurses, and clinic assistants to log patient visits, track symptoms and treatments, and monitor medicine availability, usage, and expiration dates. The system aims to improve efficiency, reduce manual record-keeping, and ensure accurate, real-time tracking of patient care and medicine resources within the school clinic.
Project Scopes
The School Clinic Patient and Medicine Inventory Management System focuses on managing student clinic consultations and first-aid medicine inventory within the school clinic. The system is designed for use by authorized clinic personnel to ensure accurate record-keeping and efficient clinic operations.
 
Project Deliverables
1.	Patient Monitoring
a.	Recording patient clinic visits
b.	Logging symptoms, reasons for consultation, and treatments provided
c.	Storing basic patient information for clinic reference
2.	Medicine Inventory Management
a.	Recording available first-aid medicines
b.	Monitoring stock quantities and expiration dates
c.	Tracking medicine usage based on patient treatments
3.	Integrated System Functions
a.	Automatic deduction of medicine stock after treatment is recorded
b.	Real-time update of medicine availability
4.	Search and Retrieval
a.	Searching student patient records
b.	Searching medicine details quickly and accurately
5.	Data Management
a.	Secure storage of patient and medicine records
b.	Backup and basic data recovery features
 
Project Objectives
To address the identified problems in the school clinic, we propose the development of a School Clinic Patient and Medicine Inventory Management System.

The proposed system will computerize the recording and monitoring of student clinic consultations by allowing clinic staff, nurses, and clinic assistants to log patient visits, symptoms, reasons for consultation, and treatments provided in a centralized database. This will ensure organized, accurate, and easily retrievable patient records.

The integration of patient monitoring and medicine inventory will eliminate inconsistencies between treatment records and medicine usage. A built-in search function will enable users to quickly locate patient records or specific medicines, reducing delays in clinic operations.




Statement of the Problem
The School Clinic plays an essential role in providing basic healthcare services to students. However, the clinic currently relies on manual and paper-based methods for recording student consultations and managing first-aid medicine inventory. This traditional approach leads to several operational challenges.

Patient records are difficult to organize, retrieve, and monitor, especially when tracking previous clinic visits, symptoms, and treatments provided. Manual record-keeping increases the risk of incomplete, inaccurate, or misplaced patient information, which can delay medical assistance and affect the quality of care given to students.
The lack of integration between patient treatment records and medicine inventory further complicates clinic operations. Medicine usage is not automatically recorded, leading to inconsistencies between actual stock levels and recorded inventory data.

Therefore, there is a need for an integrated system that can efficiently record and monitor student patient consultations while simultaneously managing first-aid medicine inventory. Such a system will improve data accuracy, enhance clinic efficiency, and support better healthcare service delivery within the school.
 
Solution
To address the identified problems in the school clinic, we propose the development of a School Clinic Patient and Medicine Inventory Management System.
 
The proposed system will computerize the recording and monitoring of student clinic consultations by allowing clinic staff, nurses, and clinic assistants to log patient visits, symptoms, reasons for consultation, and treatments provided in a centralized database. This will ensure organized, accurate, and easily retrievable patient records.
 
The integration of patient monitoring and medicine inventory will eliminate inconsistencies between treatment records and medicine usage. A built-in search function will enable users to quickly locate patient records or specific medicines, reducing delays in clinic operations.
 
Overall, the proposed system will reduce manual paperwork, minimize data entry errors, improve clinic efficiency, and support safer and more effective healthcare services for students.
 
Proposed System
The proposed School Clinic Patient and Medicine Inventory Management System aims to improve clinic operations by digitizing patient records and integrating medicine inventory management. The system will help clinic staff, nurses, and clinic assistants efficiently record student consultations, monitor medicine availability, and ensure accurate usage tracking.

Characteristics
The proposed system is a web-based School Clinic Patient and Medicine Inventory Management System designed to improve the efficiency and organization of clinic operations. Due to the continuous advancement of technology, the system aims to replace the existing manual and paper-based methods used in recording student clinic consultations and managing first-aid medicine inventory.

Unlike systems that require individual user accounts, the proposed system does not include a user login feature. The system is intended to be accessed directly through designated clinic computers and used only by authorized clinic staff, nurses, and clinic assistants. This approach simplifies system usage and ensures faster access during emergency or high-volume clinic situations.

The system utilizes a centralized database to store patient records and medicine inventory data. It automatically updates medicine stock levels based on recorded treatments, reduces paperwork, improves data accuracy, and allows quick retrieval of patient and medicine information.
 
Processes
Step 1: System Access
-	Clinic staff, nurses, or clinic assistants access the system directly from the clinic computer
-	No login or credential verification is required
Step 2: Patient Registration and Consultation Recording
-	Register new student patient information
-	Search and select existing patient records
-	Record symptoms, reason for consultation, and date of visit
Step 3: Treatment and Medicine Recording
-	Record treatments or first-aid services provided
-	Select medicines used during the consultation
-	The system automatically deducts medicine quantities from the inventory
Step 4: Medicine Inventory Management
-	Add new medicine stocks to the system
-	Monitor available medicine quantities and expiration dates
-	View real-time updates of medicine inventory
Step 5: Search and Record Retrieval
-	Search and retrieve patient consultation records
-	Search medicine details quickly and accurately
Step 6: Data Storage and Maintenance
-	All patient and medicine records are stored in a centralized database
-	Data backup can be performed to prevent record loss


Functional Decomposition Diagram
```mermaidjs
graph TD
    %% Main Title
    System["School Clinic Patient and Medicine Inventory Management System"]

    %% Main Modules
    PCM["Patient Consultation Management"]
    MIM["Medicine Inventory Management"]
    RM["Record Management"]
    RAM["Reports and Monitoring"]

    %% Connections to Main Modules
    System --> PCM
    System --> MIM
    System --> RM
    System --> RAM

    %% Patient Consultation Sub-items
    PCM --> EPN["Encode Patient Information"]
    PCM --> RSC["Record Symptoms and Concerns"]
    PCM --> AOD["Assessment and Observation Decision"]
    PCM --> RTG["Record Treatment Given"]

    %% Medicine Inventory Sub-items
    MIM --> CMA["Check Medicine Availability"]
    MIM --> DM["Dispense Medicine"]
    MIM --> ASU["Automatic Stock Update"]
    MIM --> MME["Monitor Medicine Expiration"]

    %% Record Management Sub-items
    RM --> SPR["Store Patient Records (Database)"]
    RM --> STR["Store Treatment Records"]
    RM --> SMU["Store Medicine Usage Records"]

    %% Reports and Monitoring Sub-items
    RAM --> DPR["Daily Patient Reports"]
    RAM --> MUR["Medicine Usage Reports"]
    RAM --> ISR["Inventory Status Reports"]
```

System Flowchart
```mermaidjs
graph TD
    Start([Patient Entered the Clinic]) --> Registration[Patient Registration]
    Registration --> Info[Patient Entering Information]
    
    Database[(Patient Record Database)]
    Info -.- Database
    
    Info --> Exists{Patient Exists?}
    Exists -- No --> AddNew[Add New Patient]
    Exists -- Yes --> Record[Record Consultation]
    AddNew --> Record
    
    Exists -.- Database
    
    Record --> Medicine{Medicine Needed?}
    Medicine -- No --> Skip[Skip Medicine Step]
    Medicine -- Yes --> A{{A}}
    Skip --> A
    
    Medicine -.- Database
```
System FLowchart Continuation:
```mermaidjs
graph TD
    A{{A}} --> Check[Check Medicine Inventory]
    
    InventoryDB[(Medicine Inventory Database)]
    Check -.- InventoryDB
    
    Check --> Available{Medicine Available?}
    Available -- No --> Notify[Notify Out of Stock]
    Available -- Yes --> Dispense[Dispense Medicine]
    Notify --> Dispense
    
    Available -.- InventoryDB
    Dispense -.- InventoryDB
    
    Dispense --> Update[Update Patient Record & Inventory]
    
    PatientDB[(Patient Record Database)]
    Update -.- PatientDB
    Update -.- InventoryDB
    
    Update --> Reports[Generate Daily / Monthly Reports]
    Reports -.- PatientDB
    
    Reports --> End([Patient Exited the Clinic])
```

Data Flow Diagram
```mermaidjs
graph LR
    %% Entities
    SP[Students / Patients]
    NCA[Nurse / Clinic Assistant]

    %% System
    System(0 <br/> SCHOOL CLINIC PATIENT AND MEDICINE INVENTORY MANAGEMENT SYSTEM)

    %% Flow lines
    System -- Treatment Information --> SP
    System -- Patient Records --> NCA
    System -- Medicine Availability --> NCA
    NCA -- Patient Record Input --> System
    NCA -- Medicine Details Input --> System
```

Detailed Data Flow Diagram
```mermaidjs
graph TD
    %% External Entities
    SP[Students / Patients]
    NCA[Nurse / Clinic Assistant]

    %% Processes
    P1[1.0 Manage Patient Record]
    P2[2.0 Manage Medicine Inventory]
    P3[3.0 Search and Retrieve Records]

    %% Data Stores
    D1[(D1 Patient Record Database)]
    D2[(D2 Medicine Inventory Database)]

    %% Connections for P1
    SP -- Patient consultation details --> P1
    P1 -- Patient Details --> NCA
    NCA -- Accesses patient records --> P1
    P1 -- Patient Records --> D1

    %% Connections for P2
    NCA -- Medicine Details Input --> P2
    P2 -- Medicine Details --> D2
    D2 -- Updated medicine stock data --> P2
    P1 -- Medicine usage details --> P2
    P2 -- Medicine availability status --> P1

    %% Connections for P3
    NCA -- Medicine Search Query --> P3
    P3 -- Medicine Details --> NCA
    P3 -- Medicine search query --> D2
    D2 -- Medicine inventory data --> P3
```

---

From the reference above (and the Images), make a PostgreSQL schema tables for it.
but in a format of markdown table (one table).
the table is formatted as Markdown Table, basically put the table inside markdown code block.
Basically a "Data Dictionary".

**Table Format** (Columns):
- 1st - Name - the name of that attribute
- 2nd - Description - Brief description of what is that attribute do
- 3rd - Uhh, idk, see the example table below.
- 4th - Attribute type
- 5th - Attribute Size
- 6th - Sample - A data sample, if Name is Attribute, then the sample is "Bryan"
- 7th - Location - the format is "<table-name>_db.sql"

Example Table(Data Dictionary):
| Name            | Description                                        | Attribute Name    | Attribute Type | Size       | Sample | Location                    |
| --------------- | -------------------------------------------------- | ----------------- | -------------- | ---------- | ------ | --------------------------- |
| User            | Number The computer generated number for the user. | Unum              | Integer        | 11 int     | 23     | ULC_db.sql Applicant_db.sql |
| User First Name | The first name of the user.                        | UFname            | VarChar        | 20 varchar | Shem   | ULC_db.sql                  |

