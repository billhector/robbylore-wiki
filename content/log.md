---
title: Activity Log
description: Reverse-chronological record of operations on the Robby Lore wiki — compiles, queries, lint passes.
publish: true
---

# Activity Log

Reverse-chronological record (newest first). Every compile, query, and lint pass logs here.

## [2026-05-30] cleanup | Tier-3 network backfill

Ran three network-dependent backfills from the lint audit:

**(f) Pedophile-snowstorm anecdote — confirmed.** Firecrawl search surfaced a YouTube clip titled *"Robby Hoffman's Near Death Experience"* (`youtube.com/watch?v=o815kfGRfW8`) with description: *"In the dead of winter her and her pedophile girlfriend got caught in a snow storm on Christmas..."* This is a clip from Robby's Aug 2025 Breaking Bread with Tom Papa appearance. Confirms the framing: Robby's **pre-Gabby ex was a pedophile**, the **near-death event happened on Christmas** during a snowstorm. Added to the Robby hub's Tom Papa source entry. Full transcript-level detail of the story would require scraping the YouTube short or finding a longer clip — left for a future query.

**(g) Forbes 2019 ingested.** Scraped and saved at `raw/articles/2019-07-24 Robby Hoffman From Drop Out to Stand-Up Forbes.md` (compiled: true). Article is by **Karl Moore**, Robby's former **McGill MBA leadership professor** — a connection the wiki had no record of. Surfaced new material:
- Robby **applied only to McGill** because *"the application was cheaper than any of the other options."*
- The **CPA grad-program walkout** told from the program's perspective.
- The **day-shift / night-shift** working pattern (10am-7pm writers' room → 9pm stage).
- *"I'm a nomad"* / *"I can really bring the audience somewhere, like a tour guide"* operating quotes.
- The 2019 JFL Montreal festival was the year Robby played three shows including her own set — this is the recording context that grew into the [[projects/i-m-nervous|I'm Nervous]] special.
- `career/accounting-to-standup` updated with all of the above.

**(h) 2026 Junos co-nominees filled.** From CBC Music's Jan 27 2026 nominee announcement. Robby's *[[projects/i-m-nervous|I'm Nervous]]* is nominated for **Comedy Album of the Year**, with co-nominees:
- *Dragonflies* — Adam Christie
- *Fish From the Jar* — Charlie Demers
- *Dawud* — Dave Merheje
- *Homesick.* — Faris Hytiaa
- *I'm Nervous* — Robby Hoffman

**Ceremony:** **March 29, 2026** at Hamilton's **TD Coliseum**, hosted by **Mae Martin** (comedian, singer, actor). The 2026 Junos also feature **Joni Mitchell receiving Lifetime Achievement** and **Nelly Furtado being inducted into the Canadian Music Hall of Fame.**

**Post-Tier-3 lint state:** 100 wiki pages, **44 raws** (43 prior + 1 new Forbes 2019), all compiled, 0 broken wikilinks, 0 thin pages, 0 missing Key Takeaways. All three Tier-3 knowledge gaps from the audit have been resolved or actioned. **The lint-to-clean cycle is complete.**

## [2026-05-30] cleanup | Tier-2 thin-page expansion

Expanded **all 15 thin anchor pages** (sub-600c bodies) flagged by the lint audit. Each page now carries 4–6 substantive bullets sourced from material already compiled into the wiki, plus a `## Related` cross-link section.

**People (7):**
- `people/rachel-kaly` — Too Far co-host context, NYT *"addictive"* quote, Office Hours Live "flopped" booking, format details
- `people/dog-nardo` — Labradoodle, near-9, autoimmune (initially misdiagnosed as cancer), peanut-butter med delivery, "useless" framing, German-Shepherd-upgrade campaign
- `people/jen-statsky` — Hacks creator trio, Randi's first line, "had they cast anyone else" framing, 6-lines / Emmy paradox
- `people/matt-tarses` — Lawrence-network operating-system framing, casting trajectory expansion
- `people/neal-brennan` — Blocks format design, the depth of the top-surgery interview
- `people/stacy-farber` — Degrassi role context, Robby's framing of relief vs regret
- (`people/megan-stalter`, `people/charly-clive`, `people/lauren-tsai`, `people/bill-lawrence`, `people/lucia-aniello`, `people/paul-w-downs` — already at acceptable length post-Tier-1)

**Projects (7):**
- `projects/not-skinny-but-not-fat` — fleshed out from stub: Amanda Hirsch host, single-source for Emmy-loss / Kris Jenner / Robert Pattinson / HBO script sneak / black-socks anecdotes
- `projects/dancing-with-the-stars` — Gabby's S31 2nd-place finish, tour-fatigue → sexuality questioning bridge to Robby
- `projects/long-winded` — *"The Robby Hoffman"* episode as deepest dual-perspective on tape
- `projects/the-bachelorette` — Clayton Echard S26 context, dual-Bachelorette S19 with Rachel Recchia, Erich Schwer engagement arc, Bachelor-Nation acceptance of Robby
- `projects/the-traitors` — Scotland-shoot isolation, supervised weekly calls, Shema prayer card, win → marriage announcement timing
- `projects/call-her-daddy` — Alex Cooper context, socks-during-sex + Gabby-meeting + quit-vaping disclosures
- `projects/mind-fudge` — Justine Nelson series context, 2019 four-credit cluster framing

**Bits (2):**
- `bits/i-dont-take-no-bait` — operating-principle framing, gender + grace overlay, Jihad-against-semantics tension
- `bits/supercuts-tuesday` — hair-and-glasses-constancy sibling, class-aware status-inversion frame, polo-lounge cluster pairing

**Lint-state post-Tier-2:** 100 wiki pages, 43 raws compiled, **0 broken wikilinks**, 0 orphans (except `log.md`), 0 missing-frontmatter outside `log.md` singleton, **0 thin pages**, 0 missing Key Takeaways. **Vault is structurally and content-shape clean.** Tier-3 (network: Forbes 2019 ingest, Junos co-nominees, pedophile-snowstorm follow-up) remains.

## [2026-05-30] cleanup | Tier-1 lint fixes

Applied Tier-1 fixes from the [[#[2026-05-30] lint | Wiki audit|lint audit]]:

- **Backfilled `source:` frontmatter on 44 pages** — 24 got 1+ raw-wikilink refs extracted from each page's `## Sources` body section; 20 got `source: []` (external-only sources without raw counterparts in the vault, e.g., Wikipedia-only references like `projects/kiff`, `projects/sherwood`).
- **`bits/trash-can-rant`** — added a `## Key Takeaways` section above the existing `## The bit` section.
- **Deleted `wiki/log 2.md`** — stale Obsidian sync-conflict copy of `log.md`.
- **Fixed dangling lint-report link** — changed the previous wikilink form (pointing to `output/lint-report-2026-05-30`) to a plain backtick reference (output/ lives outside the published wiki tree).

**Post-cleanup state:** 100 wiki pages, 43 raws compiled, **zero broken wikilinks**, zero orphans (other than `log.md`), zero missing-frontmatter issues outside the intentional `log.md` singleton. Tier-2 (thin-page expansion) and Tier-3 (network: Forbes 2019 ingest, Junos co-nominees, pedophile-snowstorm follow-up) remain available.

## [2026-05-30] lint | Wiki audit

Post-full-compile audit. **100 wiki pages**, **43 raws all compiled**, **zero broken links**, **zero orphans**, **zero web-publish violations**, **zero hollow raws**. Vault is in strong shape.

**Issues flagged:**
- **44 pages missing `source:` frontmatter** — legacy stubs created in earlier compile passes; sources are cited in body `## Sources` sections but the frontmatter array is incomplete. Tier-1 backfill candidate.
- **1 page missing `## Key Takeaways`:** `bits/trash-can-rant` (uses `## The bit` heading instead).
- **15 thin anchor pages** (under 600c body) — thinnest: `people/rachel-kaly` (325c), `projects/not-skinny-but-not-fat` (276c). Expected pattern for LLM-wiki anchors; not an error, but expansion opportunities.

**Knowledge gaps flagged for future queries:** the "pedophile-girlfriend-snowstorm" Tom Papa anecdote, McGill CPA-walkout primary source (Forbes 2019 not yet in `raw/`), pre-Gabby first girlfriend's name, sister Devorah's recent graduation institution, 2026 Junos co-nominees + winner.

Full report at `output/lint-report-2026-05-30.md` (local only, not published).

## [2026-05-30] compile | 4 transcripts — Steph-Tolev-on-Too-Far + Steph-Infection + Stavvy's-World + Shank

Final batch (4 of 43 raws). All transcripts now compiled. Net: **1 new page** (`people/steph-tolev`), substantive updates to 3 existing pages.

**Created:**
- `people/steph-tolev` — Bill Burr *Friends Who Kill* alum, host of *Steph Infection*, **Robby's former LA roommate** (pre-Gabby). Full roommate-breakup arc included: Steph took Robby in after Robby's pre-Gabby big breakup; Robby moved out without notice during Steph's 2-day Joshua Tree trip; recurring "hello while I napped" napping-fight bit. Reconnected and remain close as of 2026.

**Updated:**
- `people/robby-hoffman` — 4 new source citations; **Verdun, Montreal** confirmed as the Hoffman family neighborhood; **Kybella chin injections** (acid-into-fat-cells; got chin + stomach done); **considering hip-reduction surgery** for further masculinization (per Steph Infection Feb 2026); Wake-Up January 2026 press cluster (Stavvy's World Jan 19 + Howie Mandel Jan 6); 9-siblings-poor rehearsal on Stavvy's.
- `themes/canada` — **Verdun, Montreal** added as the specific Hoffman family neighborhood, *"the only Jews ever in Verdun"*; predominantly French-Canadian; *"they hated us there."*
- `projects/wake-up` — January 2026 release-week press cluster (Stavvy's World + Howie Mandel) named; February 2026 expansion (Beck-Kyle + Steph Infection).

**Source chronology insight:** the Steph Tolev episodes (Aug 2024 + Feb 2026) bookend ~18 months of Robby's pre-Gabby and post-Gabby life with the same close-friend lens. The roommate-breakup story is the cleanest pre-Gabby "Robby moves through a friendship" data point in the source set; **Verdun** is the first neighborhood-level Montreal detail to surface anywhere.

**Completion status:** all 43 raws now `compiled: true`. Vault is fully compiled. Next maintenance pass should be `/wiki-lint` to check for broken wikilinks and orphan pages introduced during this multi-batch compile.

## [2026-05-30] compile | 5 transcripts — Tom-Papa + David-Cross + Beck-and-Kyle + Howie-Mandel + Tea-Time

Fourth batch of 5. Date span: Aug 2024 (Senses Working Overtime / David Cross) → Feb 2026 (Beck Bennett + Kyle Mooney "Male Loneliness Epidemic"). No new pages this batch — all content folded into existing structure.

**Updated (substantive):**
- `people/robby-hoffman` — 5 new source citations; **formal OCD diagnosis confirmed** (David Cross 2024); **mother's full name = Constance** (Tea Time confirms the long form behind "Connie"); David Cross's *"new Daddy"* framing of mother's religious-to-Christian-to-Jesus substitution arc; Tom Papa's wild **near-death-snow-storm-with-a-pedophile-girlfriend** anecdote flagged (pre-Gabby ex; details TBD on future query); Robby's **kosher-extremity self-anchor** — *"if a knife touched something un-kosher you were burying the knife and un-burying it."*
- `career/vegas-elopement` — **May 1, 2025 planned proposal date** that the LA fires preempted, per Tea Time (Jun 2025); Robby had been **building a custom ring** for that date.
- `themes/queerness` — **they/them pronouns "not seamless"** segment from Tom Papa (Aug 2025).
- `themes/orthodox-upbringing` — David Cross's *"new Daddy"* framing of Connie's Christian turn; the kosher-knife-burying self-anchor; religion-as-OCD parallel.

**Source chronology insight:** the David Cross conversation (Aug 2024) is the **only** compiled source where Robby explicitly states a **formal OCD diagnosis** — important because every podcast appearance since (Tom Papa, Howie Mandel, RIP Jordan Jensen) has referenced her OCD but the wiki had it as inferred. Tom Papa's August 2025 episode contains the most explicit *"I dated a pedophile"* anecdote on record; Robby names no specifics but the existence of that relationship + the snow-storm near-death event sits in pre-Gabby territory and warrants flagging for future expansion.

## [2026-05-30] reconcile | Wikipedia cross-check on Robby Hoffman biography + filmography

Cross-checked the wiki against the [Wikipedia article on Robby Hoffman](https://en.wikipedia.org/wiki/Robby_Hoffman). Applied biographical corrections + added 7 new pages for ungrouped credits.

**Corrections to existing pages:**
- `people/robby-hoffman` — full legal name corrected: **Rivkah Sarah Hoffman** (Wikipedia + verified Instagram August 2024). Previous wiki used the phonetic "Rifka." Family still uses Rifka/Rivkah at home; public name = Robby. **DOB added: December 2, 1989.** Added McGill **double major** (accounting + communications). Distinguished the McGill **graduate CPA program walkout** ("a few hours into her first day," Forbes 2019) from the KPMG audit job — these are sequential, not the same event. Added **2025 Primetime Emmy nomination** (Outstanding Guest Actress in a Comedy Series for Hacks). Added **2026 Juno Award nomination** for I'm Nervous. Added pre-Wake-Up recognition list (NY Comedy Fest 2018, Comedy Central Up Next 2018, Conan Comics to Watch, Vulture 2020). Added Wikipedia to sources.
- `career/accounting-to-standup` — sequence clarified: KPMG → first comedy attempt → CPA grad program → quit hours in → comedy for good. Forbes 2019 added as primary source for the CPA walkout.
- `themes/orthodox-upbringing` — added that **both parents were originally Reform Jews** who later became *baal teshuva* to Hasidic; Robby's quote: *"They're two people who joined a Hasidic cult and had ten kids, and I'm the product of it."*
- `projects/i-m-nervous` — **2019 special recorded at Just For Laughs Toronto for Crave TV**; **2026 Juno Comedy Album of the Year nomination** added (CBC Music, Jan 27 2026).
- `projects/hacks` — **8 episodes across Seasons 4–5** confirmed; 2025 Primetime Emmy nomination category named precisely.
- `projects/dying-for-sex` — **character name confirmed as "G"** in episode **"Topping is a Sacred Skill"**.
- `projects/the-rooster` — **8 episodes recurring** confirmed; Wikipedia lists the series simply as *Rooster*.

**Created (7 new pages):**
- `career/bialik-secondary-school` — Robby's Montreal private Jewish high school, now named.
- `projects/history-of-the-world-part-ii` — Hulu sketch series; Natalia, ep "III" (2023).
- `projects/kiff` — Disney animation; voice role Jackie Pennidötter, 2 eps 2025.
- `projects/sherwood` — 2019 TV series; writer credit, 2 eps.
- `projects/mind-fudge` — Justine Nelson series; writer, S2 2019.
- `projects/dino-dana` — Canadian kids' TV; writer, 2017 (earliest known TV writing credit).
- `projects/dykevic` — Robby Hoffman Consulting Group / formerly Dykevic; weekly call-in advice show on Chris Gethard's Planet Scum Live, 2020–21.

**Indexes refreshed:** `projects/index` (Television + Podcast sections expanded with 5 new credits + Dykevic), `career/index` (added Bialik).

**Why this matters:** the existing wiki was built almost entirely from podcast/article retellings, which emphasized Wake Up / Hacks / Rooster and Robby's bit material. The Wikipedia cross-check surfaces the **pre-Wake-Up Canadian-TV writing career** (2017 Dino Dana → 2019 Sherwood/Mind Fudge/Odd Squad Emmy/I'm Nervous Crave TV special) and the **2020–21 hosting practice** on Planet Scum Live — both of which are load-bearing for understanding how she landed Randi on Hacks but had been invisible in the podcast/article source set.

## [2026-05-30] compile | 5 transcripts — Office-Hours-Live + Fitzdog + Lovett-or-Leave-It + Anniewood-Ep127 + Online-Forever

Third batch of 5. Date span: July 2024 (Office Hours Live, mid-WGA-aftermath) → May 2025 (Fitzdog Radio, mid-press-tour). Net: **2 new pages** (`people/rachel-bloom`, `career/comedy-store-passed`), substantive updates to 5 existing pages, indexes refreshed.

**Created:**
- `people/rachel-bloom` — comedian / Crazy Ex-Girlfriend creator; Robby's joint guest on Lovett or Leave It Passover 2025 episode; both share *"the boy in the relationship"* self-id.
- `career/comedy-store-passed` — Robby was **not** passed at the Hollywood Comedy Store until April 2025 despite booking spots there — only learned from booker Emily after years (per Bein' Ian Oct 2024); announced as the headline of Anniewood Ep. 127.

**Updated (substantive):**
- `people/robby-hoffman` — 6 new source citations; full picture of mid-2024 → mid-2025 press cadence; sex-work position (decriminalize + benefits but question "choice" framing); comedy-best-friend **Natalie** named.
- `people/annie-lederman` — confirmed attendance at the Vegas wedding (Jan 11 2025); twin brother Todd birthday-week-with-Annie scheduling.
- `career/vegas-elopement` — Annie Lederman as named wedding-guest source.
- `projects/hacks` — May 2025 simultaneous-streaming-press cluster (Fitzdog + Lovett); Robby's *"I think I'm in almost every episode"* of the new season.
- `projects/dying-for-sex` — fleshed out from stub: **Robby plays a sexual guide to Michelle Williams' character**; Spring 2025 premiere; tag-team Hulu/Max press window with Hacks; Rachel Bloom is also in the show.

**Source chronology insight:** Office Hours Live (Tim Heidecker, July 2024) caps an interesting failure-mode — Robby was originally booked with [[people/rachel-kaly|Rachel Kaly]] who "flopped" and the producers reached for Robby solo. Fitzdog Radio (May 2025) is the cleanest single source on Robby's *Hacks + Dying for Sex + Verified* triple-streaming moment. Anniewood Ep. 127 (April 2025) bookends the [[career/comedy-store-passed|Comedy Store pass]] arc that started on Bein' Ian Ep. 115 in October 2024.

## [2026-05-30] compile | 5 transcripts — Anniewood-Ep20 + Bless-These-Braces + Live-From-Bed + My-Favorite-Lyrics + RIP-Jordan-Jensen

Second batch of 5. Span: pre-Gabby March 2023 (Anniewood Ep. 20) → Wake-Up post-release surge March 2026 (RIP Jordan Jensen Ep. 60). **No new pages this batch** — all content folded into existing structure. ~7 substantive existing-page updates plus a structural correction on `people/jordan-jensen` (she is alive — "RIP" is the podcast name, not a memorial).

**Corrections:**
- `people/jordan-jensen` — corrected; Jordan is alive. RIP Jordan Jensen Ep. 60 (Mar 2026) shows her recording, reconciling with Robby after Bein' Ian Ep. 115 friction. Added OCD + chronic-lateness traits and the reconciliation arc.

**Updated (substantive):**
- `people/robby-hoffman` — 5 new source citations; cat **Numb** named; **1983 Toyota Corolla** as first car; **Connie's Cosby-records-on-sale** mailing; brother **"Shanaer"** Pride-bulletin-call addition; mother's *"reverence for doctors"* annual-checkup ritual.
- `people/gabby-windey` — Numb + Labradoodle dynamic; *"giving each other the childhood we wanted"* no-kids framing; Gabby chronic-late (Jordan ep).
- `people/schmuly-hoffman` — Saskatchewan-mall location; pro-German-Shepherd LA-safety advocacy.
- `people/annie-lederman` — first Robby appearance (Ep. 20 March 2023 Ybor City); Tesla-vs-1983-Corolla framing; twin-brother-Todd producer; Marie Kondo project carried over.
- `people/jordan-jensen` — (see Corrections above) reconciliation + OCD details.
- `career/top-surgery` — Anniewood Ep. 20 regret-symmetry argument; 3% tissue left; *"no goof, no test"*; *"don't buy surgery on sale"*; Bein'-Ian Wall-Street-bailout insurance frame.
- `career/mcdonalds-job` — 12-to-8 shift; Diet-Coke take-home; manager-with-keys after-hours fries; **broke kosher on an Egg McMuffin at 19** (McGill exam morning); 40th-birthday self-catering haul (40/15/60).
- `projects/wake-up` — Robby's *"between Gervais and Rife"* self-rating; March 2026 secondary press surge (View + Seth Meyers); Cranberries "Dreams" clearance request.
- `themes/family` — annual-checkup-in-underwear scene; **Menachem flagged underweight**; **Khaya's *"if the queen invited you"*** line; **Shanaer's Pride-bulletin call**; Schmuly's German-Shepherd campaign.
- `themes/orthodox-upbringing` — kosher-till-19 + Egg-McMuffin break; first-girl-bat-mitzvah; religious-weird-Ellie-Kemper-of-school self-positioning; Argentinian-Jewish-subsidy parallel via Tam.

**Source chronology insight:** Anniewood Ep. 20 (Mar 2023) is the earliest pre-Gabby snapshot we have — gives the cleanest version of Robby's top-surgery decision logic before public-figure dynamics complicated retellings. RIP Jordan Jensen (Mar 2026) caps the press surge and shows Robby openly rating Wake Up alongside Gervais/Rife — the first source where she does this on the record.

## [2026-05-30] compile | 5 transcripts — Bethenny + Bein' Ian + Made It Out + Endless Honeymoon + Anniewood

Compiled five 2024–25 podcast transcripts (oldest published first: Bethenny Frankel Sept 2023, Made It Out Jul 2024, Anniewood Jul 2024, Bein' Ian Oct 2024, Endless Honeymoon Oct 2025). Net: **3 new wiki pages** (`people/annie-lederman`, `people/jordan-jensen`, `bits/trash-can-rant`), substantive updates to 9 existing pages, all primary type-folder indexes refreshed. No contradictions surfaced.

**Created:**
- `people/annie-lederman` — Anniewood host, recurring Robby guest, mutual-friend bridge.
- `people/jordan-jensen` — Bein' Ian co-host, gender-identity debate sparring partner; flagged deceased 2025 (page to expand after the RIP-Jordan-Jensen raw is compiled).
- `bits/trash-can-rant` — bathroom-pedal-lid despair thesis.

**Updated (substantive):**
- `people/robby-hoffman` — anti-Pride core stance (*"ashamed to the day I die"*); diabetes-management grief frame; God-just-likes-me line; "40 for 10 years" age-decade; BB-gun from Gabby Christmas; 6 new source citations covering all 5 raws.
- `people/gabby-windey` — Bridget + Kyle wingman backstory (Bethenny 2023); pre-Robby Raya + Thursday queer line-dancing; "nobody explores this late in life" (Robby); joint *View* coming-out moment (Mal Glowenke); independent no-kids decisions; 50/50 finances; "lesbian years are dog years"; "monogamy is for lesbians."
- `people/nathan-letovsky` — died at 88; deathbed quote *"prioritize leisure"* / *"vacation without your family is not a vacation."*
- `people/schmuly-hoffman` — shop-class wooden dildo on mother's piano; tank-top slur; *"you're cutting your tits off"* dinner-table reaction.
- `themes/queerness` — full Walk-to-Remember outing scene (student bar, bathroom stall, primm-and-proper classmate, cafeteria walk); Ally + Malay loyalty; best-friend 3-month silence; *"ashamed to the day I die"* anti-Pride core; "Adam and Steve" sister logic; almost-married-rich temptation; first-girlfriend graffitier; first-breakup 9-lb-weight-loss at 19; *View* joint coming-out framing.
- `themes/family` — 13-months-apart sibling spacing; mother's 12-year-one-night-class-at-a-time graduation; art-teacher $45 program declined; D'vorah graduation 2025; Big Brother / Big Sister program (Sherry + Stu); program ended after overnight suggestion; Emmys with Kaya.
- `themes/orthodox-upbringing` — mother named Messianic Jew / Jews for Jesus; AIDS-needles-in-cinema-seats paranoia; Châlent love; *"due for a new religion"* framing.
- `themes/dating` — *"nobody explores this late in life"*; *"I would never ghost a date"* communication ethos; U-Haul-or-Ghost game; Bridget+Kyle wingman.
- `themes/monogamy` — Gabby's *"monogamy is for lesbians"* line; mutual jealousy as transparency tool.
- `people/index` — added Annie Lederman + Jordan Jensen.
- `bits/index` — added Trash Can Rant.

**Source chronology insight:** Two early-relationship sources (Bethenny Sept 2023, Made It Out Jul 2024, Anniewood Jul 2024) deepen the Gabby-meeting story significantly — the bar wingman story (Bridget + Kyle) is new detail not present in Semi-Tropic-anchored 2025 retellings. The Endless Honeymoon Oct 2025 episode is post-Emmy; the *"prioritize leisure"* grandfather quote is the most quotable new line for the [[people/nathan-letovsky]] page.

## [2026-05-30] compile | Bustle 2023 — "Comedian Robby Hoffman Isn't Exactly Happy To Be Here"

Compiled the Bustle interview by Lizzie Logan, October 26 2023 — a Frogtown, LA lunch during the WGA strike's final weeks. Substantive (~12.7K body, no iframes); no new pages, heavy updates to 7 existing.

**Updated:**
- `projects/rivkah` — Showtime pilot first announced June 2021 (Deadline); producer-at-the-next-table Frogtown cameo; Addison-Rae-yarmulke riff.
- `projects/too-far` — pinned NYT *"addictive"* quote to its 2023-10-17 piece grouping Robby + Rachel + Bobbi Althoff.
- `people/robby-hoffman` — Oct 2023 quote bank added (*"I never got to come out gay,"* *"Dreams are free,"* *"Michael Jordan level proportions"*); agent named (Mark); style frame *"small grievances"*; Bethenny Frankel *"roll it into the batter"*; 10+-years-same glasses/hair.
- `people/gabby-windey` — Bustle hair/dress churn contrast; *"Gabby's obsessed with Jews"* quote predating engagement.
- `career/wga-strike-speech` — places Robby's speech ~4-5 months before strike resolution; couldn't talk to Rivkah producer about the show during the Frogtown lunch.
- `career/accounting-to-standup` — Eddie-Murphy-as-discovery-vector; *"I wouldn't wish a calling on my worst enemy"*.
- `themes/queerness` — *"I never got to come out gay"* and the androgyny-as-announcement frame.

## [2026-05-30] cleanup | Deleted IndieWire source

Deleted the IndieWire "Just Discovering Robby Hoffman" raw and all references (it was hollow — only 119 chars of promo billboard, no body — and the site's clipping pipeline is unreliable). The Hacks + Dying-for-Sex tags it contributed are already redundantly cited by the Guardian piece.

## [2026-05-30] compile | 7 sources — Synagogue/Lovebirds/Realtor/Q-Tom-Power/GQ-Mulaney/People-Carell/Guardian

Compiled 7 raw files: 6 articles + 1 transcript. Net: **16 new wiki pages**, ~18 heavy updates, all indexes refreshed, zero broken wikilinks.

**Created (16):**
- Projects (4): `projects/rivkah` (Showtime autobiographical series), `projects/unentitled` (Robby's first sold HBO show, post-WGA-speech), `projects/working-moms` (CBC; 1-week punch-up), `projects/everybodys-live` (Mulaney's Netflix talk show).
- People (9): `people/lauren-tsai` (Rooster co-star — Sunny), `people/bill-lawrence` (Rooster co-creator), `people/matt-tarses` (Rooster co-creator), `people/charly-clive` (Carell's daughter Katie on Rooster), `people/lucia-aniello` (Hacks co-creator; wrote Randi for Robby), `people/paul-w-downs` (Hacks co-creator + Jimmy), `people/jen-statsky` (Hacks co-creator), `people/megan-stalter` (Hacks Kayla; Robby's agency-side scene partner), `people/stacy-farber` (got the Degrassi role Robby was scouted for).
- Career (1): `career/degrassi-audition` (age 12-14; mother shut it down).
- Bits (3): `bits/aids-popsicle` (childhood paranoia bit; mother bought ten boxes), `bits/package-deal` (grandfather's school-interview line), `bits/polo-lounge` (early-LA $7-beer ritual).

**Updated (heavy hits):**
- `people/robby-hoffman` — 7-of-10 confirmed, Bernie supporter, autism self-id no diagnosis, dad estrangement since early-20s, mom 5:30am routine, Mulaney intro via Dan Levy + Joe Mande, Mo-on-Rooster confirmed, Unentitled HBO sale named, writer's cabin added, new bits + sources.
- `people/gabby-windey` — Semi-Tropic meeting venue, May 2023 dating start, Spanish-style $5K rental specs, Traitors supervised-call protocol, Shema prayer card, Lamictal/Gabapentin pills inventory, Bob-the-Drag-Queen parallel.
- `people/john-mulaney` — first heard Robby at WGA assembly, Dan Levy / Joe Mande validation chain, September '24 text, Everybody's Live segment, road-tour hotel-coffee policy.
- `people/steve-carell` — Greg Russo character; "botched every interaction" framing; Office-ensemble comparison.
- `projects/wake-up` — Mulaney's "legend at the top of their game" stage intro line.
- `projects/hacks` — Aniello/Downs/Statsky named as Randi authors; Randi's *"Last week I was a Hassidic Lubavitch Jew"* intro line.
- `projects/the-rooster` — full cast (Tsai/Clive/Deadwyler/Dunster/McGinley/Britton), Mo/Sunny role names, Carell's Office quote.
- `projects/odd-squad` — 2019 Daytime Emmy confirmed; backstory of why Robby said yes (six-month contract long enough vs 1-2 week gigs).
- `projects/baroness-von-sketch` — clarified: 1-week punch-up only.
- `projects/i-m-nervous` — 2019 Canadian special; Robby's *"doesn't even count"* dismissal vs Wake Up.
- `career/wga-strike-speech` — full chronology (two questions, real-estate first then salaries, Carmen's prediction, Joe Mande validation, *Unentitled* sale outcome); "maybe my timing was autistic" reflection.
- `career/vegas-elopement` — Jan 11 date, 20-min ceremony, Chappell Roan walk-down, evacuation cargo (cat + podcast gear + keepsakes), $799 package contents (limo + photos + minister).
- `career/hbo-script-sneak` — clarified as separate sale from Unentitled; KPMG-stolen-supplies dialogue; first rep, not first show.
- `career/accounting-to-standup` — McGill free-laptop framing; George Braithwaite's loft; *"Comedy was foisted upon me, like Moses"*; refused-short-contracts era.
- `themes/family` — 7-of-10 placement; 5:30am-mom; early-20s dad estrangement; new GQ-Mulaney anecdotes.
- `themes/orthodox-upbringing` — synagogue "ticking time bomb"; *"fanatic religious sect"* framing; current *"something larger than us"* belief.
- `themes/canada` — Montreal-Toronto inferiority complex; 6-min JFL sellout; Schwartz's / Busan ritual.
- `themes/marriage` — Jan 11 date, Hot To Go walk-down, *"best night of my life"*.
- `bits/proposing-via-crossword` — *"Will you marry me, Gabby?"* full puzzle text; Gabby's three-weeks-in framing.

**Indexes updated:** projects (split Stand-up / Television / In Development / Reality / Podcast; added 4 new entries); people (new Hacks-creators + Rooster-creators sections); career (degrassi-audition); bits (3 new entries).

**Heads up:** 1 brand-new raw arrived mid-compile — "Comedian Robby Hoffman Isn't Exactly Happy To Be Here.md" — left untouched (`compiled: false`) for next /wiki-ingest + /wiki-compile pass.

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
