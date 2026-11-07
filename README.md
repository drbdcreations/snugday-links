# Snugday links site

Static files for `https://app.drdbcreations.com` (D2-119), published from the public repository `drbdcreations/snugday-links` with GitHub Pages. Edit them in `tool/links_site/` of the app repository, then copy them there. Keep this site free of analytics and third-party scripts: invite links contain a private token.

- `.well-known/assetlinks.json`: lets Android open invite links in the app. It lists the debug signing key and, since 2026-11-04, the upload key's SHA-256 (D2-150); once Play App Signing issues the app signing certificate, add that fingerprint too, since installs from Play are signed with it.
- `index.html`: where email confirmation links land, so this address must stay Supabase's Site URL (D2-135). It says "confirmed" or "didn't work" from what Supabase adds to the link, and otherwise just "Snugday".
- `404.html`: GitHub Pages serves it for `/invite/<token>`. It shows when the app didn't open the link.
- `.well-known/apple-app-site-association`: lets iPhone open invite links in the app (team `LSFZ688TNU`, the team of the KAL Foundry signing certificates on the release Mac; confirm it matches the App Store Connect team before the first upload). It has no file extension on purpose, as Apple requires.
- `support/`: the support page App Store Connect asks for, with the team's email address.
- `privacy/` and `terms/`: the privacy policy and terms of use (D2-147), generated from `legal/*.md` by `dart run tool/legal_site.dart` in the app repository; never edit the HTML by hand. English at the folder root, Spanish, French, Chinese and Portuguese under `es/`, `fr/`, `zh/` and `pt/`. The English page sends a browser set to one of those languages to its translation once; `?lang=en` keeps English. The app links `https://app.drdbcreations.com/privacy/` and `/terms/`.
