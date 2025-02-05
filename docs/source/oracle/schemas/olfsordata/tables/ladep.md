# Dependents Details Table

The Dependents table serves as a comprehensive repository for managing and tracking all insured dependents' information within insurance policies, storing essential details such as personal information, relationship to the primary policy holder, and specific coverage arrangements.

## Table Description

??? quote "LADEP"

    | **Field Name**  | **Data Type** | **Constraint** | **Description**                                   |
    |-----------------|---------------|----------------|---------------------------------------------------|
    | PLAN            | CHAR(2)       |                | Insurance plan identifier                         |
    | PROPOSAL_NO     | NUMBER(9)     |                | Unique proposal identification number             |
    | PROPOSAL_NUMBER | CHAR(9)       |                | Formatted proposal reference number               |
    | POLICY_NO       | CHAR(9)       |                | Insurance policy number                           |
    | AGE             | NUMBER(2)     |                | Age of the dependant/primary person               |
    | RELATION        | CHAR(2)       |                | Relationship code with primary insured            |
    | SURNAME         | CHAR(15)      |                | Last name of the dependant/primary person         |
    | OTHER_NAMES     | CHAR(25)      |                | First and middle dependant/primary of the insured |
    | SEX             | CHAR(1)       |                | Gender indicator                                  |
    | MIN_ASSURED     | NUMBER(13)    |                | Minimum assured amount                            |
    | ANNUAL_PREM     | NUMBER(13,2)  |                | Annual premium amount                             |
    | DOB             | DATE          |                | Date of birth                                     |
    | STATUS_CODE     | CHAR(2)       |                | Status of the policy/proposal                     |
    | DEP_NO          | NUMBER(2)     |                | Dependent number                                  |
    | CLIENT_NO       | CHAR(8)       |                | Unique client identifier (primary person)         |
    | PAY_MODE        | CHAR(1)       |                | Payment mode indicator                            |
    | PAY_PERIOD      | NUMBER(2)     |                | Payment period in months/years                    |
    | TERM            | NUMBER(2)     |                | Policy term duration                              |
    | INTEREST_RATE   | NUMBER(5,2)   |                | Applicable interest rate                          |
    | CODE            | CHAR(1)       |                |                                                   |
    | MEMBERS         | NUMBER(2)     |                | Number of members covered                         |
    | WP              | CHAR(1)       |                | Waiver of premium indicator                       |
    | INSURED_FLAG    | CHAR(1)       |                | Insurance status flag                             |
    | RIDER_CODE      | CHAR(2)       |                | Additional rider identification code              |
    | CASH_BACK_PREM  | NUMBER(20,2)  |                | Cash back premium amount                          |
    | CASH_BACK_YN    | CHAR(1)       |                | Cash back eligibility indicator                   |
    | PROD_SUB_CODE   | CHAR(6)       |                | Product sub-category code                         |
    | SUB_PROD_CODE   | NUMBER(2)     |                | Sub-product identifier                            |
    | BEN_STATUS      | CHAR(1)       |                | Benefit status indicator                          |
    | PRODUCT_CODE    | NUMBER(4)     |                | Main product identifier                           |
    | CLAIM_PROCESSED | CHAR(1)       |                | Claim processing status                           |
    | PLAN_CODE       | CHAR(5)       |                | Detailed plan identification code                 |
    | NEW_SURNAME     | CHAR(50)      |                | Updated/new surname field                         |
    | TARRIF_PERIOD   | CHAR(6)       |                | Tariff period identifier                          |
