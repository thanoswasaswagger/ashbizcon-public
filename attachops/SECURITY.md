# ASHBIZCON AttachOps for Jira — Security Policy

**Effective date:** 15 September 2026  
**Publisher:** ASHBIZCON

This document describes the security model and vulnerability-reporting process for **AttachOps for Jira**.

## 1. Supported release

Security support targets the current AttachOps for Jira V1 Marketplace release and subsequent maintained updates.

## 2. Reporting a vulnerability

Please do **not** disclose security vulnerabilities in a public GitHub issue.

Use GitHub's private vulnerability-reporting / security-advisory channel for the AttachOps repository when available. If a private channel is unavailable, use the public support channel only to request private contact and include **no exploit details, customer data, attachment content, credentials, API tokens, secrets, or personally identifiable information**.

A useful private report should include:

- a concise description of the issue;
- the affected AttachOps version, if known;
- reproduction steps;
- expected and actual behavior;
- likely security impact; and
- any safe proof-of-concept details required to understand the issue.

Please test only systems and data that you own or are explicitly authorized to test.

## 3. Security architecture

AttachOps V1 is designed around these boundaries:

- Jira access is mediated through Atlassian Forge and Jira APIs.
- The app requests `read:jira-work` and the granular `delete:attachment:jira` scope.
- Broad `write:jira-work` access is intentionally not requested.
- Safe Cleanup is user initiated and guarded by dry-run review, Jira permission checks, metadata revalidation and exact confirmation.
- No automatic or scheduled attachment deletion is implemented.
- No ASHBIZCON-operated external attachment object store, external attachment database, OCR service, AI inference service, or unrelated third-party attachment-processing backend is required by V1.
- Product code is checked in CI for unexpected external networking and unsafe destructive-operation patterns.

## 4. Data handling

Attachment metadata and content are accessed through Atlassian Jira/Forge APIs according to the current user's Jira permissions.

Bulk-download content is requested only when a user explicitly starts a download. ZIP packaging is performed in the current browser session. AttachOps V1 does not intentionally copy Jira attachment content into an ASHBIZCON-operated external file store.

## 5. Destructive-operation safeguards

Attachment deletion is the only destructive V1 operation. The workflow is designed so that:

1. the cleanup target must be explicitly selected or intentionally narrowed;
2. a dry run re-reads Jira metadata;
3. current Jira delete permissions are checked in issue context;
4. changed, missing, blocked and errored rows are excluded;
5. exact typed confirmation is required;
6. metadata and permissions are revalidated immediately before each delete;
7. delete requests execute sequentially;
8. destructive requests are not automatically retried; and
9. per-row outcomes can be exported for audit.

Jira remains the authorization authority and source of truth for delete operations.

## 6. Dependency and release security

- High or critical runtime dependency findings require review before release.
- Dependency updates must pass the app's automated test/build/safety pipeline.
- Forced dependency upgrades that could bypass compatibility review are not applied automatically.
- Release validation includes Forge/Jira checks that cannot be fully replaced by credential-free CI.

## 7. Security response

ASHBIZCON will review credible vulnerability reports, attempt to reproduce the issue, assess severity and affected versions, and prepare a fix or mitigation where appropriate.

Public disclosure should be coordinated so customers have a reasonable opportunity to update or apply mitigations before detailed exploit information is published.

## 8. Privacy

See the public AttachOps Privacy Policy:

https://github.com/thanoswasaswagger/ashbizcon-public/blob/main/attachops/PRIVACY.md

## 9. Support

Public support information:

https://github.com/thanoswasaswagger/ashbizcon-public/blob/main/attachops/SUPPORT.md

For security vulnerabilities, do not place sensitive technical details in the public support channel.
