# SeatAudit for Jira — Documentation

SeatAudit for Jira by ASHBIZCON is a Forge-native, evidence-first Jira seat-review and license-hygiene app for administrators. It helps identify accounts that deserve human review, explains the evidence behind each finding, and creates management-ready exports without automatically changing Jira access.

## What SeatAudit does

- Builds a paginated, deduplicated Jira user inventory from data available to the invoking administrator.
- Shows Jira-reported account state and supported profile evidence.
- Maps inspectable direct project-role footprint with bounded, partial-failure-safe processing.
- Applies conservative, deterministic review rules.
- Separates available, limited, unavailable, and not-evaluated evidence so missing data is not presented as proof.
- Provides Overview, Review seats, Projects & roles, Reports, Settings, search, filters, sorting, evidence details, and candidate selection.
- Generates formula-safe CSV, deterministic JSON, and local HTML management exports.
- Lets administrators enter their own seat-cost assumptions for scenario estimates.

## Important evidence boundaries

SeatAudit is a review assistant, not an automatic deprovisioning system.

SeatAudit does not claim that a review candidate is definitely a paid seat, definitely inactive in every Atlassian product, or safe to remove. Authoritative product last-active data and authoritative billable-seat status are not inferred when the connected Jira APIs do not prove them. Direct project-role evidence is not the same as total access, and other access paths can exist.

Each finding should be verified by an administrator using the organization’s own access, identity, and licensing controls before any account or license change is made outside SeatAudit.

## Running an audit

1. Open **SeatAudit for Jira** from the Jira administration area.
2. Choose **Start live audit**.
3. Review the evidence coverage states and any limitations.
4. Use **Review seats** to search, filter, sort, and inspect accounts.
5. Open an account’s evidence drawer to review findings, direct project-role footprint, known limitations, and the recommended next administrator check.
6. Select only the accounts you want to include in a review scenario.
7. Use **Reports** to export the review in CSV, JSON, or local HTML format.

A clearly labeled fictional demo mode may be available for product exploration. Demo data is never substituted for a failed live audit.

## Reports and savings scenarios

SeatAudit’s savings figures are scenarios based on the administrator’s configured cost assumptions and selected candidates. They are not billing data and are not a guarantee of savings.

Exports are generated only after an explicit administrator action. Downloaded files can contain Jira user information and should be handled under the customer’s own data-retention and access-control policies.

## Data handling

SeatAudit V1 processes Jira data in Atlassian Forge and the customer browser. It has no ASHBIZCON application backend, external database, advertising tracker, analytics SDK, external AI service, or custom external egress.

Forge KVS is used only for bounded SeatAudit settings. Full inventories, generated reports, and exports are not persisted by SeatAudit.

See the public Privacy & Security Statement and Support Policy for further details.

## Permissions

SeatAudit requests Jira read access needed for supported user/project-role evidence plus Forge app storage for settings. It does not request Jira write, delete, or access-management permissions and does not include automatic account deactivation, suspension, deletion, or group mutation.

## Support

For product support, use the public ASHBIZCON SeatAudit support resources or email support@ashbizcon.com. Do not send credentials, authorization headers, API tokens, exported inventories, or other customer-sensitive data in support requests.

Security reports should be sent privately to security@ashbizcon.com without customer PII or credentials.
