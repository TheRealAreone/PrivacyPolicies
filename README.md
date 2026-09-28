# PrivacyPolicies

Privacy policy pages for my apps, published with GitHub Pages.

| App | Policy | Store listing |
| --- | --- | --- |
| ScoreSquad (Android, desktop) | [`index.html`](index.html) → <https://therealareone.github.io/PrivacyPolicies/> | Google Play |

## Layout

Each policy is a plain, self-contained HTML page. There is no build step, no CSS or JS
framework, and no external assets — including no web fonts, analytics, or CDN links. A
privacy policy that phones home to load its own stylesheet would contradict its own
text, so nothing on this site makes a network request to a third party.

- `index.html` — the ScoreSquad policy, served at the site root.
- `.nojekyll` — stops GitHub Pages from running the site through Jekyll, so files are
  served exactly as committed.

## Editing

1. Edit `index.html` and commit.
2. GitHub Pages rebuilds automatically; the change is live in under a minute.

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

Once a second app needs a policy, make the root a simple index of links and give each app
its own folder:

```
index.html              # link list
scoresquad/index.html   # move the current page here
anotherapp/index.html
```

Then the ScoreSquad URL becomes
<https://therealareone.github.io/PrivacyPolicies/scoresquad/>, which is fine for a
Play Console listing — update the URL in the listing when you move it.
