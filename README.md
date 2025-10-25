# Blood Bank Management System

## 1. Introduction

Blood banks play a crucial role in collecting, storing, and supplying blood to individuals in need. Those who generously contribute blood are known as 'donors.' The collected blood is meticulously categorized based on blood groups to ensure efficient distribution, with a focus on preventing contamination. The primary objective of blood banks is to furnish hospitals and healthcare systems with the vital resource needed to save patients' lives.

Monitoring the quality of blood and keeping track of donors pose significant challenges for blood banks. The existing systems fall short in meeting the requirements for maintaining high-quality blood and effectively managing donor information. In response to these limitations, we have introduced a novel solution known as the 'Blood Donation Management System.'

The 'Blood Bank Management System' offers a comprehensive approach to monitoring blood quality and tracking available blood when requested by recipients. Manual systems, currently in use, are time-consuming and lack effectiveness. The 'Blood Bank Management System' automates blood distribution, streamlining the process. The system's database encompasses thousands of records for each blood bank, facilitating efficient searching of available blood and saving considerable time compared to the manual system.

## 2. Information on Entities

In total, we have eight entities:

- **Blood_Donor:**
  - **Attributes:** `bd_ID` (PK), `bd_name`, `bd_sex`, `bd_age`, `bd_Bgroup`, `bd_reg_date`, `bd_phNo`
  - **Description:** The person who donates blood.

- **Recipient:**
  - **Attributes:** `reci_ID` (PK), `reci_name`, `reci_age`, `reci_Bgrp`, `reci_Bqnty`, `reci_sex`, `reci_reg_date`, `reci_phNo`
  - **Description:** The person who receives blood from the blood bank.

- **BB_Manager:**
  - **Attributes:** `m_ID` (PK), `m_Name`, `m_phNo`
  - **Description:** Manages available blood samples and handles requests.

- **Recording_Staff:**
  - **Attributes:** `reco_ID` (PK), `reco_Name`, `reco_phNo`
  - **Description:** Registers donors and recipients.

- **BloodSpecimen:**
  - **Attributes:** `specimen_number` (PK), `b_group` (PK), `status`
  - **Description:** Information on blood samples available in the bank.

- **DiseaseFinder:**
  - **Attributes:** `dfind_ID` (PK), `dfind_name`, `dfind_PhNo`
  - **Description:** The doctor who checks blood for contaminations.

- **Hospital_Info:**
  - **Attributes:** `hosp_ID` (PK), `hosp_name`, `hosp_needed_Bgrp`, `hosp_needed_Bqnty`
  - **Description:** Information on hospitals.

- **City:**
  - **Attributes:** `city_ID` (PK), `city_name`
  - **Description:** Stores city information for donors, recipients, and hospitals.

## 3. Relationships Between Entities

- **City and Hospital_Info:** "in" (1-to-Many)
- **City and Blood_Donor:** "lives in" (1-to-Many)
- **City and Recipient:** "lives in" (1-to-Many)
- **Recording_Staff and Donor:** "registers" (1-to-Many)
- **Recording_Staff and Recipient:** "records" (1-to-Many)
- **Hospital_Info and BB_Manager:** "gives order to" (1-to-Many)
- **BB_Manager and Blood Specimen:** "deals with specimen" (1-to-Many)
- **Recipient and BB_Manager:** "requests to" (1-to-Many)
- **Disease_finder and Blood Specimen:** "checks" (1-to-Many)
