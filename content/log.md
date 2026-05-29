---
title: Activity Log
description: Append-only record of operations on the Robby Lore wiki — compiles, queries, lint passes.
publish: true
---

# Activity Log

Append-only chronological record. Every compile, query, and lint pass logs here.

## [2026-05-29] init | wiki scaffolded

Initial structure created:
- `content/index.md` — site homepage
- `content/people/`, `projects/`, `episodes/`, `bits/`, `themes/`, `career/` — type folders, each w/ `index.md` landing page
- `content/log.md` — this file

Quartz scaffold + Cloudflare Pages deploy pipeline set up. Domain robbylore.org → Cloudflare. Vault at `~/ObsidianVaults/robbylore/` with private `raw/` (billhector/robbylore-raw) + public wiki (billhector/robbylore-wiki, symlinked via Quartz content/).

No raw sources ingested yet. No wiki articles compiled yet. Ready for first clips.
