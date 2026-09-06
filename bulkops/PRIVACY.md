# ASHBIZCON BulkOps for Confluence — Privacy Notice

Last updated: 6 September 2026

## Scope

ASHBIZCON BulkOps for Confluence is a Forge-native bulk page operations utility. It is designed to minimize retained customer data and does not require an ASHBIZCON-hosted content database, analytics service, advertising service, or AI provider.

## Data processed

BulkOps may process Confluence metadata required for discovery, preview, authorization, execution, recovery, and audit, including page/content IDs and titles, space identifiers and names, parent identifiers, content type/status, labels, available owner/actor identifiers, modified timestamps, version numbers, current-user permission outcomes, operation IDs, timestamps, action type, result/error categories, and filter/preset values deliberately saved by the user.

BulkOps may briefly receive page data from Atlassian APIs when required for a supported operation. Marketplace V1 is designed not to persist page bodies, attachments, or comments in Forge Storage.

## Data retained

BulkOps uses Atlassian Forge-hosted storage for bounded operational state:

- latest 20 scalable selection jobs and their target-ID chunks;
- latest 50 scalable preflights and reviewed metadata chunks;
- up to 250 completed operation-history entries with lightweight item results needed for audit/retry; and
- saved discovery presets until the user deletes them or installation data is removed.

Oldest indexed artifacts are removed as these bounded limits are exceeded. Pending input chunks are removed as they are consumed. Customers needing long-term evidence should export the deterministic CSV audit before older records are evicted.

## Data deliberately not retained

BulkOps does not intentionally persist page bodies, attachments or attachment contents, comments, passwords, API tokens, cookies, authorization headers, raw upstream HTTP response bodies, advertising identifiers, or AI prompts/model outputs.

## Data movement and hosting

BulkOps V1 declares no ASHBIZCON external content database or remote content processor. Application compute and persistent application storage use Atlassian Forge. Atlassian platform terms, infrastructure, subprocessors, and supported data-residency behavior therefore apply to the Forge services used by the app.

## Customer controls

Users can delete saved presets, export preview/operation CSV evidence, and uninstall BulkOps. Atlassian controls Forge installation-data retention/recovery behavior following uninstall. Requests involving personal-data access, correction, or erasure will be handled consistently with applicable law and Atlassian Forge requirements.

## Support and privacy requests

Do not send page bodies, credentials, tokens, cookies, or confidential attachments in a support request. Use the public ASHBIZCON support tracker and provide only safe metadata such as app version, operation ID, timestamp/timezone, expected versus observed behavior, and a redacted audit export when useful:

https://github.com/thanoswasaswagger/ashbizcon-public/issues

This notice describes the implemented BulkOps V1 data behavior. Marketplace listing disclosures must remain consistent with the deployed version.
