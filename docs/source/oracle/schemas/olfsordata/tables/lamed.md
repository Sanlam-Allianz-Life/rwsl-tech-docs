# Medicals Table

## Table Description

??? quote "LAMED"

    | Field Name        | Data Type    | Constraint | Description                           |
    |-------------------|--------------|------------|---------------------------------------|
    | PROPOSAL_NO       | CHAR(9)      | NOT NULL   | Unique proposal identification number |
    | CHEQUE_DATE       | DATE         |            | Date of cheque transaction            |
    | MEDICAL_CODE      | CHAR(1)      |            | Medical examination code identifier   |
    | MEDICAL_RESULTS   | CHAR(1)      |            | Results of medical examination        |
    | GRAND_RESULTS     | CHAR(1)      |            | Overall assessment results            |
    | FEES_PAID         | CHAR(1)      |            | Indicator for fee payment status      |
    | MED_FEES_DUE      | NUMBER(8,2)  |            | Medical fees pending payment          |
    | USER_ID           | CHAR(4)      |            | User identifier                       |
    | CREATION_DATE     | DATE         |            | Record creation date                  |
    | CREATION_ID       | CHAR(4)      |            | ID of user who created the record     |
    | BRANCH            | NUMBER(3)    |            | Branch office code                    |
    | TYPE              | NUMBER(2)    |            | Type of proposal/policy               |
    | AGENT             | NUMBER(5)    |            | Agent identification number           |
    | EXAMINATION_DATE  | DATE         |            | Date of medical examination           |
    | REMARK_CODE       | CHAR(2)      |            | Code for additional remarks           |
    | SUM_ASSURED       | NUMBER(13,2) |            | Total insured amount                  |
    | BALANCE           | NUMBER(13,2) |            | Remaining balance amount              |
    | BANK_NO           | CHAR(6)      |            | Bank identification number            |
    | CHEQUE_NO         | CHAR(20)     |            | Cheque number                         |
    | MED_FEES_PAID     | NUMBER(13,2) |            | Medical fees already paid             |
    | PAYMENT_DATE      | DATE         |            | Date of payment                       |
    | PREV_SUM_ASSURED  | NUMBER(13,2) |            | Previous sum assured amount           |
    | JOINT_FLAG        | CHAR(1)      |            | Indicator for joint policy            |
    | PARTNER           | CHAR(1)      |            | Partner indicator                     |
    | INVOICE_NO        | CHAR(10)     |            | Invoice number                        |
    | INVOICE_DATE      | DATE         |            | Date of invoice                       |
    | ACCESS_AGE        | NUMBER(2)    |            | Age for policy access                 |
    | REQUEST_DATE      | DATE         |            | Date of request                       |
    | OFFCD             | CHAR(3)      |            | Office code                           |
    | GL_UPDATE         | CHAR(1)      |            | General ledger update flag            |
    | CLIENT_NO         | CHAR(8)      |            | Client identification number          |
    | ACCOUNT_YEAR      | NUMBER(4)    |            | Fiscal/Account year                   |
    | ACCOUNT_MONTH     | NUMBER(2)    |            | Month of accounting                   |
    | BASIC_PREM        | NUMBER(13,2) |            | Basic premium amount                  |
    | PAYMENT_FLAG      | CHAR(1)      |            | Payment status indicator              |
    | GLHEAD            | CHAR(8)      |            | General ledger head code              |
    | SCHED             | CHAR(1)      |            | Schedule indicator                    |
    | OLD_POLICY_TYPE   | CHAR(1)      |            | Type of old policy                    |
    | OLD_POLICY_SERIAL | NUMBER(10)   |            | Serial number of old policy           |
    | OLD_POLICY_FLAG   | CHAR(1)      |            | Old policy status flag                |
