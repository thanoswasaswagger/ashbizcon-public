# Security

SeatAudit V1 is read-only with respect to Jira. It requests Atlassian's documented classic read scopes `read:jira-user` and `read:jira-work`, plus Forge `storage:app` for bounded application settings. It requests no Jira write, delete, manage, organization-admin, SCIM, external-fetch, or custom egress permission.

The app contains no access-removal or account-mutation action, remote backend, customer credential collection, telemetry, advertising tracker, or external AI service. Inputs and stored settings are bounded and validated. Jira responses are defensively parsed; customer-facing errors do not expose raw Jira responses or PII. HTML and CSV exports neutralize injection risks and frontend rendering relies on React escaping.

## Authorization boundaries

Customer-triggered Jira reads originate from the Jira admin page and use Forge `api.asUser()`. Jira therefore evaluates the invoking administrator's own permissions in addition to the app's manifest scopes. UI code never receives Jira credentials and never calls Jira directly.

A separate token-protected live-smoke webtrigger exists only in the development manifest so CI can validate Jira + KVS without an interactive user session. That development diagnostic explicitly uses `api.asApp()`, emits only bounded non-PII pass/failure markers, creates a temporary webtrigger URL, and removes its temporary token/route after the check. The production manifest contains neither the webtrigger nor the live-smoke function.

Full account inventories and generated reports are not persisted by SeatAudit. Forge KVS stores only validated application settings. Do not log inventories, report contents, credentials, authorization headers, or customer PII.

## Marketplace licensing

Marketplace licensing is enabled in both development and production manifests. Production live scans and persisted-settings writes fail closed when Forge does not provide an active Marketplace license. Development remains usable for engineering validation, including Atlassian's simulated license states. The clearly labeled fictional demo remains available without granting unlicensed live Jira access.

## Dependency posture

Release CI uses reproducible `npm ci` installs and automated dependency audits. The September 2026 release review found no high or critical production dependency findings. Two moderate transitive findings descend from Atlassian's current `@forge/bridge` dependency graph through Atlaskit and `uuid`; SeatAudit does not directly invoke the affected transitive API.

`@forge/bridge` 6.3.1 is the current public Forge Bridge release as of the release review. SeatAudit does not force an incompatible transitive override merely to suppress audit output. The upstream-only moderate findings are monitored by CI and must be remediated when a compatible Atlassian dependency resolution becomes available or within any applicable Atlassian Marketplace Security remediation due date. Any high or critical production finding remains a release blocker.

## Vulnerability management

ASHBIZCON follows Atlassian Marketplace cloud-app vulnerability remediation expectations. Security contacts must monitor Atlassian Marketplace Security notifications and maintain current contact information. Known vulnerabilities are triaged by exploitability, affected code path, severity, and upstream ownership; upstream ownership does not remove ASHBIZCON's responsibility to track remediation.

## Reporting

Report suspected vulnerabilities privately to **security@ashbizcon.com**. Do not include real customer PII, tokens, credentials, exported inventories, or authorization headers in reports. Customer-facing response commitments must match the support policy published with the Marketplace listing.
