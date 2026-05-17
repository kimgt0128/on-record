# on-record

CareLink AI Agent prototype for the LIKELION ideathon.

Production: https://idea-black-two.vercel.app

## What This Is

This is a lightweight static HTML demo. It is intentionally built as a visual prototype, not a production app.

The current demo shows:

- Organization admin dashboard
- Care worker mobile app flow
- AI visit report demo
- Protection event and evidence collection demo
- Agent reasoning-style animations

## Project Structure

```text
.
├── index.html          # Main prototype: HTML, CSS, demo data, and JS
├── vercel.json         # Vercel static deployment settings
├── .vercelignore       # Files excluded from Vercel deployments
└── .github/            # Issue, PR, and CI collaboration setup
```

Local reference documents may exist in `docs/`, but they are intentionally excluded from the public repository.

## Local Preview

Run a static server from the project root:

```bash
python3 -m http.server 4173
```

Then open:

```text
http://127.0.0.1:4173
```

## How To Edit

Most changes happen in `index.html`.

Useful anchors:

- Page metadata and submission branding: top of `index.html`
- Admin/worker tab switching: `switchMode`
- Admin demo data: `EVENTS`, `REPORTS`, `STAFF`
- Admin dashboard UI: `renderDashboard`
- Worker app login flow: `buildLogin`
- Worker visit flow: `buildVisit`

Keep changes small and demo-focused. If a feature only needs to look real for the ideathon, use static demo data and simulated interactions.

## Collaboration Flow

1. Create an issue for the feature or bug.
2. Create a branch from `main`.
3. Edit `index.html` or docs.
4. Preview locally.
5. Open a pull request and link the issue.
6. Review the Vercel preview deployment.
7. Merge to `main` when the demo looks good.

## Deployment

This project is already deployed on Vercel.

Current production URL:

```text
https://idea-black-two.vercel.app
```

After the GitHub repository is connected to Vercel, pull requests should get preview deployments automatically and merges to `main` should update production.
