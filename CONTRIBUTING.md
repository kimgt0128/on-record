# Contributing

## Goal

Move fast and keep the prototype stable enough for the ideathon demo.

## Branch Naming

Use short branch names:

```text
feature/report-sharing
feature/worker-flow
fix/mobile-layout
docs/demo-script
```

## Commit Style

Use concise commit messages:

```text
Add report sharing demo state
Fix worker tab layout on mobile
Update ideathon README
```

## Pull Request Checklist

Before requesting review:

- Preview the page locally.
- Check both tabs: `기관 관리자`, `요양보호사 앱`.
- Make sure button text does not overflow.
- Keep demo data static unless real backend work is explicitly planned.
- Link the issue in the PR description.

## Working Agreement

- `index.html` is the source of truth for the current prototype.
- Do not edit `.vercel/`; it is local Vercel project metadata.
- Do not add secrets or API keys.
- Prefer simple simulated UI over real infrastructure until after the ideathon.
