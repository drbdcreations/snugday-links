# Snugday links site

Static files for `https://app.drdbcreations.com` (D2-119), published from the public repository `drbdcreations/snugday-links` with GitHub Pages. Edit them in `tool/links_site/` of the app repository, then copy them there. Keep this site free of analytics and third-party scripts: invite links contain a private token.

- `.well-known/assetlinks.json`: lets Android open invite links in the app. It lists the debug signing key for now; add the release key's SHA-256 before release.
- `index.html`: where email confirmation links land, so this address must stay Supabase's Site URL (D2-135). It says "confirmed" or "didn't work" from what Supabase adds to the link, and otherwise just "Snugday".
- `404.html`: GitHub Pages serves it for `/invite/<token>`. It shows when the app didn't open the link.
- `apple-app-site-association` is not here yet. It needs the Apple Team ID.
- `privacy/` and `terms/`: the privacy policy and terms of use (D2-147), generated from `legal/*.md` by `dart run tool/legal_site.dart` in the app repository; never edit the HTML by hand. English at the folder root, Spanish, French and Chinese under `es/`, `fr/` and `zh/`. The English page sends a browser set to one of those languages to its translation once; `?lang=en` keeps English. The app links `https://app.drdbcreations.com/privacy/` and `/terms/`.
