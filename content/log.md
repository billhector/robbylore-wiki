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

## [2026-05-29] ingest | 10 transcripts cleaned

Pass 2 webclipper cleanup on 10 transcripts in `raw/transcripts/` (all already had bare frontmatter from clipper). Renamed 6 files to collapse double-spaces from stripped `|` delimiters. Rewrote all 10 truncated descriptions. Inferred topic tags (2–5 per file). Bodies untouched.

Files:
- Talk Easy (Sam Fragoso, 2025-12-28)
- Why Won't You Date Me? (Nicole Byer, 2025-02-28)
- The Downside (Gianmarco Soresi, 2025-04-08)
- Blocks (Neal Brennan, 2026-02-19)
- We're Having Gay Sex (Ashley Gavin, 2024-08-05)
- Good For You (Whitney Cummings, 2024-05-15)
- Not Skinny But Not Fat (2026-04-28)
- Call Her Daddy (Alex Cooper, 2026-05-20)
- Etalk (Lainey Lui, 2026-03-28)
- Long Winded (Gabby Windey, 2025-12-18)

## [2026-05-29] compile | Wake Up press tour (10 transcripts)

First wiki compile. Processed all 10 ingested transcripts. Built 31 wiki pages across 5 type folders (no host pages, no episode pages, per user direction).

**People (8):** robby-hoffman (hub, priority high), gabby-windey, uncle-eddie, kaya-hoffman, schmuly-hoffman, john-mulaney, steve-carell, tim-dylan, rob-reiner.

**Projects (7):** wake-up, hacks, the-rooster, too-far, the-chris-gethard-show, after-midnight, i-m-nervous.

**Themes (7):** orthodox-upbringing, family, queerness, money, marriage, dating, canada.

**Bits (6):** one-hot-one-smart, socks-during-sex, testing-god-by-being-gay, proposing-via-crossword, juneteenth-cookout, two-year-decision-rule.

**Career (8):** montreal-flight, accounting-to-standup, hbo-script-sneak, mcdonalds-job, wga-strike-speech, top-surgery, vegas-elopement, losing-the-emmy.

Updated all 5 type-folder `index.md` files. Updated `wiki/index.md` with a "Recently added" block. Flipped `compiled: true` on all 10 raw files.

Known orphan wikilinks intentionally left for future compile passes: rachel-kaly, leanne-morgan, robert-pattinson, dog-nardo, the-bachelorette, the-traitors, dancing-with-the-stars, long-winded, talk-easy, blocks, etalk, not-skinny-but-not-fat, call-her-daddy, baroness-von-sketch, odd-squad, dying-for-sex, pull-rich-men, dora-the-explorer, jesus-loves-me, no-backsies-they-them, supercuts-tuesday, monogamy, identity, wake-up-press-tour. Lint pass will surface these — decide per-link whether to write a stub or strip the wikilink.
