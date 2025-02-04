# Ordinary Life Data Schema

Schema name: `OLFSORDATA`

## Tables

| **Name**                                | **Description**                                    |
|-----------------------------------------|----------------------------------------------------|
| [LACLNT](tables/laclnt.md)              | All client details                                 |
| [SALARYDEDUCT][olfsordata.salarydeduct] | Salary deduction details and deduction process     |
| [LAPRO](tables/lapro.md)                | All details on a Proposal                          |
| [LADEP](tables/ladep.md)                | All details on dependent (safe family and funeral) |
| [LAMED](tables/lamed.md)                | All details about medicals                         |
| [LAPBEN](tables/lapben.md)              | All about beneficiary                              |
| [LAPOL](tables/lapol.md)                | All details on converted and issued polices        |
| [SALSERIALS](tables/salserials.md)      | Salary code sequential number                      |

## Triggers

| **Name**                        | **Tables**                                                |
|---------------------------------|-----------------------------------------------------------|
| [update_deductions_without_req] | [olfsordata.salarydeduct], `TRG OWNER` [ext.agent_report] |

[update_deductions_without_req]: ../ext/tables/agent_report.md#update-deductions
[ext.agent_report]: ../ext/tables/agent_report.md
[olfsordata.salarydeduct]: tables/salarydeduct.md
