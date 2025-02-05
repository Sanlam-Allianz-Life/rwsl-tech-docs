# TransUnion (CRB) Data Upload API

API for TransUnion Credit Bureau Subscribers to report credit information via web service client applications

## Reported Data

- Customer details information
- Policy details information
- Life Insurance claims

## API Development

| **Item**          | **Details**                                                                                                     |
|-------------------|-----------------------------------------------------------------------------------------------------------------|
| API Documentation | <https://secure3.crbafrica.com/duv2/doc/index.html>{:target="_blank"}                                           |
| Documentation     | [TransUnion CRB Data API Rwanda v1.0](../Files/TransUnion%20CRB%20Data%20API_Rwanda_V1.0.pdf){:target="_blank"} |
| GitHub Repo       | :fontawesome-brands-github: <https://github.com/jospinbahizi/transunion-crb>{:target="_blank"}                  |
| LoginURL          | `BASE_URL/login`                                                                                                |
| UpdateURL         | `BASE_URL/data/rw/update`                                                                                       |

!!! info

    UAT BASE URL: <https://secure3.crbafrica.com/duv2/>{:target="_blank"}

    PROD BASE URL: <https://secure7.transunionafrica.com/duv2/>{:target="_blank"}

!!! note "Important Notes"

    1. **Data Submission Requirements:** submit all required data to the CRB no later than the 8th day of each calendar month.
    2. **System Development Guidelines:** review the complete [documentation](../Files/TransUnion%20CRB%20Data%20API_Rwanda_V1.0.pdf){:target="_blank"} to implement all necessary validation checks and ensure compliance with established development standards.
    3. **Claims Processing Protocol:** when submitting claims reports, include comprehensive policy details and client information for proper cross-referencing and complete documentation.

### Authentication

`POST LoginURL`

=== "Sample request"

    ```json
    {
        "infinityCode": "INFINITY_CODE_PROVIDED",
        "password": "YOUR_PASSWORD",
        "username": "YOUR_USERNAME"
    }
    ```

=== "Sample response"

    ```json
    {
        "token":
        "eyJhbGciOiJIUzUxMiJ9.eyJzdWIiOiJhIiwiZXhwIjoxNTI1ODQ2Mzc4LCJzdWJzY3JpYmVySWQiOjEzMjl9.
        QqP3MdnXOo1tgXz5AsVQP8Y6 5vAQ2TVvClDRPCINfPZfFB9dCUmuxkbyISzwT0hhKTgUlwIz7j-0Rxd56UpaBwup",
        "expiresAfter": "2592000000",
        "status": "Ok"
    }
    ```

The Bearer token received in the response must be included in the Authorization header for all subsequent requests to the Data Upload API.

!!! note "Request Headers"

    * Content-Type: application/json
    * Authotizarion: Bearer Token

### Customer Details

Data Source: [olfsordata/laclnt](../oracle/schemas/olfsordata/tables/laclnt.md)

CRB API Endpoint: `POST $UpdateURL/customerdetails`

=== "Sample Request"

    ``` json
    {
        "customerDetailsInformationRecord": {
            "customerType": "I",
            "salutation": "string",
            "surName": "string",
            "firstName": "string",
            "identificationDocumentType": "I",
            "identificationDocumentNumber": "string",
            "gender": "string",
            "dateOfBirth": "string",
            "placeOfBirth": "string",
            "physicalAddress": "string",
            "country": "RWANDA",
            "sector": "string",
            "homeTelephone": "string",
            "workTelephone": "string",
            "mobileTelephone": "string",
            "income": "0.00",
            "incomeFrequency": "M",
            "nationality": "string",
            "district": "string",
            "province": "string",
        },
        "recordType": "MX"
    }
    ```
=== "Field Mapping"

    | **CRB Field Name**           | **Data Source Field Name** | **Comment**                       |
    |------------------------------|----------------------------|-----------------------------------|
    | salutation                   | title                      |                                   |
    | surName                      | surname                    |                                   |
    | firstName                    | other_names                |                                   |
    | identificationDocumentType   | N/A                        | Default `I`                       |
    | identificationDocumentNumber | identity_card_no           |                                   |
    | gender                       | sex                        |                                   |
    | mobileTelephone              | mobile_no                  | Include Area Code, default `+250` |
    | workTelephone                | mobile_no                  | Include Area Code, default `+250` |
    | homeTelephone                | mobile_no                  | Include Area Code, default `+250` |
    | dateOfBirth                  | birth_date                 |                                   |
    | placeOfBirth                 | birth_place                |                                   |
    | physicalAddress              | address                    |                                   |
    | sector                       | sector_code                |                                   |
    | nationality                  | nationality                |                                   |
    | customerType                 | N/A                        | Default `I`                       |
    | country                      | N/A                        | Default `RWANDA`                  |
    | income                       | N/A                        | Default `0.00`                    |
    | incomeFrequency              | N/A                        | Default `M`                       |
    | district                     | N/A                        | Derived from sector               |
    | province                     | N/A                        | Derived from district             |

### Policy Details

Data Source: [olfsordata/lapol](../oracle/schemas/olfsordata/tables/lapol.md)

CRB API Endpoint: `POST $UpdateURL/policydetails`

=== "Sample Request"

    ``` json
    {
        "policyDetailsInformationRecord": {
            "basePolicyNumber": "string",
            "surName": "string",
            "firstName": "string",
            "identificationDocumentNumber": "string",
            "identificationDocumentType": "I",
            "currency": "RWF",
            "classification": "L",
            "numberOfPersonsCovered": "1",
            "policyType": "B",
            "policyStatus": "P",
            "baseTransactionDate": "string",
            "policyStartDate": "string",
            "policyExpiryDate": "string",
            "insuredAmount": "string",
            "grossPremiumAmount": "string",
            "currentBalanceOnPolicy": "0.00",
            "premiumPaidToDate": "string",
            "dueDate": "string",
            "daysInArrears": "0",
            "endorsementDate": "string"
        },
        "recordType": "PO"
    }
    ```
=== "Field Mapping"

    | **CRB Field Name**           | **Data Source Field Name** | **Comment**                   |
    |------------------------------|----------------------------|-------------------------------|
    | basePolicyNumber             | policy_no                  |                               |
    | baseTransactionDate          | proposal_date              |                               |
    | policyStartDate              | effective_date             |                               |
    | policyExpiryDate             | maturity_date              |                               |
    | grossPremiumAmount           | modal_prem                 |                               |
    | dueDate                      | premdue_date               |                               |
    | premiumPaidToDate            | received                   |                               |
    | insuredAmount                | min_assured                |                               |
    | endorsementDate              | dola                       |                               |
    | surName                      | N/A                        | Derived from customer details |
    | firstName                    | N/A                        | Derived from customer details |
    | identificationDocumentType   | N/A                        | Derived from customer details |
    | identificationDocumentNumber | N/A                        | Derived from customer details |
    | currency                     | N/A                        | Default `RWF`                 |
    | classification               | N/A                        | Default `L`                   |
    | numberOfPersonsCovered       | N/A                        | Default `1`                   |
    | policyType                   | N/A                        | Default `B`                   |
    | policyStatus                 | N/A                        | Default `P`                   |
    | currentBalanceOnPolicy       | N/A                        | Default `0.00`                |
    | daysInArrears                | N/A                        | Default `0`                   |

### Claims Details

Data Source: [olfsordata/laclaim](../oracle/schemas/olfsordata/tables/laclaim.md)

CRB API Endpoint: `POST UpdateURL/lifeinsurance`

=== "Sample Request"

    ```json 
    {
        "lifeInsuranceClaimsInformationRecord": {
            "policyNumber": "string",
            "claimNumber": "string",
            "claimDeclarationDate": "string",
            "claimStatus": "P",
            "rejectionReason": "",
            "amountOfClaimReserve": "string",
            "amountPaid": "string",
            "claimSettlementDate": "string",
            "classOfInsurance": "C",
            "claimType": "A",
            "incidentDate": "string",
            "beneficiary": "string",
            "beneficiaryAddress": "string",
            "identificationDocumentType": "I",
            "identificationDocumentNumber": "string"
        },
        "recordType": "PL"
    }
    ```
=== "Field Mapping"

    | **CRB Field Name**           | **Data Source Field Name** | **Comment**                                                |
    |------------------------------|----------------------------|------------------------------------------------------------|
    | policyNumber                 | policy_no                  |                                                            |
    | claimNumber                  | claim_no                   |                                                            |
    | claimDeclarationDate         | process_date               |                                                            |
    | claimStatus                  | N/A                        | Default `P`                                                |
    | rejectionReason              | N/A                        | Default `null`                                             |
    | amountOfClaimReserve         | net_payment                |                                                            |
    | amountPaid                   | net_payment                |                                                            |
    | classOfInsurance             | N/A                        | Default `C`                                                |
    | claimType                    | N/A                        | Default `A`                                                |
    | incidentDate                 | process_date               |                                                            |
    | claimSettlementDate          | process_date               |                                                            |
    | Beneficiary                  | N/A                        | Derived from customer details (`surName` + `firstName`)    |
    | identificationDocumentType   | N/A                        | Default `I`                                                |
    | identificationDocumentNumber | N/A                        | Derived from customer details                              |
    | beneficiaryAddress           | N/A                        | Derived from customer details (`physicalAddress` or `N\A`) |
