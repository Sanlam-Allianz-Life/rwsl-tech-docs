# External Data Schema

Schema name: `EXT`

## Tables

| **Name**                        | **Description** |
|---------------------------------|-----------------|
| [AGENT_REPORT][tbl-agentreport] |                 |

## Triggers

| **Name**                                              | **Tables**                                                                                   |
|-------------------------------------------------------|----------------------------------------------------------------------------------------------|
| [update_deductions_without_req][trg-updatedeductions] | `TRG OWNER` [ext.agent_report][tbl-agentreport], [olfsordata.salarydeduct][tbl-salarydeduct] |

[trg-updatedeductions]: tables/agent_report.md#update-deductions
[tbl-agentreport]: tables/agent_report.md
[tbl-salarydeduct]: ../olfsordata/tables/salarydeduct.md
