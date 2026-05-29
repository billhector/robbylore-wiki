# Robby Lore — Design Decisions

Source of truth for the visual design of **robbylore.org**. If `quartz.config.yaml`, brand docs, or any rendered output disagrees with this file, this file wins and the downstream is the bug.

The site is built with **Quartz v5**. Quartz's theming surface is `quartz.config.yaml` `configuration.theme.{typography, colors.{lightMode,darkMode}}`. The schema uses **fixed token names** (`light`, `lightgray`, `gray`, `darkgray`, `dark`, `secondary`, `tertiary`, `highlight`, `textHighlight`) — these names are about **role**, not about value (e.g. `dark` is the *text* color in light mode).

---

## Locked decisions (2026-05-29)

### Typography

| Role | Family | Origin | Notes |
|---|---|---|---|
| Headers (`theme.typography.header`) | **Cutive** | Google Fonts | Typewriter-style serif. Reads "encyclopedia entry" / fan-archive. |
| Body (`theme.typography.body`) | Source Sans Pro | Google Fonts | Quartz default body; kept for legibility. |
| Code / mono (`theme.typography.code`) | IBM Plex Mono | Google Fonts | Quartz default code; kept. |

**Font origin:** `googleFonts` (not self-hosted). This intentionally diverges from PROFILE.md's "self-hosted woff2" preference — switching Quartz to local fonts is a larger refactor and not warranted yet.

### Colors

#### Light mode

| Token | Hex | Role |
|---|---|---|
| `light` | **`#EAE0CF`** | **page background** — warm manuscript cream |
| `dark` | `#2b2b2b` | body text |
| `secondary` | **`#94B4C1`** | **accent** — links / active / brand color (soft blue-gray) |
| `tertiary` | `#84a59d` | popover hover / secondary accent (unchanged) |
| `lightgray` | `#e5e5e5` | rules / subtle borders (unchanged) |
| `gray` | `#b8b8b8` | muted text (unchanged) |
| `darkgray` | `#4e4e4e` | secondary text (unchanged) |
| `highlight` | `rgba(143, 159, 169, 0.15)` | subtle bg highlight (unchanged) |
| `textHighlight` | `#fff23688` | `==marked text==` background (unchanged) |

#### Dark mode

| Token | Hex | Role |
|---|---|---|
| `light` | **`#213448`** | **page background** — deep midnight navy |
| `dark` | `#ebebec` | body text |
| `secondary` | **`#547792`** | **accent** — links / active / brand color (steel blue) |
| `tertiary` | `#84a59d` | popover hover / secondary accent (unchanged) |
| `lightgray` | `#393639` | rules / subtle borders (unchanged) |
| `gray` | `#646464` | muted text (unchanged) |
| `darkgray` | `#d4d4d4` | secondary text (unchanged) |
| `highlight` | `rgba(143, 159, 169, 0.15)` | subtle bg highlight (unchanged) |
| `textHighlight` | `#b3aa0288` | `==marked text==` background (unchanged) |

### Vibe summary

Warm-cream day mode, midnight-library night mode. Cutive typewriter headers + soft slate-blue accents read "archival fan reference," matching the LLM-wiki framing of the site.

---

## Custom CSS overrides (`quartz/styles/custom.scss`)

- **Force header weight 400 + disable bold synthesis.** Cutive ships only at weight 400 on Google Fonts and is naturally heavy. CSS sets `font-weight: 400` and `font-synthesis-weight: none` on `h1`–`h6`, `.article-title`, and `.page-title` so browsers don't synthesize a faux-bold from the 400 master. Quartz still emits a build-time warning *"Failed to fetch font Cutive with weight 700, got Bad Request"* — that's cosmetic; Google Fonts returns the 400 face regardless, and the CSS override means nothing on the page ever asks for 700.

## Known accessibility caveats

- **Accent contrast.** Light-mode accent `#94B4C1` on bg `#EAE0CF` is ≈ 2.0:1. Dark-mode accent `#547792` on bg `#213448` is ≈ 3.3:1. Both fall below WCAG AA 4.5:1 for normal-size text used as a link. Quartz links inherit the accent and are typically not underlined by default in v5, so this is *visually* fine but *technically* sub-AA.
- **Mitigation, if needed later:** add an underline rule for `a` elements (via `quartz/styles/custom.scss`), or darken the accent. Re-evaluate if this is ever flagged.

---

## Design skills available

The user can invoke these against this project:
- `/design-extractor` — pull a fresh palette + Tailwind theme from another site URL (overkill for Quartz; useful if migrating off).
- `/design-auditor` — audit the current rendered site against accessibility + token consistency.
- `/design-system-standards` — validate decisions against the cross-project standards in `~/.claude/skills/design-system-standards/`.
- `/frontend-design` — build new components for the site (auto-reads this DESIGN.md).
- `/tailwind-patterns` — N/A for Quartz (Quartz uses SCSS, not Tailwind).

---

## Gotcha: `quartz-themes` plugin is disabled

The `quartz-themes` plugin (`github:saberzero1/quartz-themes`) ports the Obsidian default theme onto Quartz. Its CSS is emitted into `@layer obsidian-theme`, which is declared **after** Quartz's own `@layer quartz-base`. By Cascade Layers precedence rules, **later layers win** — so the plugin redefines `:root { --titleFont, --headerFont, --bodyFont, --light, --dark, --secondary, ... }` and silently overrides everything in `configuration.theme` from `quartz.config.yaml`.

Symptoms when the plugin is enabled: bg renders as `#fff`, accent as Obsidian's default purple, fonts fall through to Times because the plugin chains `--titleFont` through `--font-text` / `--font-default` vars that aren't defined.

**Current state (2026-05-29):** plugin set `enabled: false` in `quartz.config.yaml`. We get our chosen Cutive + cream + steel-blue theme; we lose the Obsidian-styled callouts (Quartz's built-in callout styling still works).

**If we ever re-enable the plugin** we'd need to either (a) accept its theme wholesale, or (b) override the key tokens via unlayered `:root` rules in `quartz/styles/custom.scss` — since unlayered rules beat layered rules at equal specificity.

## Out-of-scope today

Captured here so we don't relitigate them next session:

- **Self-hosting fonts** — Quartz Google-Fonts default kept. Migration would need a custom emitter or build step.
- **Component-level edits** — `quartz.layout.ts` and `quartz/components/` untouched. Default chrome (graph view, explorer sidebar, TOC, dark-mode toggle, reader mode, footer) intact.
- **Body / code font swap** — current Source Sans Pro + IBM Plex Mono retained.
