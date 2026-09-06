# ASHBIZCON BulkOps for Confluence — Security

Last updated: 6 September 2026

## Security model

BulkOps is implemented on Atlassian Forge and uses Atlassian-hosted compute and Forge storage. Marketplace V1 declares no ASHBIZCON-hosted content database, analytics service, advertising service, or AI provider.

The app requests only the Confluence scopes required for its reviewed V1 behavior: page/space/label reads, content-permission reads, page and label writes, recoverable page deletion, and Forge app storage.

## Mutation safety

BulkOps uses server-authoritative preflight, current-user permission checks, version snapshots, explicit confirmation, bounded execution, classified errors, retry/backoff, failed-only retry, durable operation state, and audit results. Trash operations use Confluence's recoverable delete behavior. BulkOps V1 does not generate permanent-purge requests.

## Data minimization

The app is designed not to persist page bodies, attachments, comments, credentials, authorization headers, or raw upstream response bodies in Forge Storage. See the public privacy notice for the bounded operational metadata that is retained.

## Vulnerability handling

ASHBIZCON treats suspected unauthorized mutation, cross-tenant access, credential exposure, permanent-deletion behavior, and data-integrity failures as high-priority security incidents.

Do **not** publish exploit details, secrets, tokens, private customer data, or reproducible attack instructions in a public GitHub issue. For non-sensitive security concerns, create a minimal issue at:

https://github.com/thanoswasaswagger/ashbizcon-public/issues

For sensitive reports, use the private security/emergency contact published in the Atlassian Marketplace partner profile once the listing is available. If a public issue is used only to establish contact, include no exploit details or customer-sensitive data.

## Dependency and release controls

The BulkOps release pipeline runs formatting, linting, strict TypeScript checks, automated tests with coverage, a production build, static release-readiness checks, and an npm high/critical vulnerability audit before release deployment.

No security certification, compliance badge, SLA, or Atlassian partner status is claimed unless separately evidenced in the Marketplace listing.
