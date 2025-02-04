# Salary Code Sequentials Table

Table storing sequence used to generate salary codes

## Table Description

??? quote "SALSERIALS"

    | **Field Name** | **Data Type** | **Constraint** | **Description**     |
    |----------------|---------------|----------------|---------------------|
    | CODE           | NUMBER(3)     | NOT NULL       | Sequence identifier |
    | SAL_NO         | NUMBER(5)     |                | Sequential number   |

## References

1. [Update deductions trigger](../../ext/tables/agent_report.md#update-deductions): updates `sal_no` column value value after each record insert in `olfsordata.salarydeduct`
