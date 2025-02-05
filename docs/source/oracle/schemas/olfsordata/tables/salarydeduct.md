# Salary Deductions Table

The table is a central repository for managing insurance system salary and payment processing, storing transaction details, client data, authorization status, and administrative data, enabling effective monitoring and management of insurance payment workflows.

## Table Description

??? quote "SALARYDEDUCT"

    | **Field Name**          | **Data Type** | **Constraint** | **Description**                           |
    |-------------------------|---------------|----------------|-------------------------------------------|
    | SALARY_CODE             | CHAR(9)       |                | Unique salary identifier                  |
    | PAY_MODE                | CHAR(1)       |                | Payment mode indicator                    |
    | RECEIPT_DATE            | DATE          |                | Date of receipt                           |
    | INSURED_NAME            | CHAR(50)      |                | Name of the insured person                |
    | CONTRACTANT             | CHAR(50)      |                | Contract holder name                      |
    | AMOUNT                  | NUMBER(20,2)  |                | Transaction amount with 2 decimal places  |
    | INSTITUTION             | CHAR(7)       |                | Institution identifier                    |
    | UNIT_CODE               | NUMBER(3)     |                | Unit identification number                |
    | UNIT_NAME               | CHAR(50)      |                | Name of the unit                          |
    | AGENT_CODE              | NUMBER(5)     |                | Agent identification number               |
    | AGENT_NAME              | CHAR(50)      |                | Name of the agent                         |
    | TEAM_LEADER             | NUMBER(5)     |                | Agent's team leader identification number |
    | EFFECTIVE_MONTH         | NUMBER(2)     |                | Month when policy becomes effective       |
    | EFFECTIVE_YEAR          | NUMBER(4)     |                | Year when policy becomes effective        |
    | EFFECTIVE_DATE          | DATE          |                | Full date when policy becomes effective   |
    | NUM_OF_PROP             | NUMBER(4)     |                | Number of proposals                       |
    | PHONE_NO                | NUMBER(12)    |                | Contact phone number                      |
    | STATUS                  | NUMBER(3)     |                | Status indicator                          |
    | SAL_COMMENT             | CHAR(100)     |                | Salary-related comments                   |
    | LIST_PROVIDER           | NUMBER(3)     |                | Provider list identifier                  |
    | DEDUCT_FLAG             | CHAR(1)       |                | Deduction flag indicator                  |
    | CREATED_BY              | CHAR(15)      |                | User who created the record               |
    | CHANGED_BY              | CHAR(15)      |                | User who last modified the record         |
    | CREATION_DATE           | DATE          |                | Date record was created                   |
    | BANK_ACCOUNT            | CHAR(20)      |                | Bank account number                       |
    | COMMENTS                | CHAR(150)     |                | General comments                          |
    | NEW_MONTH               | NUMBER(2)     |                | Updated month value                       |
    | NEW_YEAR                | NUMBER(4)     |                | Updated year value                        |
    | PREV_AMOUNT             | NUMBER(20,2)  |                | Previous transaction amount               |
    | DEDUCT_STATUS           | CHAR(1)       |                | Deduction status indicator                |
    | AGENT_PORTAL_FLAG       | CHAR(1)       |                | Agent portal access flag                  |
    | DEDUCTION_CODE          | CHAR(23)      |                | Code for deduction                        |
    | REP_ID                  | NUMBER(10)    |                | Representative identifier                 |
    | REQ_ID                  | NUMBER(10)    |                | Requisition identifier                    |
    | AUTHORISED              | CHAR(1)       |                | Authorization status                      |
    | SURNAME                 | CHAR(100)     |                | Last name                                 |
    | OTHER_NAME              | CHAR(100)     |                | Other names                               |
    | IDENTITY_CARD_NO        | CHAR(16)      |                | ID card number                            |
    | MOBILE_NO               | CHAR(12)      |                | Mobile phone number                       |
    | BIRTH_DATE              | DATE          |                | Date of birth                             |
    | VILLAGE_ID              | CHAR(10)      |                | Village identifier                        |
    | GENDER                  | CHAR(1)       |                | Gender indicator                          |
    | ALLOCATED               | NUMBER(20,2)  |                | Allocated amount                          |
    | UNALLOCATED             | NUMBER(20,2)  |                | Unallocated amount                        |
    | CLIENT_NO               | CHAR(8)       |                | Client number                             |
    | SUSPENSE_CODE           | VARCHAR2(15)  |                | Suspense account code                     |
    | MARITAL_STATUS          | CHAR(1)       |                | Marital status indicator                  |
    | SPOUSE                  | CHAR(50)      |                | Spouse name                               |
    | AUTHORISED_DATE         | DATE          |                | Date of authorization                     |
    | PROCESSED_SUSPENSE_FLAG | VARCHAR2(1)   |                | Processed suspense indicator              |
    | AUTHORISED_BY           | CHAR(15)      |                | User who authorized                       |
    | INTEGRATION_DATE        | DATE          |                | Date of integration                       |
    | EMP_ID                  | VARCHAR2(20)  |                | Employee identifier                       |
    | LACLNT                  | VARCHAR2(20)  |                | Client identifier                         |
    | NEW_DEDUCTION_CODE      | CHAR(23)      |                | Updated deduction code                    |

## References

1. [Update deductions trigger](../../ext/tables/agent_report.md#update-deductions): insert data in the table from [ext.agent_report](../../ext/tables/agent_report.md) after a report has been approved
