# matchafinance.com

Landing page for [Matcha Invoices](https://app.matchafinance.com), served from
the root of `matchafinance.com` by GitHub Pages.

Plain static files — no build step, no JavaScript, no dependencies.

```
index.html     the whole page (CSS is inlined in <head>)
404.html       GitHub Pages not-found page
assets/        logo, icons, app screenshots (WebP), og.png (social share image)
CNAME          custom domain for GitHub Pages
.nojekyll      serve files as-is, skip the Jekyll build
robots.txt, sitemap.xml
```

## Preview locally

```bash
python3 -m http.server 4321
```

Then open http://localhost:4321.

## Deploy (GitHub Pages)

1. Push `master` to GitHub.
2. Repo → Settings → Pages → Source: **Deploy from a branch**, `master` / `/ (root)`.
3. DNS for the apex domain: `A` records for `matchafinance.com` to
   `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   (and optionally `www` as a `CNAME` to `<user>.github.io`).
4. Once the certificate is issued, tick **Enforce HTTPS**.

## Notes

- Design tokens (colors, fonts, radii) mirror `web/src/styles.css` in the app
  repo; keep them in sync if the app's look changes.
- The screenshots are real captures of the app's seeded demo company
  (1280×800 @1.5x and 390×844 @2x, WebP). Re-capture them when the UI changes.
- Bump `lastmod` in `sitemap.xml` when the copy changes.
