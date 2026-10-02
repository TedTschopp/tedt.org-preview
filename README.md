# TedT.org Information Architecture Preview

Review the proposed site at **https://preview.tedt.org/**.

This is an unlinked public preview hosted on GitHub Pages. Cloudflare supplies only the DNS-only CNAME. Production at https://tedt.org/ remains separate and requires an explicit cutover request.

The navigation groups the site into Essays, Stories & Folklore, Games & Worlds, Tools, Learn, and About. Search and Subscribe are utilities. Plotto is featured as an active project under development.

## Repository Layout

- `site/`: the compiled, deployment-ready preview. Every HTML page is marked noindex; analytics and service-worker delivery are disabled. Existing public media is loaded from tedt.org to keep the preview within GitHub Pages limits.
- `_review/source/`: all changed Jekyll source files, with their original paths.
- `_review/source.patch`: the complete change against the production repository baseline.
- `_review/manifest.json`: baseline and source commit identities.
- `_review/validation.json`: local build, link, browser, and accessibility validation evidence.
- `.github/workflows/pages.yml`: a preview-only Pages deployment. No production publishing, social sync, or scheduled workflows are copied here.

## Review and Rebuild

Start with the home page, follow each section hub, try tool filtering and site search, and open an existing article or assessment. Review on a phone and with the light/dark theme controls.

For source changes, use the isolated `codex/ia-preview` branch in the original Jekyll repository. The source patch can also be applied to the baseline commit recorded in `_review/manifest.json` in a separate checkout. Build with `_config.yml,_config.preview.yml`, run the packager and preview checker in `_review/source/scripts/`, and replace `site/` with the resulting package. See `_review/source/docs/ia-preview.md` for the workflow and cutover instructions.

Do not copy preview configuration into a production deployment. Approval of this preview is separate from a request to cut over tedt.org.
