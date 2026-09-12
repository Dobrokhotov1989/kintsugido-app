# kintsugido-app

The deployable build of **Kintsugido** — a personal training log and programme
reference that works offline, installed to a phone's home screen.

**This repository holds built assets only.** No source code, no training data,
no personal data. It exists because GitHub Pages on a free account serves
**public** repositories only, so the published app had to be separated from
everything private. That separation is the point, not an inconvenience.

Licensed **MIT** (see [`LICENSE`](LICENSE)). The bundle also contains other
people's code — see *Third-party notices* below.

---

## What is in here, and what must never be

**Here:** `index.html`, `sw.js` (the service worker), `manifest.webmanifest`,
`assets/` (one hashed JS file and one hashed CSS file), `icons/` — nine files
from one build.

**Never here:** any log entry, activity, pain score, profile, programme content,
exercise photograph, or `.fit` file. Not one line. Personal data lives in a
separate **private** repository that this app reads and writes over the GitHub
API with a token you paste into the app at runtime; the token is never committed
anywhere and never leaves your device except as an API header.

The build step in the source repository fails if it finds data-repository
content in the artifact. If that check ever fires, something is wrong with the
build — do not disable it to ship a release.

---

## Setting it up

Six steps, in order. Steps 1–2 are one-off; step 3 repeats on every release.

### 1. Enable GitHub Pages

**Settings → Pages → Build and deployment → Source: _Deploy from a branch_ →
Branch: `main`, folder `/ (root)` → Save.**

This is possible as soon as the repository has a branch with at least one file —
which it does, so you can do it now, before any build is committed. Pages will
serve this README as the site until an `index.html` exists, which is harmless.

The site appears at:

```
https://<your-github-username>.github.io/kintsugido-app/
```

Note the **subpath**. The app is built with relative asset URLs precisely so
that it works there without configuration, and it uses a hash router (`#/today`)
because Pages has no URL-rewriting — so there is no `404.html` trick to set up
and nothing to configure per-URL. If you ever see a blank page with 404s for
`/assets/…` in the browser console, the build was made with an absolute base and
is wrong; rebuild rather than patching the HTML.

### 2. Add a `.nojekyll` file

Create an empty file named `.nojekyll` in the root of this repository.

Pages runs Jekyll over a site by default, and Jekyll **silently ignores files
and folders whose names begin with an underscore**. Nothing in the current build
starts with one, so this changes nothing today — it is here so that a future
build cannot lose a file to a rule nobody remembered. It costs one empty file.

### 3. Commit a build

In the source repository:

```bash
npm ci
npm run build
```

That writes `packages/app/dist/`. Copy the **contents** of `dist/` — not the
folder itself — into the root of this repository, replacing what is there, and
commit.

Two things worth knowing:

- **No build runs on GitHub.** There is no Actions workflow and there is not
  meant to be one; you are committing the output of a build you ran and can
  inspect. That is deliberate — it keeps the deployed bytes something a person
  chose rather than something a pipeline produced.
- **Two consecutive builds are byte-identical**, so a `git status` showing no
  change after a rebuild means the source did not change, not that the copy
  failed.

The asset filenames contain a content hash, so old files accumulate unless you
delete them. Replacing the whole `assets/` folder each time is simplest.

### 4. Third-party notices — **not generated yet**

The bundle includes Preact (MIT), Observable Plot and `idb` (ISC), several d3
modules (ISC / BSD) and `robust-predicates` (Unlicense). MIT, ISC and BSD all
require their copyright notice and permission text to travel with distributed
copies, so a `THIRD-PARTY-NOTICES.md` in this repository is an obligation, not a
courtesy.

**It does not exist yet, and the deploy is not licence-complete without it.**
This is a known gap, recorded rather than glossed over. It needs generating from
the lockfile before this app is shared with anyone else. Your own use is not
what the requirement is about.

### 5. Set up your first device

Once a build is committed and Pages is live:

1. Open the site on the phone.
2. Install it to the home screen (iOS: Share → *Add to Home Screen*; Android:
   the browser's *Install app* prompt).
3. Open it from the home screen and complete setup: the private data
   repository's owner, name and branch, plus the token.

**Setup needs one connection, and it is not optional.** The app reads
`profile.json` from your data repository during setup and stores the profile id
it finds. That is what lets every entry you log afterwards be filed under the
right person without you ever typing an id — and it is why a device that has
never been set up cannot log anything yet. After setup, the app logs fully
offline, with no token, indefinitely.

So the order matters: **your data repository must already contain a
`profile.json`** before a device can be set up. An empty repository will refuse,
with a sentence saying so.

### 6. Check it actually works offline

Not a formality — this is the property the whole design exists for.

1. Open the installed app and let it load fully.
2. Turn on aeroplane mode, or switch off Wi-Fi **and** mobile data.
3. Close the app completely and reopen it from the home screen.

It should open, show your content, and say plainly that it is not syncing. If it
shows a browser error page instead, the service worker did not install — check
that `sw.js` is present at the root of this repository and that the site is
served over HTTPS (Pages always is).

---

## Notes that will save you time

- **Platform floor: iOS 18.4.** Below that, the screen-wake-lock the session
  timer needs is broken in installed web apps. Android has no such floor.
- **Updating an installed app.** A service worker serves the old version until
  the new one takes over. Closing and reopening the app is usually enough; if it
  looks stale, open the site in a normal browser tab, reload, then reopen the
  installed app.
- **The token expires.** Fine-grained GitHub tokens have a maximum lifetime. When
  yours lapses, syncing stops and the app says so — **logging keeps working**.
  Paste a new token in Settings when convenient.
- **Nothing here phones home.** No analytics, no telemetry, no crash reporting,
  no fonts or scripts fetched from anyone else's server at runtime. The only
  network requests the app makes are to the GitHub API for your own repository.

## What is deliberately not here

- **The source.** It lives in a separate private repository, along with the
  specification, the architecture decisions and the tests.
- **Any data.** See above.
- **Continuous integration.** No workflow builds, tests or deploys this. The
  absence is a decision, not an omission.
