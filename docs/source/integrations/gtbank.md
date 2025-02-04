# GT Bank

API integration with Guaranty Trust Bank Rwanda Automated Payments System (GAP). It provides endpoints for initiating transactions, confirming transactions, and getting bank details.

!!! success ""

    > **Objective: API pushing payments from AIMS to GAP in real time**

## Background

SanlamAllianz Life previously was exporting payment order details from the core system (AIMS) into an Excel file, which was manually uploaded into the GAP portal for processing. The manual process highlighted an opportunity for improvement: integrating AIMS and GAP to streamline the payment workflow. By automating the transfer of payment order details, the integration aims at reducing the turnaround time (TAT) and minimize human errors that occured during the submission and approval of payment orders.

## API Development

The integration is facilitated through a RESTful API, utilizing JSON for data serialization and OAuth 2.0 for secure authentication.

### Load Configurations

Load environment variables from .env file, the variables are:

1. API Base url provided by GT Bank
2. Database Connection string, schema in use is [olgldata](../oracle/schemas/olgldata/index.md)
3. Partner Code: Unique SanlamAllianz identifier provided by GT Bank

### Authentication

#### Get Refresh Token

Generates a refresh token with a TTL of 1 month. The username is derived from the incoming request's IP address. The request must include a valid partner code.

Endpoint: `GET API_BASE_URL/api/v1/token/refresh`

=== "Request Body"

    `None`

=== "Response"

    ```json
    {
        "refreshToken": "string",
        "expires": number
    }
    ```

=== "Request Headers"

    `Content-Type: application/json`

=== "Request Parameters"

    `partner`: (required) loaded from configurations

#### Get Authentication Token

Generates an authorization token with a TTL of 24 hours using the refresh token and the IP address as the username.

Endpoint: `POST API_BASE_URL/api/v1/auth`

=== "Request Body"

    ```json
    {
        "refreshToken": "string",
        "partner": "string"
    }
    ```

=== "Response"

    ```json
    {
        "token": "string",
        "expires": number
    }
    ```

=== "Request Headers"

    `Content-Type: application/json`

#### Get Authorization Token's Time To Live (TTL)

Retrieves the remaining time to live (TTL) for the current authorization token.

Endpoint: `GET API_BASE_URL/api/v1/auth/ttl`

=== "Request Body"

    `None`

=== "Response"

    ```json
    {
        "expires": number
    }
    ```

=== "Request Headers"

    `Authorization: Bearer <token>`

### Transactions Processing

#### Fetch Pending Transactions

Fetch pending transactions from Oracle database and returns a formatted according to API requirements list of transactions dictionary.

Data Source: [olgldata.pending_transactions](../oracle/schemas/olgldata/tables/pending_transactions.md)

#### Submit Transactions

Submit transactions to the API.

Endpoint: `POST API_BASE_URL/api/v1/transactions`

=== "Request Body"

    ```json
    [
        {
            "date": "01JAN2001",
            "currency": "RWF",
            "beneficiary": {
            "name": "MY BENEFICIARY NAME",
            "account": "12345678910",
            "bank": {
                "name": "B&T Bank",
                "swift": "BNKTXN",
                "code": "BNKTXN"
            }
            },
            "amount": 4958000,
            "reference": "1002024111900",
            "remarks": "MY TXN REMARK",
            "external": true
        },
    ]
    ```

=== "Response"

    ```json
    {
        "reference": "1002024111900",
        "result": {
            "success": true,
            "code": "1|OK",
            "message": "1000000252 / E2E ACK",
            "data": [
                {
                    "code": "1000",
                    "message": "The Operations completed successfully"
                }
            ]
        }
    }
    ```

=== "Request Headers"

    `Content-Type: application/json` <br>
    `Authorization: Bearer <token>`

=== "Request Parameters"

    `partner: PartnerCode`

=== "Field Mapping"

    | **GT Bank API Field Name** | **Data Source Field Name** |
    |----------------------------|----------------------------|
    | date                       | transaction_date           |
    | name                       | beneficiary_name           |
    | swift                      | beneficiary_bank_swift     |
    | code                       | beneficiary_bank_code      |
    
    > Remaining fields from API matches with Data Source field names
    

#### Update Transactions Status

Update transaction status in the oracle database by setting columns `STATUS` and `PROCESSED_DATE` to PROCESSED or FAILED and current date respectively for each transactions `REFERENCE`
