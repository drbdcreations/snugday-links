# Snugday links site

Static files for `https://app.drdbcreations.com` (D2-119), published from the public repository `drbdcreations/snugday-links` with GitHub Pages. Edit them in `tool/links_site/` of the app repository, then copy them there. Keep this site free of analytics and third-party scripts: invite links contain a private token.

- `.well-known/assetlinks.json`: lets Android open invite links in the app. It lists the debug signing key for now; add the release key's SHA-256 before release.
- `404.html`: GitHub Pages serves it for `/invite/<token>`. It shows when the app didn't open the link.
- `apple-app-site-association` is not here yet. It needs the Apple Team ID.
