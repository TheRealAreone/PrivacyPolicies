# PrivacyPolicies

Privacy policy pages for my apps, published with GitHub Pages.

| App | Policy | Store listing |
| --- | --- | --- |
| ScoreSquad (Android, desktop) | [`scoresquad/index.html`](scoresquad/index.html) → <https://therealareone.github.io/PrivacyPolicies/scoresquad/> | Google Play |

## Layout

Each policy is a plain, self-contained HTML page. There is no build step, no CSS or JS
framework, and no external assets — including no web fonts, analytics, or CDN links. A
privacy policy that phones home to load its own stylesheet would contradict its own
text, so nothing on this site makes a network request to a third party.

- `index.html` — the site root: an index of links, one per app.
- `scoresquad/index.html` — the ScoreSquad policy.
- `.nojekyll` — stops GitHub Pages from running the site through Jekyll, so files are
  served exactly as committed.

Each policy carries its own copy of the stylesheet rather than sharing a site-wide one.
That keeps a policy page working even if it is served on its own, and a policy that
shared a stylesheet would make a network request for its own appearance, which
contradicts what it says about itself.

## Editing

1. Edit the app's `index.html` and commit.
2. GitHub Pages rebuilds automatically; the change is live in under a minute.

When a policy moves to a new path, update the app's store listing with the new URL in
the same commit. Google Play does not follow redirects, so the old URL will stop
working for anyone who saved it.

If a policy's facts ever change (a new SDK, a permission, a data flow), update the page
in the same commit as the code change so the published claim stays true.

Only state what is true and checkable. The ScoreSquad page once described the app as
"open-source" and linked to the ScoreSquad repo so readers could audit it — but that repo
is private, so the claim was false and the link led nowhere. It now points readers at
Android's app info permission list, which anyone can check without a repo. If ScoreSquad
is ever made public, a licence still has to be added: a public repo with no `LICENSE` is
source-available, not open source.

Google Play requires only a **publicly reachable policy URL**. It does not require the app
source to be public, so a policy in this repo is enough on its own.

## Adding another app

Give the app its own folder and add a row to the table and a link to the root index:

```
index.html                  # link list
scoresquad/index.html
anotherapp/index.html
```

Name the folder after the app in lowercase, which keeps the URL predictable and avoids
case-sensitivity problems on GitHub Pages: a request for `ScoreSquad/` may or may not
resolve depending on how it is cached.
