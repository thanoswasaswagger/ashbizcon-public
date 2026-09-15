# ASHBIZCON AttachOps for Jira — Privacy Policy

**Effective date:** 15 September 2026  
**Publisher:** ASHBIZCON

This Privacy Policy explains how **AttachOps for Jira** handles information when used with Atlassian Jira Cloud.

## 1. Summary

AttachOps is built on Atlassian Forge. AttachOps V1 is designed so that Jira attachment data stays within the Atlassian/Jira and current-user browser flow used by the app. V1 does **not** operate an ASHBIZCON-hosted attachment storage service, external attachment database, OCR service, AI inference service, advertising tracker, or unrelated third-party attachment-processing backend.

The app accesses Jira information only to provide features initiated by the user, such as attachment inventory, storage analysis, CSV export, bulk download, saved scan scopes, and guarded attachment cleanup.

## 2. Information the app may access

Depending on the feature used and the current user's Jira permissions, AttachOps may access:

- Jira project, issue, saved-filter and attachment metadata needed to build an attachment inventory and validate scan scope;
- attachment metadata such as filename, MIME type, size, upload date, uploader information, issue key and project association;
- attachment content when the user explicitly starts a download operation;
- Jira permission information needed to determine whether a requested cleanup operation is permitted; and
- the Forge/Marketplace license state needed to enable licensed production functionality.

AttachOps receives only information that Atlassian APIs make available to the current user under that user's Jira permissions.

## 3. How information is used

Information accessed by AttachOps is used to provide requested app functions, including:

- scanning and displaying attachment inventories;
- calculating storage and age summaries;
- identifying metadata-based duplicate candidates;
- generating browser-side CSV exports;
- downloading selected Jira attachments and packaging them into ZIP archives in the current browser session;
- validating Jira permissions and attachment metadata before a user-confirmed deletion; and
- displaying and exporting per-item cleanup outcomes.

AttachOps does not sell Jira customer data and does not use Jira customer content for advertising.

## 4. Storage and retention

### ASHBIZCON-operated storage

AttachOps V1 does not require or use an ASHBIZCON-operated external database or external attachment object store for Jira customer attachments.

### Browser-local storage

The app may use browser local storage to remember limited UI configuration, such as the last scan scope and saved scan presets. Presets may contain configuration values such as Jira project IDs, Jira filter IDs or JQL text. They are not intended to contain attachment binaries or a persistent copy of the full attachment inventory.

Browser-local settings remain under the user's browser profile and can be cleared using normal browser/site-data controls.

### Exports and downloads

CSV files, ZIP archives and cleanup-audit CSV files are generated or delivered to the user's current browser/device when requested. After download, those files are controlled by the user and the user's organization according to their own retention and security practices.

## 5. Attachment deletion

AttachOps includes an optional guarded cleanup workflow. Deletion is user initiated. The app performs dry-run checks, revalidates attachment metadata and Jira permissions, requires explicit confirmation, and then sends the requested delete operation to Jira. Jira remains the authorization authority and source of truth for deletion.

AttachOps V1 does not automatically or on a schedule delete attachments.

## 6. External sharing and third parties

AttachOps V1 does not intentionally send Jira attachment content to an ASHBIZCON-operated external backend or unrelated third-party processing service. The app relies on Atlassian Forge and Jira APIs to provide its functionality. Atlassian's handling of Jira Cloud and Forge data is governed by Atlassian's applicable terms and privacy documentation.

Files downloaded by a user may be handled by the user's browser, operating system, endpoint-security software, network, or organization according to that environment's policies.

## 7. Security

AttachOps follows a least-privilege design. The current V1 app requests Jira read access and the granular attachment-delete permission needed for the optional guarded cleanup feature. Broad Jira write access is intentionally not requested.

See the public AttachOps Security Policy:

https://github.com/thanoswasaswagger/ashbizcon-public/blob/main/attachops/SECURITY.md

## 8. Customer and administrator responsibilities

Jira administrators are responsible for configuring Jira permissions, deciding which users may install or use the app, determining appropriate scan and cleanup scope, and ensuring that exports/downloads are handled according to their organization's policies and legal obligations.

Users should not place secrets, credentials, unrelated sensitive personal information, or customer content into public support reports.

## 9. Privacy rights and requests

Because AttachOps V1 does not maintain an ASHBIZCON-operated external customer-content database, requests concerning Jira content should normally be handled through the customer's Jira Cloud organization and Atlassian controls.

For an AttachOps-specific privacy question or request, use the public support channel below without posting confidential or customer data. Sensitive security matters should use GitHub's private vulnerability-reporting/security-advisory channel where available.

## 10. Children

AttachOps is an enterprise/workplace Jira administration tool and is not directed to children or designed as a consumer service for children.

## 11. Changes to this policy

This policy may be updated when AttachOps features, data flows, subprocessors or legal requirements change. Material changes will be reflected in this document with an updated effective date.

## 12. Contact and support

Publisher: **ASHBIZCON**

Public support information:

https://github.com/thanoswasaswagger/ashbizcon-public/blob/main/attachops/SUPPORT.md

For non-sensitive policy questions, use the support channel without posting customer data. For security vulnerabilities, follow the private reporting instructions in the AttachOps Security Policy.
