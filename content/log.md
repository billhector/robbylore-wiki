---
title: Activity Log
description: Reverse-chronological record of operations on the Robby Lore wiki — compiles, queries, lint passes.
publish: true
---

# Activity Log

Reverse-chronological record (newest first). Every compile, query, and lint pass logs here.

## [2026-05-30] lint | Wiki audit

Full structural + content lint. Findings: 26 broken wikilinks (top: `projects/talk-easy` ×5, `bits/no-backsies-they-them` ×4, `projects/long-winded` ×3), 19 articles missing `## Key Takeaways`, 0 orphans, 0 uncompiled raws, 0 thin articles, 0 raw-wikilinks-in-body, all type indexes complete. Report saved to `output/lint-report-2026-05-30.md` (private repo only).

**Fixes applied (same day):** stripped 5 tangential broken links (themes/identity, people/robert-pattinson, people/leanne-morgan, people/horatia-harrod, career/wake-up-press-tour); created 22 stub pages (12 projects, 6 bits, 3 people, 1 theme) covering all remaining broken targets; added `## Key Takeaways` sections to 19 articles.

## [2026-05-29] compile | Robby Hoffman: 'I have the world's worst Rolex' (FT "Aesthete")

Compiled the FT 2026-05-07 "Aesthete" profile by Horatia Harrod. Source: raw/articles/2026-05-29 Robby Hoffman I have the worlds worst Rolex.

**Created (3):**
- people/nathan-letovsky — Robby's grandfather. Includes a contradiction callout: earlier transcripts used the phonetic "Lubovski"; FT print canonicalizes to "Letovsky."
- bits/multiples-of-18 — Jewish "chai = 18 = life" numerology, applied to negotiation.
- bits/cost-per-wear — Rolex amortization bit.

**Updated (10):**
- people/robby-hoffman (substantial — added Possessions inventory section, sister Devorah, cat Nam, grandfather-name correction, new sources line)
- people/gabby-windey (Bell Jar gift, no-kids, separate bathrooms, "if everything burns down" line)
- people/john-mulaney (signed Baby J special)
- themes/money (Rolex/$65k/"screaming wealth"/mother-generosity-lesson)
- themes/family (father-Porsche-instead-of-child-support, grandfather paintings as LA-fire-evacuation objects, Devorah)
- themes/orthodox-upbringing ("heretic" framing, nightly prayer, multiples of 18)
- themes/marriage ("if everything burns down" wedding context, Bell Jar gift, separate bathrooms, no kids)
- themes/canada (-30°C cashmere-scarf-from-grandfather story, Toronto→LA van move)
- career/accounting-to-standup ("least amount of work, most amount of payoff" + "would have made partner")
- career/vegas-elopement (Gabby's framing, grandfather paintings as only-things-taken)

**Indexes:** people/index, bits/index, wiki/index "Recently added" all updated. Raw `compiled: true` set on the article.

**Correction logged:** Grandfather's name canonical spelling changed from "Nathan Lubovski" (phonetic, audio-transcript) to "Nathan Letovsky" (print, FT 2026). Existing references in people/robby-hoffman.md updated; nathan-letovsky.md carries a callout pointing future readers at the spelling delta.

## [2026-05-29] compile | Wake Up press tour (10 transcripts)

First wiki compile. Processed all 10 ingested transcripts. Built 31 wiki pages across 5 type folders (no host pages, no episode pages, per user direction).

**People (8):** robby-hoffman (hub, priority high), gabby-windey, uncle-eddie, kaya-hoffman, schmuly-hoffman, john-mulaney, steve-carell, tim-dylan, rob-reiner.

**Projects (7):** wake-up, hacks, the-rooster, too-far, the-chris-gethard-show, after-midnight, i-m-nervous.

**Themes (7):** orthodox-upbringing, family, queerness, money, marriage, dating, canada.

**Bits (6):** one-hot-one-smart, socks-during-sex, testing-god-by-being-gay, proposing-via-crossword, juneteenth-cookout, two-year-decision-rule.

**Career (8):** montreal-flight, accounting-to-standup, hbo-script-sneak, mcdonalds-job, wga-strike-speech, top-surgery, vegas-elopement, losing-the-emmy.

Updated all 5 type-folder `index.md` files. Updated `wiki/index.md` with a "Recently added" block. Flipped `compiled: true` on all 10 raw files.

Known orphan wikilinks intentionally left for future compile passes: rachel-kaly, leanne-morgan, robert-pattinson, dog-nardo, the-bachelorette, the-traitors, dancing-with-the-stars, long-winded, talk-easy, blocks, etalk, not-skinny-but-not-fat, call-her-daddy, baroness-von-sketch, odd-squad, dying-for-sex, pull-rich-men, dora-the-explorer, jesus-loves-me, no-backsies-they-them, supercuts-tuesday, monogamy, identity, wake-up-press-tour. Lint pass will surface these — decide per-link whether to write a stub or strip the wikilink.

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

## [2026-05-29] init | wiki scaffolded

Initial structure created:
- `content/index.md` — site homepage
- `content/people/`, `projects/`, `episodes/`, `bits/`, `themes/`, `career/` — type folders, each w/ `index.md` landing page
- `content/log.md` — this file

Quartz scaffold + Cloudflare Pages deploy pipeline set up. Domain robbylore.org → Cloudflare. Vault at `~/ObsidianVaults/robbylore/` with private `raw/` (billhector/robbylore-raw) + public wiki (billhector/robbylore-wiki, symlinked via Quartz content/).

No raw sources ingested yet. No wiki articles compiled yet. Ready for first clips.
