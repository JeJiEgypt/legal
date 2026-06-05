# JeJiEgypt — Legal

Privacy policies and terms of service for JeJiEgypt apps, served as static pages via **GitHub Pages**.

The repository is **private**, but the published pages are **publicly reachable** (required so app
stores and end users can open a policy URL without signing in). This works because the JeJiEgypt org
is on the **GitHub Team** plan, which allows Pages to build from private repositories.

## Live site

- Site root: https://jejiegypt.github.io/legal/
- The Alpha — Privacy Policy: https://jejiegypt.github.io/legal/the-alpha/privacy/

## Structure

One folder per app; each document is an `index.html` so the URLs end in a clean trailing slash.

```
legal/
├── index.html              # landing page linking to each app's documents
├── the-alpha/
│   └── privacy/
│       └── index.html      # → /legal/the-alpha/privacy/
└── <app>/
    ├── privacy/index.html  # → /legal/<app>/privacy/
    └── terms/index.html    # → /legal/<app>/terms/ (add only if the app needs terms)
```

## Adding a new app's policy

1. Create `your-app/privacy/index.html` (copy an existing one as a template).
2. Add a link to it in the root `index.html`.
3. Open a pull request (see below). Once merged to `main`, GitHub Pages redeploys automatically.
4. Paste `https://jejiegypt.github.io/legal/your-app/privacy/` into the store listing.

## Conventions

- **Contact email** on all policies: `jejiegypt@gmail.com`.
- Keep each policy **accurate to that app's actual data handling** — write it from a real audit of the
  app, not a generic template.
- **Changes go through a pull request**, not a direct push to `main`.
- This content is **published publicly** — never commit secrets, keys, or private data here.

## Hosting / Pages config

- Pages source: `main` branch, root (`/`).
- Plain static HTML — no build step.
- A custom domain (e.g. `legal.jejiegypt.com`) can later be pointed at this one repo to serve every
  app's documents under a branded domain.
