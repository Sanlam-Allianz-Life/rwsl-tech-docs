# Ordinary & Group Life Ledger Data 

Schema name: `OLGLDATA`

## Tables

| **Name**                                              | **Description**                                                             |
|-------------------------------------------------------|-----------------------------------------------------------------------------|
| [PAYREQSTMULTI][olgldata.payreqstmulti]               | Payment requests                                                            |
| [PAYREQSTMULTISUM][olgldata.payreqstmultisum]         | Payment requests summary table (Batches)                                    |
| [PENDING_TRANSACTIONS][olgldata.pending_transactions] | Pending transaction to be processed by GT Bank internet banking integration |

## Triggers

| **Name**                  | **tables**                                                               |
|---------------------------|--------------------------------------------------------------------------|
| [process_gtbank]          | `TRG OWNER` [olgldata.payreqstmultisum], [olgldata.pending_transactions] |
| [update_payreqstmultisum] | `TRG OWNER` [olgldata.payreqstmultisum]                                  |

<!-- tables -->
[olgldata.payreqstmulti]: tables/payreqstmulti.md
[olgldata.payreqstmultisum]: tables/payreqstmultisum.md
[olgldata.pending_transactions]: tables/pending_transactions.md

<!-- Triggers -->
[process_gtbank]: tables/payreqstmultisum.md#process-gt-bank-payments
[update_payreqstmultisum]: tables/payreqstmultisum.md#update-batch-payments-request-table
