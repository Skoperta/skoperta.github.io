# skoperta.github.io

Company website for Skoperta Ltd, served by GitHub Pages from the root of the `main` branch at https://skoperta.github.io/ (moving to https://skoperta.com/, see below). Plain HTML and CSS: no build step, no JavaScript, no third-party scripts, no cookies.

## Structure

| Path | Purpose |
|---|---|
| `index.html` | Landing page: what we do, how we work, contact |
| `privacy/index.html` | Privacy notice (website, email, products) |
| `404.html` | Not-found page (GitHub Pages serves it automatically) |
| `assets/css/style.css` | Design tokens (colours, type, spacing) and layout, shared by every page |
| `assets/favicon.svg`, `assets/favicon.png`, `assets/apple-touch-icon.png` | Site icons |
| `robots.txt`, `sitemap.xml` | Crawler permissions and page list |
| `.nojekyll` | Disables Jekyll processing |

## Conventions

- One folder per page with an `index.html` inside, so URLs stay clean (`/privacy/`, `/products/<name>/`).
- Every page links `/assets/css/style.css` and reuses the header and footer markup from `index.html`. Mark the current page's nav link with `aria-current="page"`.
- Change colours, type and spacing through the custom properties at the top of `style.css`, not in page markup.
- Keep the legal footer (registered name, company number, registered office) on every page.
- Absolute URLs appear only in the `<head>` of each page (canonical, Open Graph, JSON-LD), in `sitemap.xml` and in `robots.txt`. Change them together when the domain moves.
- When the privacy notice changes, update its "Last updated" date and the `lastmod` in `sitemap.xml`.

## Adding a product

Create `products/<slug>/index.html` with `products/<slug>/privacy/index.html` and `products/<slug>/support/index.html` alongside it, copying the header and footer from `index.html`, then add the new URLs to `sitemap.xml`. App store forms then point at stable URLs: `/products/<slug>/privacy/` for the privacy policy and `/products/<slug>/support/` for support.

## Moving to skoperta.com

1. At the DNS provider, add four A records for the apex pointing to GitHub Pages (185.199.108.153, 185.199.109.153, 185.199.110.153, 185.199.111.153; check the current list in the GitHub Pages docs) and a CNAME record for `www` pointing to `skoperta.github.io`.
2. In this repository, Settings > Pages, set the custom domain to `skoperta.com` (GitHub commits a `CNAME` file) and tick Enforce HTTPS once the certificate is issued.
3. Verify the domain under the account's Pages settings to prevent takeover.
4. Replace `https://skoperta.github.io/` with `https://skoperta.com/` in the `<head>` of each page, in `sitemap.xml` and in `robots.txt`.

## Company details used on the site

Skoperta Ltd, registered in England and Wales, company number 17570656. Registered office: 71-75 Shelton Street, Covent Garden, London WC2H 9JQ. Contact: hello@skoperta.com.
