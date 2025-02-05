# Pending Transactions Table

## Table Description

??? quote "PENDING_TRANSACTIONS"

    | **Field Name**         | **Data Type** | **Constraint** | **Description**                                                         |
    |------------------------|---------------|----------------|-------------------------------------------------------------------------|
    | TRANSACTION_DATE       | DATE          | NOT NULL       | Date when the transaction is created                                    |
    | CURRENCY               | VARCHAR2(3)   | NOT NULL       | Three-letter currency code (e.g., USD, EUR, RWF)                        |
    | BENEFICIARY_NAME       | VARCHAR2(100) | NOT NULL       | Name of the payment recipient                                           |
    | BENEFICIARY_ACCOUNT    | VARCHAR2(20)  | NOT NULL       | Account number of the beneficiary                                       |
    | BENEFICIARY_BANK_NAME  | VARCHAR2(100) | NOT NULL       | Name of the beneficiary's bank                                          |
    | BENEFICIARY_BANK_SWIFT | VARCHAR2(11)  | NOT NULL       | SWIFT/BIC code of the beneficiary's bank                                |
    | BENEFICIARY_BANK_CODE  | VARCHAR2(10)  | NOT NULL       | Local bank code or routing number                                       |
    | AMOUNT                 | NUMBER(20,2)  | NOT NULL       | Transaction amount with 2 decimal places                                |
    | REFERENCE              | VARCHAR2(20)  | NOT NULL       | Unique reference number for the transaction                             |
    | REMARKS                | VARCHAR2(200) | NULL           | Additional notes or comments about the transaction                      |
    | IS_EXTERNAL            | CHAR(1)       | NOT NULL       | Flag indicating if transaction is external (`Y`/`N`)                    |
    | STATUS                 | VARCHAR2(10)  | NOT NULL       | Current status of the transaction (`PENDING`, `PROCESSED` Or `FAILED` ) |
    | PROCESSED_DATE         | DATE          | NULL           | Date when the transaction was processed                                 |
