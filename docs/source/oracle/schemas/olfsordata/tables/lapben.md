# Beneficiary Details Table

LAPBEN serves as a comprehensive repository for managing insurance policy beneficiary information, relationships to policy holders, storing essential details such as proposal numbers, policy numbers, and personal information of beneficiaries

## Table Description

??? quote "LAPBEN"

    | Field Name        | Data Type    | Constraint | Description                              |
    |-------------------|--------------|------------|------------------------------------------|
    | PROPOSAL_NO       | NUMBER(9)    | NOT NULL   | Unique proposal identification number    |
    | POLICY_NO         | CHAR(9)      | NOT NULL   | Insurance policy number                  |
    | NO                | CHAR(2)      | NOT NULL   | Beneficiary sequence number              |
    | SURNAME           | CHAR(100)    | NOT NULL   | Beneficiary's last name                  |
    | OTHER_NAMES       | CHAR(100)    | NULLABLE   | Beneficiary's other names/first name     |
    | TITLE             | CHAR(4)      | NULLABLE   | Beneficiary's title (Mr., Mrs., etc.)    |
    | DOB               | DATE         | NULLABLE   | Beneficiary's date of birth              |
    | RELATION          | CHAR(2)      | NULLABLE   | Relationship code with the policy holder |
    | PERC              | NUMBER(13,2) | NULLABLE   | Percentage allocation of benefits        |
    | IDENTITY          | CHAR(9)      | NULLABLE   | Beneficiary's identification number      |
    | CLIENT_NO         | CHAR(8)      | NULLABLE   | Client reference number                  |
    | BENE_TYPE         | NUMBER(2)    | NULLABLE   | Type of beneficiary                      |
    | CORP_BENEFICIARY  | CHAR(100)    | NULLABLE   | Corporate beneficiary name if applicable |
    | OLD_POLICY_TYPE   | CHAR(1)      | NULLABLE   | Type code for old policy                 |
    | OLD_POLICY_SERIAL | NUMBER(10)   | NULLABLE   | Serial number of old policy              |
    | OLD_POLICY_FLAG   | CHAR(1)      | NULLABLE   | Flag indicating old policy status        |
    | ENDORSE_YEAR      | NUMBER(4)    | NULLABLE   | Year of endorsement                      |
    | ENDORSE_SERIAL    | NUMBER(4)    | NULLABLE   | Serial number of endorsement             |
    | STATUS_CODE       | NUMBER(1)    | NULLABLE   | Status code of the beneficiary record    |
    | USER_STR          | CHAR(3)      | NULLABLE   | User identification string               |
    | SAHAM_FLAG        | CHAR(1)      | NULLABLE   | Flag for Saham insurance records         |
    | SAHAM_POLICY_NO   | CHAR(20)     | NULLABLE   | Saham insurance policy number            |
    | SAHAM_CLIENT_NO   | NUMBER(10)   | NULLABLE   | Saham client identification number       |
