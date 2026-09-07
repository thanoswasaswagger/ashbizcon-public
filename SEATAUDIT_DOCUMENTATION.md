# SeatAudit for Jira — Documentation

SeatAudit for Jira is an ASHBIZCON Forge app for evidence-first Jira seat review and license-hygiene workflows. It helps Jira administrators identify accounts worth human review, understand the evidence behind each finding, and export decision-ready reports without automatically deactivating, deleting, suspending, or modifying Jira accounts.

## What SeatAudit does

SeatAudit can:

- build a paginated Jira user inventory from Jira-supported APIs;
- show Jira-reported account status and account type;
- map direct project-role footprint for inspectable Jira projects;
- identify review candidates using conservative, deterministic rules;
- explain why each candidate was flagged and show evidence limitations;
- distinguish available, limited, unavailable, and not-evaluated evidence;
- let administrators select review candidates and enter their own seat-cost assumptions;
- export formula-safe CSV, deterministic JSON, and a browser-generated HTML management report;
- store bounded configuration in Atlassian Forge KVS.

SeatAudit does not automatically deactivate, suspend, delete, remove, or deprovision Jira accounts.

## Getting started

1. Install SeatAudit for Jira from Atlassian Marketplace using a Jira administrator account.
2. Open **SeatAudit** from the Jira administration area.
3. Review the evidence-coverage indicators before interpreting results.
4. Run a live audit to retrieve Jira-supported account and direct project-role evidence.
5. Use search, filters, sorting, and the evidence inspector to review candidates.
6. Select only the accounts you want included in your review scenario.
7. Optionally enter your own seat-cost assumptions in Settings.
8. Export CSV, JSON, or HTML reports when needed.

A clearly labeled demo mode may be available for exploring the interface. Demo data is not substituted for failed live Jira data.

## Evidence model

SeatAudit is deliberately conservative. It keeps different evidence types separate instead of turning missing data into certainty.

### Account status

SeatAudit can display Jira-reported account state where the Jira API exposes it. Account state alone does not prove that a paid seat can safely be reclaimed.

### Project and role footprint

SeatAudit maps direct project-role assignments for inspectable projects. Direct role evidence is useful context, but it is not the same as total Jira access because access can also be granted through other paths.

### Activity and billing evidence

SeatAudit does not invent authoritative product last-active dates or billable-seat status when the available Jira/Forge APIs do not prove them. The interface surfaces those limitations so administrators can perform the appropriate follow-up check.

## Review candidates

A SeatAudit finding means **review recommended**, not **safe to remove**. Administrators remain responsible for validating business ownership, access paths, licensing state, identity-provider status, and other organization-specific context before making account changes outside SeatAudit.

## Reports and exports

SeatAudit can generate:

- **CSV** for spreadsheet review;
- **JSON** for deterministic machine-readable audit output;
- **HTML management report** for a portable, human-readable summary.

Exports are generated in the customer browser after an explicit administrator action. SeatAudit does not persist full inventories or generated reports in an ASHBIZCON backend.

## Settings and savings scenarios

Administrators can configure supported review-policy settings and enter their own cost assumptions. Savings values are scenario estimates based on administrator-entered assumptions and selected review candidates. They are not guarantees of actual license savings.

## Permissions and data handling

SeatAudit is read-mostly and requests only the permissions required for its documented Jira evidence and bounded Forge configuration. It does not request Jira write/delete/manage scopes for account modification.

Processing occurs within Atlassian Forge and the customer browser. SeatAudit V1 has no ASHBIZCON backend, external database, advertising tracker, external AI/LLM service, or custom external egress.

See:

- [Privacy Notice](./PRIVACY.md)
- [Security Policy](./SECURITY.md)
- [Data Security and Privacy Statement](./SEATAUDIT_DATA_SECURITY_AND_PRIVACY.md)
- [Support Policy](./SUPPORT.md)

## Support

For SeatAudit support, email **support@ashbizcon.com** and include the SeatAudit version, Forge environment, non-sensitive diagnostic run ID, coverage states, and concise reproduction steps. Do not send credentials, API tokens, authorization headers, or exported user inventories.
