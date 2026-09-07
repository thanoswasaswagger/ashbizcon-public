# ASHBIZCON SitePreflight — Privacy

Last updated: 7 September 2026

ASHBIZCON SitePreflight is a local-first Framer plugin designed to run its release-preflight checks inside the Framer plugin client.

## Data handling

- ASHBIZCON does not operate a backend for SitePreflight.
- Project content is not uploaded to ASHBIZCON.
- No ASHBIZCON account is required.
- SitePreflight does not use an ASHBIZCON analytics or telemetry service.
- SitePreflight does not call an AI service.
- Generated HTML, CSV and JSON reports are created locally in the plugin/browser environment and downloaded by the user.

## Framer platform access

SitePreflight reads only the project information made available through the Framer Plugin API that is required for its deterministic checks. Where the current Framer Plugin API does not expose a fact reliably, SitePreflight marks the corresponding check as limited or not evaluated rather than guessing.

## Customer content

Do not send confidential project content, private URLs, credentials, access tokens or unsanitized exported reports in support requests.

## Changes

If SitePreflight's architecture or data handling changes in a future release, this policy will be updated before those changes are represented in Marketplace disclosures.

## Support

Product support information: https://github.com/thanoswasaswagger/ashbizcon-public/blob/main/sitepreflight/SUPPORT.md
