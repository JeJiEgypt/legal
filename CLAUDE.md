# CLAUDE.md — JeJiEgypt/legal

Guidance for AI agents (and humans) working in this repository.

## What this repo is

A collection of **static HTML legal documents** (privacy policies, and terms of service where needed)
for JeJiEgypt's apps, published via **GitHub Pages**. There is **no build step** — the HTML in `main`
is served as-is.

- Repo is **private**; the published Pages site is **public** (intentional — store review and end users
  must reach policy URLs without authenticating). Enabled by the org's **GitHub Team** plan.
- Pages source: `main` branch, root (`/`). Merging to `main` auto-redeploys (~30–60s).

## Layout convention

One folder per app, each document as `index.html` for clean trailing-slash URLs:

```
<app>/privacy/index.html   →  https://jejiegypt.github.io/legal/<app>/privacy/
<app>/terms/index.html     →  https://jejiegypt.github.io/legal/<app>/terms/
```

When one app ships to **two stores whose behaviour differs**, add a platform sub-page instead of hedging
a single document to cover both — a store reviewer compares the policy against *that* platform's app:

```
<app>/privacy/index.html            →  .../legal/<app>/privacy/             (original / default platform)
<app>/privacy/<platform>/index.html →  .../legal/<app>/privacy/<platform>/  (e.g. windows)
```

Each page names the platform it covers and links to its sibling. Currently `cats-up/privacy/` is the
**macOS** (Mac App Store) policy and `cats-up/privacy/windows/` is the **Windows** (Microsoft Store) one.

The root `index.html` is a landing page that links to every app's documents — update it when adding an
app or a platform variant.

## Rules

- **Open a pull request** for every change; do **not** push directly to `main`.
- **Public content** — never commit secrets, API keys, tokens, or private data. Anything here is
  world-readable via Pages.
- **Contact email** on all documents: `jejiegypt@gmail.com`.
- Write each privacy policy from a **real audit of that app's code** (permissions, network, storage,
  SDKs, backup behavior) — do not ship a generic boilerplate policy. State only what is true for that app.
- Keep the **"Last updated"** date current whenever a policy's substance changes.

## Adding or updating a policy

1. Branch off `main`.
2. Add/edit `<app>/privacy/index.html` (copy `the-alpha/privacy/index.html` as a starting template).
3. Link it from the root `index.html` if new.
4. Open a PR. After merge, verify the live URL serves the change before using it in a store listing.

## Related

- `the-alpha` app: published to Google Play; uses https://jejiegypt.github.io/legal/the-alpha/privacy/
  as its privacy-policy URL.
