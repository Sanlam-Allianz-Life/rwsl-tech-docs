# Payment Request Table

## Table Description

??? quote "PAYREQSTMULTI"

    | **Field Name**      | **Data Type** | **Constraint** | **Description**                             |
    |---------------------|---------------|----------------|---------------------------------------------|
    | REFERENCE_NO        | CHAR(15)      |                | Reference number for the transaction        |
    | ACCOUNT_YEAR        | NUMBER(4)     |                | Fiscal or accounting year                   |
    | ACCOUNT_MONTH       | NUMBER(2)     |                | Month of the accounting period              |
    | SOURCE_CODE         | CHAR(3)       |                | Code indicating the transaction source      |
    | GROSS_AMOUNT        | NUMBER(20,2)  | NOT NULL       | Total amount before deductions              |
    | DEDUCT_ADDITION_AMT | NUMBER(20,2)  | NOT NULL       | Amount to be added or deducted              |
    | NETT_AMOUNT         | NUMBER(20,2)  | NOT NULL       | Final amount after all calculations         |
    | DOLA                | DATE          |                | Date of last action/update                  |
    | CREATE_DATE         | DATE          |                | Record creation date                        |
    | CREATED_BY          | CHAR(15)      |                | User ID who created the record              |
    | USER_STR            | CHAR(15)      |                | User string for additional user information |
    | STATUS_CODE         | CHAR(2)       |                | Current status of the record                |
    | PAY_REFERENCE       | CHAR(10)      |                | Payment reference identifier                |
    | REQ_NO              | CHAR(15)      |                | Request number                              |
    | BANK_CODE           | CHAR(3)       |                | Bank identifier code                        |
    | PAYEE_ACCOUNT_NO    | CHAR(50)      |                | Bank account number of the payee            |
    | BANK_NAME           | CHAR(100)     |                | Name of the bank                            |
    | PAYEE               | CHAR(100)     |                | Name of the payment recipient               |
    | ITEM_NO             | NUMBER(4)     |                | Sequential item number                      |
