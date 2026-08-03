# API Spec Converter — public site

The explanation site and hosted app for **API Spec Converter**: a free,
100%-client-side converter between **Swagger 2.0** and **OpenAPI 3.0 / 3.1**.
Nothing is uploaded; every lossy conversion is flagged honestly.

- **Site:** https://sreenivas-sadhu-prabhakara.github.io/apispec-converter/
- **The tool:** https://sreenivas-sadhu-prabhakara.github.io/apispec-converter/app/

## Repo layout

- `public/` — the docs / explanation site, deployed to the **`gh-pages` root**.
- The converter **app** lives at **`/app`** on `gh-pages`. It is built and
  published from the private source repo (`apispec-converter-app`) by its CI —
  the app source is intentionally not in this repo.

## Deploys (single writer per path)

- Push to `main` here → `.github/workflows/pages.yml` publishes `public/` to the
  `gh-pages` root with `keep_files: true`, so it never touches `/app`.
- Push to the private repo's `main` → its CI publishes the built app to
  `gh-pages/app` (also `keep_files: true`).

Because the two pipelines write to disjoint paths and both preserve existing
files, they coexist without clobbering each other.
