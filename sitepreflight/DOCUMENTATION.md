# ASHBIZCON SitePreflight — Documentation

ASHBIZCON SitePreflight is a deterministic release-preflight plugin for Framer. It helps reviewers inspect evidence-backed link, accessibility, structure, image, form, and responsive-layout risks before publishing a site.

## Core workflow

1. Open SitePreflight in a Framer project.
2. Choose **All pages** or **Current page** scope.
3. Run the scan.
4. Review the readiness score together with audit coverage.
5. Filter findings by severity, confidence, category, page, or text.
6. Open a finding to see evidence, impact, recommended action, and limitations.
7. Use **Focus in Framer** when supported to navigate back to the affected layer.
8. Rescan after fixes.
9. Export HTML, CSV, or JSON reports locally when needed.

## What SitePreflight checks

Depending on the evidence exposed by the current Framer Plugin API, SitePreflight can evaluate:

- project-local link resolution, including relative paths;
- readable exact and wildcard Framer redirects;
- external destination inventory without pretending to prove remote availability;
- exposed image layers with missing alternative text;
- image source-resolution oversizing using intrinsic-versus-rendered dimensions;
- available breakpoint geometry for possible overflow risk;
- page-aware heading structure from exposed semantic/Text Style tag evidence;
- conservative probable-form/completion evidence;
- audit coverage and limitations for checks that cannot be evaluated reliably.

## Important limitations

SitePreflight is conservative by design. It does not invent facts the Framer Plugin API does not expose.

Current V1 does not claim to statically prove:

- page SEO title/description values when those values are not exposed to the plugin;
- final encoded image transfer byte size;
- arbitrary custom form runtime behavior;
- final responsive behavior in every browser/device;
- live reachability of arbitrary external websites.

Those checks are shown as limited/not evaluated or as clearly labelled heuristics instead of being silently treated as passes.

## Privacy

SitePreflight does not require an ASHBIZCON account or an ASHBIZCON backend. Project content is not uploaded to ASHBIZCON, and generated reports are created locally.

Privacy policy: https://github.com/thanoswasaswagger/ashbizcon-public/blob/main/sitepreflight/PRIVACY.md

## Support

Support policy: https://github.com/thanoswasaswagger/ashbizcon-public/blob/main/sitepreflight/SUPPORT.md
