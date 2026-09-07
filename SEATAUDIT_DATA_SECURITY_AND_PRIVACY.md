# SeatAudit for Jira — Data Security and Privacy Statement

SeatAudit for Jira is designed as a read-mostly, Forge-native Jira administration utility with data minimization and transparent evidence handling.

## Data accessed

When an administrator runs a SeatAudit review, the app may access Jira account IDs, display names, account active state, account type, profile-visible email/avatar fields, inspectable projects, project roles, and role actors through Atlassian-supported APIs. Hidden profile data is treated as unavailable evidence rather than as an error or inferred value.

## Processing location

SeatAudit V1 processes app logic in Atlassian Forge and presentation/export logic in the customer browser. It has no ASHBIZCON-operated application backend or external database for customer Jira inventories.

## Stored data

SeatAudit uses Atlassian Forge KVS only for bounded, schema-versioned configuration such as supported audit policy settings, protection IDs/types, administrator-entered savings assumptions, default filters, and report preferences.

SeatAudit does not persist full Jira user inventories, profile-visible emails, completed audit results, or generated CSV/JSON/HTML reports in an ASHBIZCON backend.

## External transfers and egress

SeatAudit V1 has no custom external network egress, external analytics or advertising SDK, external AI/LLM service, or organization API-key collection. Customer Jira inventory data is not intentionally sent to an ASHBIZCON-operated external service.

## Reports

CSV, JSON, and HTML exports are generated only after an explicit administrator action. Exported files may contain Jira user information and, after download, are governed by the customer's own storage, access-control, retention, and handling practices.

## Security model

- Atlassian Forge provides the app runtime and platform-managed infrastructure.
- Jira API access is authenticated and authorized through Atlassian's Forge mechanisms and the permissions granted to the app.
- SeatAudit is read-mostly and does not request Jira write/delete/manage scopes for automatic account deactivation, deletion, suspension, or group mutation.
- SeatAudit does not ask customers to provide Jira account passwords, personal access tokens, or external organization administrator API keys for its V1 workflow.
- Evidence limitations are surfaced explicitly so unavailable data is not presented as proof.

## Data retention

SeatAudit does not retain full inventories or generated reports in an ASHBIZCON backend. Bounded configuration stored in Atlassian Forge KVS follows the app's Forge storage lifecycle and applicable Atlassian platform controls.

## Customer responsibility

SeatAudit findings are review recommendations, not proof that an account is safe to remove or that a billing seat is reclaimable. Administrators remain responsible for validating organization-specific access, identity, business ownership, and billing context before making changes outside SeatAudit.

## Related policies

- [Privacy Notice](./PRIVACY.md)
- [Security Policy](./SECURITY.md)
- [SeatAudit Documentation](./SEATAUDIT_DOCUMENTATION.md)
- [Support Policy](./SUPPORT.md)

Security concerns can be reported to **security@ashbizcon.com**. General product support is available at **support@ashbizcon.com**.
