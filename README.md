# commonparts.org

Source for the [commonparts.org](https://commonparts.org) website, the public presentation of Common Parts Access: an open index of 3D-printable spare parts, organised by appliance.

## Structure

```
index.html        # Language selection: redirects to /fr/ or /en/
fr/index.html     # French page (launch language)
en/index.html     # English page
assets/site.css   # Shared styles (Common Parts design system tokens)
assets/fonts/     # Self-hosted IBM Plex (SIL OFL 1.1), no third-party requests
symbol.svg        # Logo and favicon
sitemap.xml       # Both language versions, with hreflang alternates
robots.txt
CNAME             # GitHub Pages custom domain
```

Both language pages share the same structure and must be kept in sync. Each declares its equivalent through `hreflang` links.

The root page picks a language from an explicit choice (stored when a visitor uses the language switch), then from the browser language. It never uses geolocation.

## Content rules

- The site presents the community index only. Frozen work (CPSP, certified printer network, certification, institutional structure) does not appear on any public page.
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

Site source: MIT — see [LICENSE](./LICENSE). Fonts: SIL Open Font License 1.1 — see [assets/fonts/OFL.txt](./assets/fonts/OFL.txt). Index data published by Common Parts Access: CC BY-SA 4.0.
