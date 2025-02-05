# Batch Payment Request Table

## Table Description

??? quote "PAYREQSTMULTISUM"

    | **Field Name**  | **Data Type** | **Constraint** | **Description**                     |
    |-----------------|---------------|----------------|-------------------------------------|
    | REFERENCE_NO    | VARCHAR2(15)  |                | Transaction reference number        |
    | ACCOUNT_YEAR    | NUMBER(4)     |                | Fiscal/accounting year              |
    | ACCOUNT_MONTH   | NUMBER(2)     |                | Month of accounting period          |
    | SOURCE_CODE     | CHAR(3)       |                | Code identifying transaction source |
    | GROSS_AMOUNT    | NUMBER(20,2)  | NOT NULL       | Total amount before deductions      |
    | NETT_AMOUNT     | NUMBER(20,2)  | NOT NULL       | Final amount after deductions       |
    | STATUS_CODE     | CHAR(2)       |                | Code indicating transaction status  |
    | CREATED_BY      | CHAR(15)      |                | User ID of transaction creator      |
    | CREATE_DATE     | DATE          |                | Date when record was created        |
    | PAY_REFERENCE   | CHAR(10)      |                | Payment reference identifier        |
    | PAYMENT_DATE    | DATE          |                | Date when payment was made          |
    | NARRATION       | CHAR(200)     |                | Transaction description/notes       |
    | AMOUNT_IN_WORDS | CHAR(200)     |                | Amount spelled out in words         |
    | BANK_CODE       | CHAR(3)       |                | Bank identifier code                |
    | LEDGER_ACCOUNT  | CHAR(15)      |                | Account number in the ledger        |
    | PAY_METHOD      | CHAR(1)       |                | Payment method indicator            |
    | POST_YEAR       | NUMBER(4)     |                | Year when transaction was posted    |
    | POST_MONTH      | NUMBER(2)     |                | Month when transaction was posted   |
    | CHARGES         | NUMBER(10)    |                | Transaction fees or charges         |
    | REF_NO          | VARCHAR2(11)  |                | Alternative reference number        |
    | ECOBNK_TRANS    | CHAR(1)       |                | Ecobank transaction indicator       |

## Triggers

### Update Batch Payments Request Table

### Process GT Bank Payments

**<span class="text-light-blue">Purpose</span>**

Trigger `process_gtbank` processes GT Bank payment transactions when the status is updated to **`P`** in [payreqstmultisum] table. It handles both individual and group insurance policies, validates bank information, and creates pending transactions for payment processing.

**<span class="text-light-blue">Flow</span>**

1. Checks if status is updated to **`P`**
2. Validates bank account in GLBNKNAMES
3. Processes individual and group policies
4. Creates pending transaction records

**<span class="text-light-blue">Tables</span>**

1. [payreqstmultisum] source table for payment summaries
2. [olgldata.payreqstmulti][payreqstmulti] detailed payment records
3. GLBNKNAMES bank information
4. [olfsordata.lapol][lapol], [olfsordata.laclnt][laclnt] individual policy/client data
5. glclaims, membermaster, glclmast group policy data
6. [olgldata.pending_transactions][pending_transactions] target table for payment records

### Process Ecobank Payments

**<span class="text-light-blue">Purpose</span>**

Trigger `PROCESS_ECOBNK` is designed to handle bank payment processing for Ecobank transactions. It fires AFTER UPDATE on the [payreqstmultisum] table when payments are marked for Ecobank processing.

**<span class="text-light-blue">Flow</span>**

1. Triggers when a payment record is marked for Ecobank processing `ecobnk_trans = 'Y'`
2. Processes multiple payment requests under one reference number
3. Retrieves bank and beneficiary details
4. Handles two types of insurance policies:
    - Individual policies (starting with P[^1], F[^2], S[^3], R[^4])
    - Group policies (starting with 100[^5], 700[^6], 800[^7])
5. Creates payment records in ECOPAYMENTDET table for bank processing

**<span class="text-light-blue">Tables</span>**

1. [olgldata.payreqstmultisum][payreqstmultisum] source table for payment summaries
2. [olgldata.payreqstmulti][payreqstmulti] detailed payment records
3. GLBNKNAMES bank information
4. [olfsordata.lapol][lapol], [olfsordata.laclnt][laclnt], PROVINCES individual policy/client data
5. glclaims, membermaster, glclmast group policy data
6. [olgldata.pending_transactions][pending_transactions] target table for payment records
7. ECOPAYMENTDET bank payment details
8. PAYREQST payment requisitions  

<!-- tables -->
[payreqstmulti]: payreqstmulti.md
[payreqstmultisum]: #table-description
[pending_transactions]: pending_transactions.md#pending-transactions-table
[lapol]: ../../olfsordata/tables/lapol.md#table-description
[laclnt]: ../../olfsordata/tables/laclnt.md#table-description

[^1]: [Pension](../../../../topics/products.md#retirement-plan-40)
[^2]: [Funeral](../../../../topics/products.md#funeral-plan-20)
[^3]: [Safe Family](../../../../topics/products.md#safe-family-plan-10)
[^4]: [Education](../../../../topics/products.md#education-plan-30)
[^5]: [Group Life](../../../../topics/products.md)
[^6]: [Group Credit](../../../../topics/products.md)
[^7]: [Mortage](../../../../topics/products.md)
