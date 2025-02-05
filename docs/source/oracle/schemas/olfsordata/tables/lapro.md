# Policy Proposal Info Table

This table store policy proposal data. It encompasses a wide range of attributes, including details about premiums, coverage sums, personal information of policyholders and their partners, financial terms, and administrative flags.
The fields cover various aspects such as premium amounts for different coverages, sum assured values, personal details like age and smoking status, financial terms such as interest rates and payment periods, and administrative flags and codes for tracking and managing the proposals.

## Table Description

??? quote "LAPRO"

    | **Field Name**          | **Data Type** | **Constraint** | **Description**                                                       |
    |-------------------------|---------------|----------------|-----------------------------------------------------------------------|
    | DAB                     | CHAR(1)       |                | Code indicating a specific type of benefit or coverage.               |
    | DAB_FEMALE_PREMIUM      | NUMBER(10,2)  |                | Premium amount for female coverage under DAB.                         |
    | DAB_MALE_PREMIUM        | NUMBER(10,2)  |                | Premium amount for male coverage under DAB.                           |
    | WP                      | CHAR(1)       |                | Code indicating another type of coverage or plan.                     |
    | WP_FEMALE_PREMIUM       | NUMBER(10,2)  |                | Premium for female coverage under WP.                                 |
    | WP_MALE_PREMIUM         | NUMBER(10,2)  |                | Premium for male coverage under WP.                                   |
    | ISB                     | CHAR(1)       |                | Code indicating another coverage type.                                |
    | ISB_FEMALE_PREMIUM      | NUMBER(10,2)  |                | Premium for female coverage under ISB.                                |
    | ISB_MALE_PREMIUM        | NUMBER(10,2)  |                | Premium for male coverage under ISB.                                  |
    | ISB_SUM_ASSURED         | NUMBER(10,2)  |                | Sum assured for ISB coverage.                                         |
    | MALE_SMOKER             | CHAR(1)       |                | Indicates if the male policyholder is a smoker.                       |
    | FEMALE_SMOKER           | CHAR(1)       |                | Indicates if the female policyholder is a smoker.                     |
    | JOINT_SMOKER            | CHAR(1)       |                | Indicates if joint policyholders are smokers.                         |
    | ACCESS_AGE              | NUMBER(2)     |                | Age at which access to coverage is granted.                           |
    | AGE                     | NUMBER(2)     |                | Age of the policyholder.                                              |
    | JOINT_AGE               | NUMBER(2)     |                | Age of the joint policyholder.                                        |
    | RATE_TYPE               | CHAR(1)       |                | Type of rate applied, e.g., standard or preferred.                    |
    | CIC_TOTAL_PREMIUM       | NUMBER(13,2)  |                | Total premium for CIC coverage.                                       |
    | BASIC_PREMIUM           | NUMBER(13,2)  |                | Base premium without additional riders or benefits.                   |
    | WP_PREMIUM              | NUMBER(10,2)  |                | Premium for WP coverage.                                              |
    | DAB_PREMIUM             | NUMBER(10,2)  |                | Premium for DAB coverage.                                             |
    | ISB_PREMIUM             | NUMBER(10,2)  |                | Premium for ISB coverage.                                             |
    | CIC_2ND_LIFE            | CHAR(1)       |                | Indicates second life coverage under CIC.                             |
    | LTB_2ND_LIFE            | CHAR(1)       |                | Indicates second life coverage under LTB.                             |
    | ISB_2ND_LIFE            | CHAR(1)       |                | Indicates second life coverage under ISB.                             |
    | DAB_2ND_LIFE            | CHAR(1)       |                | Indicates second life coverage under DAB.                             |
    | WP_2ND_LIFE             | CHAR(1)       |                | Indicates second life coverage under WP.                              |
    | PARTNERS_AGE            | NUMBER(2)     |                | Age of the partner or spouse.                                         |
    | LTB_PREMIUM             | NUMBER(13,2)  |                | Premium for LTB coverage.                                             |
    | INTEREST_RATE           | NUMBER(5,2)   |                | Interest rate applicable to the policy.                               |
    | PAY_PERIOD              | NUMBER(2)     |                | Payment period for premiums, e.g., monthly, annually.                 |
    | MORTGAGE_PROTECTION     | CHAR(1)       |                | Indicates if mortgage protection is included.                         |
    | PARTNERS_DOB            | DATE          |                | Date of birth of the partner or spouse.                               |
    | PARTNERS_NO             | CHAR(8)       |                | Partner's identification number.                                      |
    | LEB                     | CHAR(1)       |                | Code indicating another coverage type.                                |
    | LEB_PREMIUM             | NUMBER(10,2)  |                | Premium for LEB coverage.                                             |
    | NONSMOKING_DISC         | NUMBER(10,2)  |                | Discount for non-smokers.                                             |
    | MATURITY_AGE            | NUMBER(2)     |                | Age at which the policy matures.                                      |
    | VESTING_AGE             | NUMBER(2)     |                | Age at which the policy vests.                                        |
    | LEB_SUM_ASSURED         | NUMBER(13,2)  |                | Sum assured for LEB coverage.                                         |
    | DAB_SUM_ASSURED         | NUMBER(13,2)  |                | Sum assured for DAB coverage.                                         |
    | CURRENCY_CODE           | CHAR(3)       |                | Currency used for transactions, e.g., USD, EUR.                       |
    | ALOAD                   | NUMBER(2)     |                | Additional load or charges applied.                                   |
    | EMR                     | NUMBER(8,2)   |                | Estimated monthly revenue or another financial metric.                |
    | SA_DISCOUNT             | NUMBER(13,2)  |                | Discount on sum assured.                                              |
    | OCCUP                   | NUMBER(8,2)   |                | Occupation code categorizing the policyholder's occupation.           |
    | OFFCD                   | CHAR(3)       |                | Office code identifying the office or branch.                         |
    | QUOTED                  | CHAR(1)       |                | Indicates whether a quotation has been provided.                      |
    | QUOTATION_NO            | NUMBER(9)     |                | Number assigned to the quotation.                                     |
    | EXTRA_PREMIUM           | NUMBER(13,2)  |                | Additional premium amounts beyond the basic premium.                  |
    | SCHEME_NO               | CHAR(9)       |                | Scheme number for the policy.                                         |
    | SCHEME_CLIENT           | CHAR(8)       |                | Client identifier for the scheme.                                     |
    | FROM_GROUP              | CHAR(1)       |                | Indicates if the policy is from a group plan.                         |
    | MED_EXEMPTION           | CHAR(1)       |                | Indicates medical exemption status.                                   |
    | BENEFICIARY_CREATED     | CHAR(1)       |                | Indicates whether a beneficiary has been assigned.                    |
    | SETUP_YEAR              | NUMBER(1)     |                | Year the policy was set up.                                           |
    | GUARDIAN                | CHAR(24)      |                | Name or identifier of the policyholder's guardian.                    |
    | PPA                     | CHAR(1)       |                | Code indicating another coverage or plan.                             |
    | PPA_PREMIUM             | NUMBER(13,2)  |                | Premium for PPA coverage.                                             |
    | PPA_SUM_ASSURED         | NUMBER(13,2)  |                | Sum assured for PPA coverage.                                         |
    | FIB                     | CHAR(1)       |                | Code indicating another coverage or plan.                             |
    | FIB_TERM                | NUMBER(2)     |                | Term length for FIB coverage.                                         |
    | FIB_PREMIUM             | NUMBER(13,2)  |                | Premium for FIB coverage.                                             |
    | FIB_SUM_ASSURED         | NUMBER(13,2)  |                | Sum assured for FIB coverage.                                         |
    | MED_REQUIRED            | CHAR(1)       |                | Indicates whether medical examination is required.                    |
    | PARTNERS_NAMES          | CHAR(20)      |                | Name of the partner or spouse.                                        |
    | PARTNERS_SEX            | CHAR(1)       |                | Gender of the partner or spouse.                                      |
    | RIDER_CODE              | CHAR(2)       |                | Code for riders attached to the policy.                               |
    | RIDER_TERM              | NUMBER(2)     |                | Term length for the rider.                                            |
    | RIDER_SUM_ASSURED       | NUMBER(15,2)  |                | Sum assured for the rider.                                            |
    | RIDER_PREMIUM           | NUMBER(15,2)  |                | Premium for the rider.                                                |
    | RIDER                   | CHAR(1)       |                | Indicates the presence of a rider.                                    |
    | DEPOSIT                 | CHAR(1)       |                | Indicates whether a deposit has been made.                            |
    | PROP_ON                 | CHAR(1)       |                | Property-related flag or code.                                        |
    | UNIT_LINKED             | CHAR(1)       |                | Indicates if the policy is unit-linked.                               |
    | ULF_CODE                | CHAR(3)       |                | Unit-linked fund code.                                                |
    | UL_INV_AMT              | NUMBER(15,2)  |                | Investment amount for unit-linked policies.                           |
    | UL_LIFE_PREM            | NUMBER(15,2)  |                | Life premium for unit-linked policies.                                |
    | UL_TYPE                 | NUMBER(2)     |                | Type of unit-linked policy.                                           |
    | LIFE_UNITS              | NUMBER(2)     |                | Units for life coverage in unit-linked policies.                      |
    | MEDICALS                | CHAR(1)       |                | Indicates whether medical information is required or available.       |
    | LIEN_OPTION             | CHAR(1)       |                | Indicates the lien option chosen.                                     |
    | TERMINAL_ILLNESS        | CHAR(1)       |                | Indicates coverage or status related to terminal illness.             |
    | PREMIUM_ESCALATOR       | CHAR(1)       |                | Indicates whether premium escalator is applied.                       |
    | ESCALATOR_RATE          | NUMBER(8,2)   |                | Rate at which premiums escalate.                                      |
    | MED_FEES_DUE            | NUMBER(10,2)  |                | Medical fees that are due.                                            |
    | DATE_PROP_RECVD         | DATE          |                | Date when proof of property was received.                             |
    | PENSION_INT_RATE        | NUMBER(13,9)  |                | Interest rate for pension-related benefits.                           |
    | VALUE_ACQUIRED          | NUMBER(13,2)  |                | Value acquired under the policy.                                      |
    | AGE_F                   | NUMBER(2)     |                | Age factor or flag related to age calculations.                       |
    | JOINT_AGE_F             | NUMBER(2)     |                | Joint age factor or flag.                                             |
    | INTEREST_TYPE           | CHAR(1)       |                | Type of interest applied, e.g., fixed, variable.                      |
    | STAFF_YN                | CHAR(1)       |                | Indicates whether the policyholder is staff (yes/no).                 |
    | MEDREQ_PRINTED_YN       | CHAR(1)       |                | Indicates whether medical request was printed (yes/no).               |
    | MEDREQ_PRINTED_BY       | CHAR(8)       |                | Identifier of who printed the medical request.                        |
    | MEDREQ_PRINTED_ON       | DATE          |                | Date when the medical request was printed.                            |
    | EMPLOYEE_NO             | CHAR(15)      |                | Employee number for staff members.                                    |
    | AGE_FACTOR              | NUMBER(2)     |                | Factor related to age, possibly for calculating premiums or benefits. |
    | DEATH_GUARANTEE_YN      | CHAR(1)       |                | Indicates death guarantee coverage (yes/no).                          |
    | DEATH_GUARANTEE_PRD     | NUMBER(2)     |                | Period of death guarantee coverage.                                   |
    | PREM_AFTER_COMM         | NUMBER(13,2)  |                | Premium after commission deductions.                                  |
    | MATURITY_INSTALL_AMT    | NUMBER(13,2)  |                | Maturity installment amount.                                          |
    | EDU_INT_LUMPSUM_PER     | NUMBER(8,2)   |                | Educational lump sum per period.                                      |
    | UW_YEAR                 | NUMBER(4)     |                | Underwriting year.                                                    |
    | EMPLOYER_CODE           | CHAR(5)       |                | Code identifying the employer.                                        |
    | ESC_FREQ                | NUMBER(1)     |                | Escalation frequency.                                                 |
    | USER_NO                 | NUMBER(2)     |                | User number for tracking purposes.                                    |
    | VALUE_ACQUIRED_3YRS     | NUMBER(15,2)  |                | Value acquired over three years.                                      |
    | MATURITY_VALUE_ACQUIRED | NUMBER(13,2)  |                | Maturity value acquired.                                              |
    | SPONSOR_NO              | CHAR(8)       |                | Sponsor number.                                                       |
    | GUARANTEE_DEATH_PRD     | NUMBER(3)     |                | Guarantee period for death benefits.                                  |
    | FREQ_INSTALL            | CHAR(1)       |                | Frequency of installments.                                            |
    | ADMIN_CHARGE            | NUMBER(15,2)  |                | Administrative charges.                                               |
    | LOAD_AMOUNT             | NUMBER(15,2)  |                | Load or additional charges amount.                                    |
    | DEATH_PREMIUM           | NUMBER(15,2)  |                | Premium related to death benefits.                                    |
    | COMM_FLAG               | CHAR(1)       |                | Commission flag.                                                      |
    | USER_STR                | CHAR(14)      |                | User string or identifier.                                            |
    | FREE_CONTRIBUTION       | CHAR(1)       |                | Indicates free contribution status.                                   |
    | SPONSOR_TYPE            | CHAR(1)       |                | Type of sponsor.                                                      |
    | MAX_FREE_COVER          | NUMBER(20,2)  |                | Maximum free coverage amount.                                         |
    | MEMBERS                 | NUMBER(2)     |                | Number of members covered under the policy.                           |
    | RISK_SUM_MAIN           | NUMBER(20,2)  |                | Main risk sum assured.                                                |
    | MEMBERS_SUM_ASSURED     | NUMBER(20,2)  |                | Sum assured for members.                                              |
    | CORPORATE_CODE          | CHAR(7)       | NOT NULL       | Corporate code, likely unique and mandatory.                          |
    | SUPERVISOR_NO           | NUMBER(6)     |                | Supervisor number.                                                    |
    | MANAGER_CODE            | NUMBER(5)     |                | Manager code.                                                         |
    | IVALUE                  | NUMBER(20,9)  |                | Value related to insurance, need to confirm.                          |
    | OVP_NO                  | NUMBER(10)    |                | Overpayment number or another identifier.                             |
    | ITEM_NO                 | NUMBER(2)     |                | Item number for tracking specific items or components of the policy.  |
    | PEN_ADMIN_CHARGE        | NUMBER(10,3)  |                | Administrative charges for pension benefits.                          |
    | EDU_ADMIN_CHARGE        | NUMBER(10,4)  |                | Administrative charges for education benefits.                        |
    | INT_RATE                | NUMBER(10,2)  |                | Interest rate for investments or loans related to the policy.         |
    | NEW_TARRIF              | CHAR(1)       |                | Indicates a new tariff or rate structure.                             |
    | GROUP_TARRIF            | CHAR(7)       |                | Group tariff code.                                                    |
    | PRODUCT_CODE            | NUMBER(4)     |                | Code identifying the product or policy type.                          |
    | PLAN_CODE               | CHAR(5)       |                | Code for the specific plan within the product.                        |
    | MODIFIED_BY             | CHAR(10)      |                | Who modified the record.                                              |
    | MODIFIED_DATE           | DATE          |                | When the record was modified.                                         |
    | FAB                     | CHAR(1)       |                | Code indicating another coverage or plan.                             |
    | FAB_SUM_ASSURED         | NUMBER(13,2)  |                | Sum assured for FAB coverage.                                         |
    | FAB_PREMIUM             | NUMBER(13,2)  |                | Premium for FAB coverage.                                             |
    | PPD                     | CHAR(1)       |                | Code indicating another coverage or plan.                             |
    | PPD_SUM_ASSURED         | NUMBER(13,2)  |                | Sum assured for PPD coverage.                                         |
    | PPD_PREMIUM             | NUMBER(13,2)  |                | Premium for PPD coverage.                                             |
    | REV                     | CHAR(1)       |                | Code indicating another coverage or plan.                             |
    | REV_SUM_ASSURED         | NUMBER(13,2)  |                | Sum assured for REV coverage.                                         |
    | REV_PREMIUM             | NUMBER(13,2)  |                | Premium for REV coverage.                                             |
    | CRT                     | CHAR(1)       |                | Code indicating another coverage or plan.                             |
    | CRT_SUM_ASSURED         | NUMBER(13,2)  |                | Sum assured for CRT coverage.                                         |
    | CRT_PREMIUM             | NUMBER(13,2)  |                | Premium for CRT coverage.                                             |
    | TPD                     | CHAR(1)       |                | Code indicating another coverage or plan.                             |
    | TPD_SUM_ASSURED         | NUMBER(13,2)  |                | Sum assured for TPD coverage.                                         |
    | TPD_PREMIUM             | NUMBER(13,2)  |                | Premium for TPD coverage.                                             |
    | SUB_GROUP               | CHAR(3)       |                | Sub-group identifier within a larger group.                           |
    | ACCOUNT_YEAR            | NUMBER(4)     |                | Fiscal year for accounting purposes.                                  |
    | ACCOUNT_MONTH           | NUMBER(2)     |                | Fiscal month for accounting purposes.                                 |
    | SALARY_CODE             | CHAR(9)       |                | Code related to salary or income classification.                      |
    | P_POLICY_NO             | CHAR(9)       |                | Policy number for the partner or spouse.                              |
    | USER_NAME               | CHAR(20)      |                | Username for system access.                                           |
    | SAHAM_FLAG              | CHAR(1)       |                | Indicates SAHAM-related status.                                       |
    | SAHAM_CLIENT_NO         | NUMBER(10)    |                | SAHAM client number.                                                  |
    | SAHAM_AGENT_NO          | CHAR(5)       |                | SAHAM agent number.                                                   |
    | SAHAM_PROPOSAL_NO       | CHAR(20)      |                | SAHAM proposal number.                                                |
    | NON_INSURANCE_PREM      | NUMBER(20,2)  |                | Premiums not related to insurance, possibly for additional services.  |
    | ACQUISITION_COST        | NUMBER(20,2)  |                | Cost of acquiring the policy.                                         |
    | PREMIUM_REVIEW_DATE     | DATE          |                | Date when premium was last reviewed.                                  |
    | CO_INSURE               | CHAR(1)       |                | Indicates co-insurance status.                                        |
    | COMPANY_SHARE           | NUMBER(10,4)  |                | The company's share in the policy or arrangement.                     |
    | TYPE_OF_BUS             | NUMBER(2)     |                | Type of business, categorizing the policyholder's business.           |
    | CASH_BENEFIT            | CHAR(1)       |                | Indicates cash benefit options.                                       |
    | DEDUCTION_CODE          | CHAR(23)      |                | Code for allowable deductions.                                        |
    | SUSPENSE_CODE           | CHAR(8)       |                | Code for suspense or hold status on the policy.                       |
