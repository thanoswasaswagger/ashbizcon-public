# ASHBIZCON AttachOps for Jira — Documentation

AttachOps is a Forge-native Jira attachment operations and storage-hygiene utility designed around explicit scope, dry-run visibility and safe user-controlled actions.

## Core workflow

1. Open AttachOps in Jira.
2. Select the Jira scope using the supported project, filter or JQL controls.
3. Run the inventory scan.
4. Review attachment counts, storage totals, age and duplicate-candidate insights.
5. Filter/sort the inventory as needed.
6. Export CSV reports or perform a user-requested bulk download.
7. If Safe Cleanup is needed, review the dry run and permission/revalidation information before confirming any deletion.

## Main capabilities

- scoped Jira attachment inventory;
- attachment filename, type, size, age and issue-context reporting;
- storage analytics;
- aging analysis;
- duplicate-candidate analysis based on available evidence;
- CSV export;
- browser-built bulk ZIP download;
- reusable scan scopes/presets;
- guarded Safe Cleanup with dry run, permission checks, metadata revalidation and explicit confirmation.

## Safe Cleanup

Safe Cleanup is not an automatic retention engine. It is an explicitly initiated operation designed to reduce accidental destructive actions. The app checks permissions and revalidates metadata before deletion and surfaces operation results to the user.

Always review the selected scope and dry-run result before confirming a cleanup operation.

## Privacy

AttachOps V1 does not require an ASHBIZCON external attachment file store. Bulk ZIP creation occurs in the browser.

Privacy notice: https://github.com/thanoswasaswagger/ashbizcon-public/blob/main/attachops/PRIVACY.md

## Support

Support policy: https://github.com/thanoswasaswagger/ashbizcon-public/blob/main/attachops/SUPPORT.md
