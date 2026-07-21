# updates.theappfoundry.co

Sparkle appcast feeds for The App Foundry's macOS apps, served over GitHub Pages.

```
catalyst/appcast.xml
```

One folder per app. Binaries are **not** here — they stay as GitHub Release assets on each app's
own releases repo, and the appcast points at those download URLs. This repo holds only the feed,
so it stays small enough to clone instantly.

## Why this exists as its own repo

`SUFeedURL` is compiled into every build and cannot be changed for copies already installed. It
therefore has to point at a hostname that can be repointed forever, independent of where the
binaries or the source happen to live. Catalyst has already been stranded twice by vendor URLs —
a Cloudflare Pages project and a Worker, both since deleted.

A custom domain in front of GitHub Pages means the host can change again without breaking a
single install.

## Publishing

The release script regenerates `<app>/appcast.xml` and pushes. Nothing to deploy.

Verify after a release:

```sh
curl -s https://updates.theappfoundry.co/catalyst/appcast.xml | head
```

## Notes

- `.nojekyll` is required — Jekyll would otherwise process the repo and can drop files.
- `CNAME` binds this repo to the custom domain. Deleting it unpublishes the domain.
- Never commit the Sparkle EdDSA **private** key. It signs the feed and lives in the login
  Keychain; losing it means no existing install can ever verify an update again.
