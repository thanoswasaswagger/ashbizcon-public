# SeatAudit for Jira — Privacy & Security Statement

This statement describes how ASHBIZCON SeatAudit for Jira handles data and the main security boundaries of the current Forge-native version.

## Data SeatAudit reads

When an administrator runs a live audit, SeatAudit may process Jira account IDs, display names, account active state, account type, profile-visible email/avatar fields, inspectable projects, project roles, and role actors needed to build the requested review. Hidden profile fields are accepted as normal privacy behavior and are not treated as scan failures.

## Processing and storage

Processing occurs in Atlassian Forge and the customer browser. The current version has no ASHBIZCON application backend, external database, telemetry or advertising tracker, external AI service, organization API-key collection, or custom external network egress.

Forge KVS stores only bounded, schema-versioned application settings such as review policy, protected account identifiers/types, savings assumptions, default filters, and report preferences. Full Jira user inventories, email inventories, completed audit results, and generated reports are not persisted by SeatAudit.

CSV, JSON, and HTML reports are generated only after an explicit administrator action. After download, those files are controlled by the customer and should be handled under the customer’s own retention, access, and security policies.

## Permissions and authorization

SeatAudit is read-only with respect to Jira. It requests Jira read scopes needed for the documented user and project-role evidence plus Forge `storage:app` for bounded settings. It does not request Jira write, delete, manage, organization-admin, SCIM, or custom egress permissions.

Customer-triggered Jira reads run through Atlassian Forge and remain subject to the invoking administrator’s Jira permissions. Frontend code does not receive Jira credentials.

SeatAudit does not contain account deactivation, deletion, suspension, access-removal, or group-mutation actions.

## Evidence safety

SeatAudit deliberately distinguishes supported evidence from unavailable or limited evidence. It does not invent authoritative last-active dates, authoritative billable-seat status, guaranteed license savings, or proof that a candidate is safe to remove.

Direct project-role evidence is not the same as all possible Jira access. Administrators must verify review candidates with their organization’s own identity, access, and licensing controls before making changes outside SeatAudit.

## Application security

Inputs and stored settings are bounded and validated. Jira responses are defensively parsed and customer-facing errors avoid exposing raw Jira responses or customer-sensitive content. Frontend rendering relies on React escaping, and generated CSV/HTML exports include safeguards against common spreadsheet or markup injection risks.

Full inventories, report contents, credentials, authorization headers, and tokens must not be written to application logs or support tickets.

## Dependency and vulnerability management

Release CI uses reproducible dependency installation, automated checks, and dependency/security review. High or critical production dependency findings are treated as release blockers. Lower-severity or upstream transitive findings are tracked and remediated when a compatible upstream fix is available or within applicable Atlassian Marketplace remediation requirements.

## Security reporting

Report suspected vulnerabilities privately to security@ashbizcon.com. Do not include real customer PII, credentials, API tokens, authorization headers, or exported user inventories in a security report.

For ordinary product support, contact support@ashbizcon.com.
