# ASHBIZCON AttachOps for Jira — Privacy Notice

Last updated: 7 September 2026

AttachOps for Jira is built on Atlassian Forge. V1 is designed so Jira attachment files are not uploaded to or stored on an external ASHBIZCON file server.

## Data processed for requested features

When an authorized Jira user uses AttachOps, the app may process Jira information available to that user, including project, issue and attachment identifiers; attachment filename, MIME type, size and upload date; related issue keys; uploader information when Jira provides it; and the project/filter/JQL scope selected by the user.

When a user explicitly performs a bulk download, attachment bytes are processed in the current browser session to build the requested archive. When a user explicitly performs guarded cleanup, the app processes the metadata and operation result needed to perform and report that action.

## Where processing occurs

AttachOps uses Atlassian Forge and Jira APIs. V1 does not require an ASHBIZCON-operated external attachment object store, external attachment database, OCR service, AI inference service, or third-party attachment-processing backend.

Bulk ZIP creation and CSV generation occur in the user's browser session.

## Browser-local information

AttachOps may store convenience configuration in browser-local storage, such as recent scan scope and named scan presets. These presets contain query configuration and are not intended to persist attachment binaries or a customer attachment inventory database.

## Jira permissions and Safe Cleanup

Most AttachOps functionality is read-only. The optional Safe Cleanup workflow requires the Jira permission needed to delete an attachment. Cleanup is explicitly initiated, dry-run first, permission checked, metadata revalidated, confirmation gated, and revalidated immediately before deletion. AttachOps does not perform automatic scheduled retention deletion.

## Purpose

Information is processed only to provide requested product functions such as attachment inventory, storage analytics, aging and duplicate-candidate reports, exports, bulk download, reusable scan scopes and guarded cleanup.

## Advertising and sale of data

AttachOps V1 does not include advertising and is not designed to sell Jira customer or end-user data.

## Retention

V1 does not maintain an external ASHBIZCON attachment-content database or file store. Browser-local preferences remain until changed, deleted in the app, or cleared from browser/site storage. Atlassian/Forge platform processing is subject to the applicable Atlassian platform terms and documentation.

## Security

Public security information: https://github.com/thanoswasaswagger/ashbizcon-public/blob/main/SECURITY.md

## Support

Product support: https://github.com/thanoswasaswagger/ashbizcon-public/blob/main/attachops/SUPPORT.md

The legal/business identity and contact information entered in the applicable Marketplace seller profile is the authoritative commercial contact for the published listing.
