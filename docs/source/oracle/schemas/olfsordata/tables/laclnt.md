# Client Info Table

Table storing detailed information about clients, including personal details, contact information, identification, financial details, and system-specfic data.

## Table Description

??? quote "LACLNT"

    | **Column Name**          | **Constraint** | **Data Type** | **Description**                                                    |
    |--------------------------|----------------|---------------|--------------------------------------------------------------------|
    | CLIENT_NO                | NOT NULL       | CHAR(8)       | Unique identifier for the client.                                  |
    | TITLE                    | NULLABLE       | CHAR(4)       | Title of the client (e.g., Mr., Mrs., Dr.).                        |
    | SURNAME                  | NULLABLE       | CHAR(50)      | Client's last name or family name.                                 |
    | OTHER_NAMES              | NULLABLE       | CHAR(50)      | Other given names of the client.                                   |
    | SEX                      | NULLABLE       | CHAR(1)       | Gender of the client (e.g., M for Male, F for Female).             |
    | ADDRESS                  | NULLABLE       | CHAR(100)     | Residential or postal address of the client.                       |
    | LOCATION                 | NULLABLE       | CHAR(20)      | General location details.                                          |
    | TOWN                     | NULLABLE       | CHAR(20)      | Town or city of residence.                                         |
    | BIRTH_DATE               | NULLABLE       | DATE          | Date of birth of the client.                                       |
    | MARITAL_STATUS           | NULLABLE       | CHAR(3)       | Marital status of the client (e.g., S for Single, M for Married).  |
    | OCCUPATION_CODE          | NULLABLE       | CHAR(4)       | Code representing the occupation of the client.                    |
    | EMPLOYER_CODE            | NULLABLE       | VARCHAR2(7)   | Code for the client's employer.                                    |
    | BIRTH_PLACE              | NULLABLE       | CHAR(24)      | Place of birth of the client.                                      |
    | IDENTITY_CARD_NO         | NULLABLE       | CHAR(16)      | National identity card number of the client.                       |
    | EMPLOYEE_NO              | NULLABLE       | CHAR(15)      | Employee number if the client is employed.                         |
    | USER_ID                  | NULLABLE       | CHAR(4)       | System user ID associated with the client.                         |
    | CREATION_DATE            | NULLABLE       | DATE          | Date the client record was created.                                |
    | CREATION_ID              | NULLABLE       | CHAR(4)       | Identifier of the user who created the record.                     |
    | PIN_NUMBER               | NULLABLE       | CHAR(15)      | Personal Identification Number (e.g., for tax or government use).  |
    | IDENTITY_TYPE            | NULLABLE       | CHAR(2)       | Type of identification document (e.g., Passport, National ID).     |
    | NAME                     | NULLABLE       | CHAR(100)     | Full name of the client.                                           |
    | PREV_SUM_ASSURED         | NULLABLE       | NUMBER(15)    | Previous sum assured for the client’s insurance coverage.          |
    | NOF_POLICIES             | NULLABLE       | NUMBER(1)     | Number of active insurance policies held by the client.            |
    | FIRST_SURPLUS            | NULLABLE       | NUMBER(13)    | First surplus amount related to financial records.                 |
    | CESSION_NO               | NULLABLE       | CHAR(8)       | Cession number for reinsurance or claims.                          |
    | GROUP_STR                | NULLABLE       | CHAR(2)       | Group structure classification.                                    |
    | OFFCD                    | NULLABLE       | NUMBER(3)     | Office code for client records.                                    |
    | BANK_CODE                | NULLABLE       | CHAR(3)       | Bank code for the client’s primary bank.                           |
    | BRANCH_CODE              | NULLABLE       | CHAR(3)       | Branch code for the client’s primary bank.                         |
    | ACCOUNT                  | NULLABLE       | CHAR(15)      | Bank account number associated with the client.                    |
    | SECOND_SURPLUS           | NULLABLE       | NUMBER(13)    | Second surplus amount related to financial records.                |
    | POSTAL_CODE              | NULLABLE       | CHAR(15)      | Postal code for the client’s address.                              |
    | GUARDIAN                 | NULLABLE       | CHAR(24)      | Name of the guardian if the client is a minor.                     |
    | TELEPHONE                | NULLABLE       | CHAR(12)      | Primary contact number of the client.                              |
    | SORT_NO                  | NULLABLE       | NUMBER(6)     | Sorting number for internal processes.                             |
    | SORT_ID                  | NULLABLE       | CHAR(1)       | Sorting identifier for internal processes.                         |
    | EMAIL                    | NULLABLE       | CHAR(50)      | Email address of the client.                                       |
    | AGE_ADMITTED             | NULLABLE       | CHAR(1)       | Age at which the client was admitted into the system.              |
    | USER_STR                 | NULLABLE       | CHAR(7)       | Additional user-specific data as a string.                         |
    | ORGANISATION             | NULLABLE       | CHAR(30)      | Organisation the client is affiliated with.                        |
    | OCCUPATION               | NULLABLE       | CHAR(100)     | Full details of the client’s occupation.                           |
    | STAFF_YN                 | NULLABLE       | CHAR(1)       | Indicates if the client is staff (Y for Yes, N for No).            |
    | SA_SUM                   | NULLABLE       | NUMBER(13,2)  | Total assured sum for financial purposes.                          |
    | ID_NO_COUNTRY            | NULLABLE       | CHAR(1)       | Country code associated with the client’s identification document. |
    | ID_NO_SERIAL             | NULLABLE       | CHAR(12)      | Serial number of the identification document.                      |
    | ID_NO_STATUS             | NULLABLE       | CHAR(1)       | Status of the identification document.                             |
    | ID_NO_COUNT              | NULLABLE       | CHAR(2)       | Number of identification documents associated with the client.     |
    | PROVINCE_CODE            | NULLABLE       | CHAR(2)       | Code representing the province of residence.                       |
    | DISTRICT_CODE            | NULLABLE       | CHAR(2)       | Code representing the district of residence.                       |
    | SECTOR_CODE              | NULLABLE       | CHAR(3)       | Code representing the sector of residence.                         |
    | CELL_CODE                | NULLABLE       | CHAR(5)       | Code representing the cell of residence.                           |
    | VILLAGE_CODE             | NULLABLE       | CHAR(6)       | Code representing the village of residence.                        |
    | MOBILE_NO                | NULLABLE       | NUMBER(10)    | Primary mobile phone number of the client.                         |
    | MOBILE_NO1               | NULLABLE       | NUMBER(10)    | Secondary mobile phone number.                                     |
    | MOBILE_NO2               | NULLABLE       | NUMBER(10)    | Additional mobile phone number.                                    |
    | CORPORATE_CODE           | NULLABLE       | CHAR(7)       | Code identifying the client’s corporate affiliation.               |
    | GROUP_TARRIF             | NULLABLE       | CHAR(7)       | Group tariff classification.                                       |
    | DOLA                     | NOT NULL       | DATE          | Date of the last activity related to the client’s record.          |
    | NATIONALITY_FLAG         | NULLABLE       | CHAR(1)       | Flag indicating nationality status.                                |
    | NATIONALITY              | NULLABLE       | CHAR(15)      | Nationality of the client.                                         |
    | SAHAM_FLAG               | NULLABLE       | CHAR(1)       | Flag for Saham-related status.                                     |
    | SAHAM_CLIENT_NO          | NULLABLE       | NUMBER(10)    | Saham client number.                                               |
    | BNR_CLASSIFICATION       | NULLABLE       | CHAR(3)       | Classification code based on the National Bank of Rwanda (BNR).    |
    | CLIENT_TYPE              | NULLABLE       | CHAR(1)       | Type of client (e.g., Individual, Corporate).                      |
    | GENDER                   | NULLABLE       | CHAR(1)       | Gender of the client (e.g., M for Male, F for Female).             |
    | RESIDENT_COUNTRY         | NULLABLE       | CHAR(4)       | Country code of the client’s residence.                            |
    | ID_DOC                   | NULLABLE       | CHAR(1)       | Identification document type.                                      |
    | COUNTRY_CODE             | NULLABLE       | CHAR(4)       | Country code associated with the client’s record.                  |
    | SPOURSE_NAME             | NULLABLE       | CHAR(998)     | Name of the client’s spouse.                                       |
    | BIRTH_REG_VILLAGE        | NULLABLE       | CHAR(98)      | Village where the client’s birth was registered.                   |
    | RESIDENCE_TYPE           | NULLABLE       | CHAR(1)       | Type of residence.                                                 |
    | ECONOMIC_SUB_SECTOR      | NULLABLE       | CHAR(98)      | Economic sub-sector associated with the client.                    |
    | RELATION_TO_COMPANY_CODE | NULLABLE       | CHAR(98)      | Relation to a company (e.g., employee, shareholder).               |
    | CELLULE                  | NULLABLE       | CHAR(98)      | Cellule within the client’s residential area.                      |
    | VILLAGE                  | NULLABLE       | CHAR(98)      | Name of the client’s residential village.                          |
    | CONTACT                  | NULLABLE       | CHAR(45)      | Emergency or alternate contact name.                               |
    | CONTACT_POSITION         | NULLABLE       | CHAR(20)      | Position of the contact person (e.g., manager, family member).     |
    | CONTACT_TELEPHONE        | NULLABLE       | CHAR(25)      | Telephone number of the contact person.                            |
    | NAICS_CODE               | NULLABLE       | CHAR(58)      | NAICS[^1] (industry classification) code.                          |
    | ADDRESS3                 | NULLABLE       | CHAR(20)      | Additional address details (e.g., alternative address).            |
    | ADDRESS2                 | NULLABLE       | CHAR(20)      | Additional address details (e.g., suite number).                   |
    | FAX                      | NULLABLE       | CHAR(15)      | Fax number of the client.                                          |
    | DISTRICT                 | NULLABLE       | CHAR(98)      | District of residence.                                             |
    | PROVINCE                 | NULLABLE       | NUMBER(1)     | Province of residence.                                             |
    | SECTOR                   | NULLABLE       | CHAR(98)      | Sector of residence.                                               |
    | RESIDENT_COUNTRY_1       | NULLABLE       | CHAR(4)       | Alternate country of residence.                                    |
    | COUNTRY_CODE_1           | NULLABLE       | CHAR(4)       | Alternate country code.                                            |
    | CLEANED_FLAG             | NULLABLE       | CHAR(1)       | Indicates if the data has been cleaned (Y for Yes, N for No).      |
    | EDUCATION                | NULLABLE       | NUMBER(3)     | Highest level of education achieved.                               |
    | DEPENDANTS_NO            | NULLABLE       | NUMBER(2)     | Number of dependents the client has.                               |
    | RELATED_PARTY            | NULLABLE       | CHAR(6)       | Identifies a related party to the client.                          |
    | BENEFICIAL_OWNER         | NULLABLE       | CHAR(50)      | Name of the beneficial owner, if applicable.                       |
    | SOURCE_OF_INCOME         | NULLABLE       | NUMBER(2)     | Source of income (e.g., employment, business).                     |
    | VISION_SBU               | NULLABLE       | VARCHAR2(10)  | Vision Strategic Business Unit code.                               |
    | ACTIVE                   | NULL           | CHAR(1)       | Indicates whether the client is active (Y/N).                      |
    | CLEAN_D                  | NULL           | CHAR(1)       | Indicator for data cleaning.                                       |
    | CLEAN_ID                 | NULL           | CHAR(1)       | Identifier for cleaned records.                                    |
    | VALID_ID                 | NULL           | CHAR(1)       | Indicates if the ID is valid (Y/N).                                |
    | OCCUPATION_STATUS        | NULL           | NUMBER(3)     | Status code for the client's occupation.                           |
    | KFS_FLAG                 | NULL           | CHAR(1)       | Flag for KFS[^2] compliance (Y/N).                                 |
    | KFS_DATE                 | NULL           | DATE          | Date of KFS compliance or validation.                              |
    | REPUTATION_RISK_FACTOR   | NULL           | NUMBER(3)     | Risk factor rating based on reputation.                            |
    | EMP_ID                   | NULL           | VARCHAR2(20)  | Identifier for the employee within the system.                     |

    [^1]: NAICS (North American Industry Classification System): is a standard used to classify business establishments in the finance and insurance sector.
    [^2]: KFS (Key Facts Statement): is a document containing essential information about insurance product in a simple and easy-to-understand format.
