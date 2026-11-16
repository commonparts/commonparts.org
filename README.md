# commonparts.org

Source for the [commonparts.org](https://commonparts.org) website.

## Structure

```
index.html        # Language selection: redirects to /fr/ or /en/
fr/index.html     # French page (launch language)
en/index.html     # English page
assets/site.css   # Shared styles (Common Parts design system tokens)
assets/fonts/     # Self-hosted IBM Plex (SIL OFL 1.1), no third-party requests
assets/           # Logo exports, favicons, web manifest, social image
symbol.svg        # Logo (site header)
sitemap.xml       # Both language versions, with hreflang alternates
robots.txt
CNAME             # GitHub Pages custom domain
```

Both language pages share the same structure and must be kept in sync. Each declares its equivalent through `hreflang` links.

The root page picks a language from an explicit choice (stored when a visitor uses the language switch), then from the browser language. It never uses geolocation.

## Logo assets

Files in `assets/` are public at `https://commonparts.org/assets/<file>`.
Names follow `commonparts-<kind>-<variant>-<width>x<height>.png`:

- **kind** — `symbol` (the mark alone) or `logo` (mark + "Common Parts")
- **variant** — `color`, `black`, or `white` (for dark backgrounds)

Also included: `commonparts-avatar-*` (profile pictures), `commonparts-og-1200x630.png`
(social preview), `favicon.ico`, `favicon.svg`, `apple-touch-icon.png`,
`commonparts-icon-*` and `site.webmanifest`.

## Content rules

- Keep it short and written for visitors. Internal strategy (CPSP, institutional structure, scope, funding, licensing decisions) stays out of the public site.
- No volatile figures (part or product counts) are hard-coded; the index itself is the source of truth.
- No third-party scripts, fonts or trackers.

## Deployment

The site is deployed via GitHub Pages. Any push to `main` updates the live site.

To preview locally, serve the directory over HTTP (the root redirect and relative paths assume a server):

```bash
git clone https://github.com/commonparts/commonparts.org.git
cd commonparts.org
python3 -m http.server 8000
```

## License

Site source: MIT — see [LICENSE](./LICENSE). Fonts: SIL Open Font License 1.1 — see [assets/fonts/OFL.txt](./assets/fonts/OFL.txt).
