# skoperta.github.io

Company website for Skoperta Ltd, served by GitHub Pages from the root of the `main` branch. Plain HTML and CSS: no build step, no JavaScript, no third-party scripts.

## Structure

| Path | Purpose |
|---|---|
| `index.html` | Landing page |
| `privacy/index.html` | Website privacy notice |
| `404.html` | Not-found page (GitHub Pages serves it automatically) |
| `assets/css/style.css` | Design tokens (colours, type, spacing) and layout |
| `assets/favicon.svg` | Site icon |
| `robots.txt` | Crawler permissions |
| `.nojekyll` | Disables Jekyll processing |

## Conventions

- One folder per page with an `index.html` inside, so URLs stay clean (`/privacy/`, `/products/<name>/`).
- Every page links `/assets/css/style.css` and reuses the header and footer markup from `index.html`.
- Change colours, type and spacing through the custom properties at the top of `style.css`, not in page markup.
- Keep the legal footer (registered name, company number, registered office) on every page.
- When adding a product, give it its own folder with `privacy/` and `support/` pages, so app store listings have stable URLs.

## Moving to skoperta.com

1. At the DNS provider, add four `A` records for the apex pointing to GitHub Pages (`185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`; check the current list in the GitHub Pages docs) and a `CNAME` record for `www` pointing to `skoperta.github.io`.
2. In this repository, Settings > Pages, set the custom domain to `skoperta.com` (GitHub commits a `CNAME` file) and tick Enforce HTTPS once the certificate is issued.
3. Verify the domain under the account's Pages settings to prevent takeover.
