# Policy Details Table

Lapol database table stores all details about converted and issued insurance policies

## Table Description

??? quote "LAPOL"

    | **Column Name**          | **Data Type** | **Constraints** | **Description**                                              |
    |--------------------------|---------------|-----------------|--------------------------------------------------------------|
    | POLICY_NO                | CHAR(9)       | NOT NULL        | Unique identifier for the insurance policy                   |
    | PROPOSAL_NO              | CHAR(9)       | -               | Reference number of the initial insurance proposal           |
    | PROPOSAL_DATE            | DATE          | -               | Date when the insurance proposal was submitted               |
    | RECEIPT_NO               | CHAR(6)       | -               | Premium payment receipt identifier                           |
    | BRANCH                   | NUMBER(3)     | -               | Branch office code where policy was issued                   |
    | ACCOUNT_TYPE             | NUMBER(2)     | -               | Type of insurance account                                    |
    | AGENT                    | NUMBER(5)     | -               | Unique identifier for the insurance agent                    |
    | CLIENT_NO                | CHAR(8)       | -               | Unique identifier for the policy holder                      |
    | ADB_EXTRA                | NUMBER(13,2)  | -               | Extra premium for Accidental Death Benefit                   |
    | PLAN                     | CHAR(2)       | -               | Insurance plan code                                          |
    | LTB_TERM                 | NUMBER(2)     | -               | Term period for Long Term Benefits                           |
    | PAY_METHOD               | CHAR(1)       | -               | Method of premium payment                                    |
    | PAY_MODE                 | CHAR(1)       | -               | Frequency of premium payments (monthly, quarterly, annually) |
    | PREMDUE_DATE             | DATE          | -               | Due date for next premium payment                            |
    | AMTPREM_DUE              | NUMBER(17,2)  | -               | Amount of premium due                                        |
    | DATE_LAST_PREM           | DATE          | -               | Date of last premium payment                                 |
    | UNDERWRITERS_CODE        | CHAR(3)       | -               | Code identifying the underwriter                             |
    | STATUS_CODE              | CHAR(2)       | -               | Current status of the policy                                 |
    | EFFECTIVE_DATE           | DATE          | -               | Date when policy coverage begins                             |
    | MATURITY_DATE            | DATE          | -               | Date when policy term ends                                   |
    | TERM_OF_POLICY           | NUMBER(2)     | -               | Duration of policy in years                                  |
    | LTB_SUM_ASSURED          | NUMBER(13,2)  | -               | Assured sum for Long Term Benefits                           |
    | ACCRUED_BONUS            | NUMBER(13,2)  | -               | Total accumulated bonus amount                               |
    | DATE_FIRST_PREM          | DATE          | -               | Date of first premium payment                                |
    | INTERIM_BONUS            | NUMBER(13,2)  | -               | Temporary bonus amount                                       |
    | ADB_SUM                  | NUMBER(13,2)  | -               | Sum assured for Accidental Death Benefit                     |
    | MIN_ASSURED              | NUMBER(13,2)  | -               | Minimum assured amount                                       |
    | UW_YEAR                  | NUMBER(4)     | -               | Underwriting year                                            |
    | SUB_CODE                 | CHAR(1)       | -               | Subsidiary code                                              |
    | DECREASE_SUM             | NUMBER(13,2)  | -               | Amount of decrease in sum assured                            |
    | BASIC_PREM               | NUMBER(13,2)  | -               | Base premium amount                                          |
    | LTB_PREMIUM              | NUMBER(13,2)  | -               | Premium for Long Term Benefits                               |
    | MODAL_PREM               | NUMBER(13,2)  | -               | Premium based on payment frequency                           |
    | ADB_PREM                 | NUMBER(13,2)  | -               | Premium for Accidental Death Benefit                         |
    | EXTRA_PREM               | NUMBER(13,2)  | -               | Additional premium charges                                   |
    | LTB_EXTRA_PREMIUM        | NUMBER(13,2)  | -               | Extra premium for Long Term Benefits                         |
    | WAIVER_PREM              | NUMBER(13,2)  | -               | Premium amount waived                                        |
    | POLICY_FEES              | NUMBER(13,2)  | -               | Administrative fees                                          |
    | RECEIVED                 | NUMBER(17,2)  | -               | Total amount received                                        |
    | PRE_ISSUED               | NUMBER(13,2)  | -               | Amount issued before policy start                            |
    | MAIN_SUSP                | NUMBER(13,2)  | -               | Main suspense amount                                         |
    | PAYMENT_SUSPENSE         | NUMBER(13,2)  | -               | Payments in suspense                                         |
    | ODD_LOT                  | NUMBER(10,2)  | -               | Odd amount adjustments                                       |
    | PREM_UNITS               | NUMBER(8)     | -               | Number of premium units                                      |
    | LIFE_COVER               | NUMBER(13,2)  | -               | Amount of life insurance coverage                            |
    | LIFECVR_TODATE           | NUMBER(13,2)  | -               | Life cover amount to date                                    |
    | WP_TODATE                | NUMBER(13,2)  | -               | Waiver of Premium amount to date                             |
    | ADB_TODATE               | NUMBER(13,2)  | -               | Accidental Death Benefit amount to date                      |
    | TAKEON_SUSPENSE          | NUMBER(13,2)  | -               | Suspense amount at policy takeover                           |
    | WP_EXTRA_PREM            | NUMBER(13,2)  | -               | Extra premium for Waiver of Premium                          |
    | INSTAL_TODATE            | NUMBER(13,2)  | -               | Installments paid to date                                    |
    | NONSMOKING_DISC          | NUMBER(13,2)  | -               | Discount for non-smoking status                              |
    | LTB_TODATE               | NUMBER(13,2)  | -               | Long Term Benefits amount to date                            |
    | COMM_PAYABLE             | NUMBER(17,2)  | -               | Commission amount payable                                    |
    | CLAIM_NOTIFY_DATE        | DATE          | -               | Date when claim was notified                                 |
    | REINSTATE_DATE           | DATE          | -               | Date of policy reinstatement                                 |
    | CANCELL_DATE             | DATE          | -               | Date of policy cancellation                                  |
    | PAIDUP_DATE              | DATE          | -               | Date when policy became paid-up                              |
    | PAIDUP_CHARGE            | NUMBER(13,2)  | -               | Charges for paid-up policy                                   |
    | LAPSE_DATE               | DATE          | -               | Date when policy lapsed                                      |
    | ISSUE_DATE               | DATE          | -               | Date when policy was issued                                  |
    | ALTERATION_DATE          | DATE          | -               | Date of last policy alteration                               |
    | LEB_SUM_ASSURED          | NUMBER(13,2)  | -               | Sum assured for Level Extra Benefits                         |
    | JOINT_LIFE               | CHAR(1)       | -               | Indicator if policy covers multiple lives                    |
    | LOAN_FLAG                | CHAR(1)       | -               | Indicator if policy has an active loan                       |
    | FINAL_ADD_BONUS          | NUMBER(13,2)  | -               | Final additional bonus amount                                |
    | EXPECTED_PREMIUMS        | NUMBER(13,2)  | -               | Expected premium payments                                    |
    | EXTRA_MATURITY_FEES      | NUMBER(13,2)  | -               | Additional fees at maturity                                  |
    | MODE_EXTRA               | NUMBER(13,2)  | -               | Extra charges based on payment mode                          |
    | AGE                      | NUMBER(2)     | -               | Age of primary insured person                                |
    | MATURITY_PENALTY         | NUMBER(13,2)  | -               | Penalty for early maturity                                   |
    | PAYMENT                  | NUMBER(13,2)  | -               | Payment amount                                               |
    | SURRENDER_DATE           | DATE          | -               | Date of policy surrender                                     |
    | SURRENDER_VALUE          | NUMBER(13,2)  | -               | Amount payable on surrender                                  |
    | ANNIVERSARY_PREMS        | NUMBER(13,2)  | -               | Anniversary premium amounts                                  |
    | RENEWAL_DATE             | DATE          | -               | Date of policy renewal                                       |
    | LOAN_VALUE               | NUMBER(10,2)  | -               | Value of policy loan                                         |
    | RENEWAL_STATUS           | CHAR(1)       | -               | Status of policy renewal                                     |
    | COMM_RATE_YR1            | NUMBER(8,2)   | -               | Commission rate for first year                               |
    | COMM_RATE_YR2            | NUMBER(8,2)   | -               | Commission rate for second year                              |
    | COMM_RATE_YR3            | NUMBER(8,2)   | -               | Commission rate for third year                               |
    | ADD_COMM_YR1             | NUMBER(8,2)   | -               | Additional commission for first year                         |
    | ADD_COMM_YR2             | NUMBER(8,2)   | -               | Additional commission for second year                        |
    | ADD_COMM_YR3             | NUMBER(8,2)   | -               | Additional commission for third year                         |
    | SUP_CODE                 | CHAR(3)       | -               | Supervisor code                                              |
    | UNIT_NO                  | NUMBER(6)     | -               | Unit number                                                  |
    | PAY_PERIOD               | NUMBER(2)     | -               | Payment period duration                                      |
    | REMARK_CODE              | CHAR(2)       | -               | Code for policy remarks                                      |
    | PREV_STATUS              | CHAR(2)       | -               | Previous policy status                                       |
    | STATUS_DATE              | DATE          | -               | Date of last status change                                   |
    | INTEREST_RATE            | NUMBER(5,2)   | -               | Applicable interest rate                                     |
    | CREATION_DATE            | DATE          | -               | Record creation date                                         |
    | CREATION_ID              | CHAR(4)       | -               | ID of user who created record                                |
    | DEBIT_ISSUE_DATE         | DATE          | -               | Date of debit issue                                          |
    | CITIZEN_CODE             | CHAR(1)       | -               | Citizenship code of policyholder                             |
    | BONUS                    | NUMBER(8,2)   | -               | Bonus amount                                                 |
    | LAPSE_CHARGE             | NUMBER(13,2)  | -               | Charges for policy lapse                                     |
    | PAIDUP_SUM               | NUMBER(13,2)  | -               | Paid-up value                                                |
    | EXACT_DURATION           | NUMBER(5,2)   | -               | Exact duration of policy                                     |
    | SUSPENSE_DATE            | DATE          | -               | Date of suspense entry                                       |
    | REINST_CHARGE            | NUMBER(13,2)  | -               | Reinstatement charges                                        |
    | INTERIM_BON              | NUMBER(8,2)   | -               | Interim bonus amount                                         |
    | LAST_CLAIM_DATE          | DATE          | -               | Date of last claim                                           |
    | CLAIM_STATUS             | CHAR(2)       | -               | Status of claim                                              |
    | SETTLEMENT_DATE          | DATE          | -               | Date of claim settlement                                     |
    | DECLINE_DATE             | DATE          | -               | Date of claim decline                                        |
    | FEMALE_EXTRA_PREM        | NUMBER(10,2)  | -               | Extra premium for female life                                |
    | DEATH_REASON             | CHAR(1)       | -               | Code for cause of death                                      |
    | TREATY_TYPE              | CHAR(2)       | -               | Type of reinsurance treaty                                   |
    | PERSIST_BONUS            | NUMBER(10,2)  | -               | Bonus for policy persistence                                 |
    | OVERIDE_COMM             | NUMBER(10,2)  | -               | Override commission amount                                   |
    | NOF_PREMIUMS_DUE         | NUMBER(5)     | -               | Number of premiums due                                       |
    | TAKEON_STATUS            | CHAR(1)       | -               | Status at policy takeover                                    |
    | DISCOUNT_AMOUNT          | NUMBER(8,2)   | -               | Amount of discount applied                                   |
    | DISCOUNT                 | CHAR(1)       | -               | Discount indicator                                           |
    | WP                       | CHAR(1)       | -               | Waiver of Premium indicator                                  |
    | PA                       | CHAR(1)       | -               | Personal Accident cover indicator                            |
    | MORTGAGE_PROTECTION      | CHAR(1)       | -               | Mortgage protection indicator                                |
    | OVER_RATE_YR1            | NUMBER(5,2)   | -               | Override rate for first year                                 |
    | OVER_RATE_YR2            | NUMBER(5,2)   | -               | Override rate for second year                                |
    | OVER_RATE_YR3            | NUMBER(5,2)   | -               | Override rate for third year                                 |
    | SUPERVISOR_NO            | NUMBER(6)     | -               | Supervisor number                                            |
    | BANK_NO                  | CHAR(6)       | -               | Bank account number                                          |
    | CLAIM_DATE               | DATE          | -               | Date of claim                                                |
    | LAPSE_PROCESS_DATE       | DATE          | -               | Date of lapse processing                                     |
    | COMPLETE_PARTIAL_PAYMENT | NUMBER(5)     | -               | Complete or partial payment indicator                        |
    | DEATH_CLAIM_ACCEPTANCE   | CHAR(1)       | -               | Death claim acceptance indicator                             |
    | DEATH_DATE               | DATE          | -               | Date of death                                                |
    | PROCESS_DATE_PUP         | DATE          | -               | Processing date for paid-up policy                           |
    | ACCOUNT_NO               | CHAR(20)      | -               | Account number                                               |
    | CURRENCY_CODE            | CHAR(3)       | -               | Currency code                                                |
    | CLAIM_AMOUNT             | NUMBER(13,2)  | -               | Amount claimed                                               |
    | VESTING_AGE              | NUMBER(2)     | -               | Age at which benefits vest                                   |
    | BONUS_YEAR               | NUMBER(4)     | -               | Year of bonus declaration                                    |
    | YEAR_INTERIM_BONUS       | NUMBER(4)     | -               | Year of interim bonus                                        |
    | JOINT_AGE                | NUMBER(2)     | -               | Age of joint life insured                                    |
    | PROPORTIONATE_SA         | NUMBER(13,2)  | -               | Proportionate sum assured                                    |
    | CHILD_AGE                | NUMBER(2)     | -               | Age of insured child                                         |
    | EMR                      | NUMBER(3)     | -               | Extra mortality rate                                         |
    | NET_PAIDUP_VALUE         | NUMBER(13,2)  | -               | Net paid-up value                                            |
    | DURATION                 | NUMBER(5,2)   | -               | Duration of policy                                           |
    | MDF_PRINT_REQUEST        | CHAR(1)       | -               | Medical form print request indicator                         |
    | YRS_AFTER_BONUS          | NUMBER(2)     | -               | Years after last bonus                                       |
    | POLICY_TYPE              | CHAR(1)       | -               | Type of policy                                               |
    | CIC                      | CHAR(1)       | -               | Critical Illness Cover indicator                             |
    | CIC_FEMALE_PREMIUM       | NUMBER(10,2)  | -               | Critical Illness Cover premium for female                    |
    | CIC_MALE_PREMIUM         | NUMBER(10,2)  | -               | Critical Illness Cover premium for male                      |
    | CIC_SUM_ASSURED          | NUMBER(10,2)  | -               | Critical Illness Cover sum assured                           |
    | CIC_TOTAL_PREMIUM        | NUMBER(13,2)  | -               | Total Critical Illness Cover premium                         |
    | CIC_TODATE               | NUMBER(13,2)  | -               | Critical Illness Cover amount to date                        |
    | DAB                      | CHAR(1)       | -               | Double Accident Benefit indicator                            |
    | LTB_MALE_PREMIUM         | NUMBER(10,2)  | -               | Long Term Benefits premium for male                          |
    | LTB_FEMALE_PREMIUM       | NUMBER(10,2)  | -               | Long Term Benefits premium for female                        |
    | ISB                      | CHAR(1)       | -               | Income Support Benefit indicator                             |
    | ISB_PREMIUM              | NUMBER(10,2)  | -               | Income Support Benefit premium                               |
    | ISB_SUM_ASSURED          | NUMBER(13,2)  | -               | Income Support Benefit sum assured                           |
    | PARTNERS_AGE             | NUMBER(2)     | -               | Age of partner                                               |
    | FEMALE_SMOKER            | CHAR(1)       | -               | Female smoker status                                         |
    | MALE_SMOKER              | CHAR(1)       | -               | Male smoker status                                           |
    | JOINT_SMOKER             | CHAR(1)       | -               | Joint life smoker status                                     |
    | TYPE                     | CHAR(1)       | -               | Policy type indicator                                        |
    | WP_FEMALE_PREMIUM        | NUMBER(10,2)  | -               | Waiver of Premium for female                                 |
    | WP_MALE_PREMIUM          | NUMBER(10,2)  | -               | Waiver of Premium for male                                   |
    | UNEXPIRED_PERIOD         | NUMBER(13,2)  | -               | Remaining policy period                                      |
    | LTB                      | CHAR(1)       | -               | Long Term Benefits indicator                                 |
    | ACCESS_AGE               | NUMBER(2)     | -               | Age at which benefits are accessible                         |
    | RATE_TYPE                | CHAR(1)       | -               | Type of rate applied                                         |
    | CIC_2ND_LIFE             | CHAR(1)       | -               | Critical Illness Cover for second life                       |
    | ISB_2ND_LIFE             | CHAR(1)       | -               | Income Support Benefit for second life                       |
    | LTB_2ND_LIFE             | CHAR(1)       | -               | Long Term Benefits for second life                           |
    | DAB_2ND_LIFE             | CHAR(1)       | -               | Double Accident Benefit for second life                      |
    | WP_2ND_LIFE              | CHAR(1)       | -               | Waiver of Premium for second life                            |
    | REFUND_PREMIUM           | NUMBER(10,2)  | -               | Premium refund amount                                        |
    | ISB_FEMALE_PREMIUM       | NUMBER(10,2)  | -               | Income Support Benefit premium for female                    |
    | DAB_FEMALE_PREMIUM       | NUMBER(10,2)  | -               | Double Accident Benefit premium for female                   |
    | DAB_MALE_PREMIUM         | NUMBER(10,2)  | -               | Double Accident Benefit premium for male                     |
    | MATURITY_AGE             | NUMBER(2)     | -               | Age at policy maturity                                       |
    | POL_FUND                 | NUMBER(13,2)  | -               | Policy                                                       |
