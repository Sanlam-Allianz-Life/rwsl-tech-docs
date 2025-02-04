# Agent Report

Agent report table `AGENT_REPORT` stores information about reports submitted by insurance agents regarding clients. It includes details such as the report ID, the agent ID, client details, report submission date, and associated insurance policy details.

## Table Description

??? quote "AGENT_REPORT"

    | **Field Name**    | **Data Type**   | **Constraint** | **Description**                                              |
    |-------------------|-----------------|----------------|--------------------------------------------------------------|
    | ID                | NUMBER          | NOT NULL       | Unique identifier for the record                             |
    | REQUISITION_ID    | NUMBER          |                | Reference ID for requisition                                 |
    | CLIENT_NIDA       | NUMBER(20)      | NOT NULL       | National ID number of the client                             |
    | CLIENT_NAME       | CHAR(100)       |                | First name of the client                                     |
    | CLIENT_SURNAME    | CHAR(100)       |                | Last name of the client                                      |
    | NEWCLIENT_FLAG    | NUMBER(5)       |                | Indicator for new client status                              |
    | INST_PAY_MODE     | VARCHAR2(20)    |                | Premium payment mode (e.g: Standing Order, Salary Deduction) |
    | PREMIUM           | NUMBER          |                | Premium amount                                               |
    | EFFECTIVE_DATE    | DATE            |                | Policy premium effective date                                |
    | PHONE_NUM         | NUMBER          |                | Client's phone number                                        |
    | LOCATION          | VARCHAR2(100)   | NOT NULL       | Physical location                                            |
    | MNG_APPROVAL      | NUMBER(5)       |                | Manager approval status                                      |
    | MNG_NAME          | VARCHAR2(150)   |                | Name of the approving manager                                |
    | MNG_APPROV_DATE   | TIMESTAMP(6)    |                | Date and time of manager approval                            |
    | NOW_COMMENT       | VARCHAR2(150)   |                | Current comments or notes                                    |
    | REPORTED_DATE     | TIMESTAMP(6)    |                | Date and time when record was reported                       |
    | AGENT             | NUMBER          |                | Agent code                                                   |
    | CLIENT_BIRTH_DATE | DATE            |                | Client's date of birth                                       |
    | EDIT_FLAG         | NUMBER(3)       |                | Flag indicating if record has been edited                    |
    | REMOVED_FLAG      | NUMBER(3)       |                | Flag indicating if record has been removed                   |
    | REMOVED_BY        | VARCHAR2(150)   |                | User who removed the record                                  |
    | REMOVED_DATE      | TIMESTAMP(6)    |                | Date and time of removal                                     |
    | EDITED_BY         | VARCHAR2(150)   |                | User who last edited the record                              |
    | EDITED_DATE       | TIMESTAMP(6)    |                | Date and time of last edit                                   |
    | MNG_REACTED       | VARCHAR2(150)   |                | Manager's reaction or response                               |
    | PAYPOINT          | VARCHAR2(50)    |                | Payment point code                                           |
    | REC_APPROVAL      | NUMBER(3)       |                | Record approval status                                       |
    | REC_APPROV_DATE   | TIMESTAMP(6)    |                | Date and time of record approval                             |
    | REC_REACTED       | VARCHAR2(200)   |                | Record reaction or response                                  |
    | ZONE              | VARCHAR2(50)    |                | Agent zone                                                   |
    | MAX_TRANSPORT     | NUMBER(38)      |                | Maximum transport value                                      |
    | EmployeeId        | NVARCHAR2(2000) |                | Employee identifier (Unicode)                                |
    | EMP_ID            | VARCHAR2(20)    |                | Employee ID in standard format                               |

## Triggers

### Update Deductions

**<span class="text-light-blue">Purpose</span>**

`UPDATE_DEDUCTIONS_WITHOUT_REQ` Manages trigger manages salary deductions for agent reports by automatically creating or updating deduction records when an agent report is approved.

**<span class="text-light-blue">Flow</span>**

1. Triggers when `MNG_APPROVAL` is updated to **`1`** (approved) on [agent_report](#table-description)
2. Determines payment mode (Salary deduction or Standing order)
3. Checks if deduction record exists
4. If no record exists:
    - Generates new salary code
    - Creates new deduction record
    - Updates serial number
5. If record exists, updates existing deduction amount

**<span class="text-light-blue">Tables</span>**

1. [agent_report](#table-description): source table, trigger fires on updates to this table
2. [olfsordata.salarydeduct](../../olfsordata/tables/salarydeduct.md#table-description): target table where deduction records are stored
3. [olfsordata.salserials](../../olfsordata/tables/salserials.md#table-description): supporting table to manage serial numbers for salary code generation
