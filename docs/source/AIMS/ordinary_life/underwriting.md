# Underwriting

## Definitions

1. To set one's name to (an insurance policy) for the purpose of thereby becoming answerable for a designated loss or damage on consideration of receiving a premium percent. [^1]
2. Insure on life or property. [^1]
3. To assume liability for (a sum or risk) as an insurer. [^1]

## AIMS Underwriting Process

### Initiation

The underwriting process is initiated when agents introduce new business (clients) through the [Agent's Portal](../../portals/agents.md). The submitted cases undergo a thorough review and approval process by the sales team. Once approved, the underwriting process formally commences.

> An integration exists between the Agent's Portal and AIMS, facilitating the exchange of basic information necessary to initiate the underwriting process.

### The Process

Step by step process including the technical details of the aims underwriting process:

1. Sales Manager Review and Approval:
    - Agents submit physical forms alongside the digital data entered into the agent portal.
    - Sales managers verify the physical forms against the data in the agent portal.
    - The physical forms are sent to the Scanning Center for digitization in the Electronic Document Management System [(EDMS)](../../internal_applications/edms.md).
    - Upon approval in the agent portal, the corresponding digitized file in EDMS is forwarded to the Underwriting Department.

2. Agents Portal and AIMS Integration:
    - The agent portal integrates with the AIMS system through a trigger named [update_deductions_without_req](../../oracle/schemas/ext/tables/agent_report.md#update-deductions).
    - The agent portal stores data related to clients, agents, and manager approvals in the [agent_report](../../oracle/schemas/ext/tables/agent_report.md) table under the [ext](../../oracle/schemas/ext/index.md) schema.
    - When the **`mng_approval`** column in the **`agent_report`** table is updated with a value of 1 (indicating approval), the trigger inserts basic KYC information into the [salarydeduct](../../oracle/schemas/olfsordata/tables/salarydeduct.md) table within the [olfsordata](../../oracle/schemas/olfsordata/index.md) schema.

3. Underwriting Process in AIMS:
    - Underwriters access the AIMS system through the menu path: **`AIMS Life System / Ordinary Life Subsystem / Policy Main Menu / New Business Menu / Proposal Details - MultiScreen`**.
    - The underwriting process starts by verifying the data transferred from the agent portal to AIMS against the digitized client form in EDMS.
    - Underwriters then complete additional required information, such as:
        - Client details (recorded in [laclnt](../../oracle/schemas/olfsordata/tables/laclnt.md))
        - Dependents (recorded in [ladep](../../oracle/schemas/olfsordata/tables/ladep.md)) and beneficiaries (recorded in [lapben](../../oracle/schemas/olfsordata/tables/lapben.md))
        - Policy information (recorded in [lapol](../../oracle/schemas/olfsordata/tables/lapol.md))
        - Compliance details as per regulators
    - The final outcome of the underwriting process is a <span class="text-green">**POLICY PROPOSAL**</span>, details recorded in [lapro](../../oracle/schemas/olfsordata/tables/lapro.md).

[^1]: [Underwriting](https://www.merriam-webster.com/dictionary/underwriting)
