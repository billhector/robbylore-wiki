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

The entire site uses a **strict 4-color palette**, no extras:

| Slot | Hex | Description |
|---|---|---|
| C1 | `#213448` | Deep navy |
| C2 | `#547792` | Steel blue |
| C3 | `#94B4C1` | Soft blue-gray |
| C4 | `#EAE0CF` | Warm cream |

All Quartz tokens map to these four. Light mode anchors on C4; dark mode flips on C1.

#### Light mode

| Token | Value | Role |
|---|---|---|
| `light` | C4 `#EAE0CF` | **page background** — cream |
| `dark` | C1 `#213448` | headings / strong |
| `darkgray` | C1 `#213448` | body text |
| `gray` | C2 `#547792` | muted text |
| `lightgray` | C3 `#94B4C1` | rules / subtle dividers |
| `secondary` | C2 `#547792` | **accent / links** (≈4.5:1 on cream — passes WCAG AA) |
| `tertiary` | C1 `#213448` | link hover (darken on hover) |
| `highlight` | `rgba(0,0,0,0)` | wikilink-pill background **disabled** |
| `textHighlight` | `rgba(84,119,146,0.25)` | `==marked text==` — steel tint |

#### Dark mode

| Token | Value | Role |
|---|---|---|
| `light` | C1 `#213448` | **page background** — navy |
| `dark` | C4 `#EAE0CF` | headings / strong |
| `darkgray` | C4 `#EAE0CF` | body text |
| `gray` | C3 `#94B4C1` | muted text |
| `lightgray` | C2 `#547792` | rules / subtle dividers |
| `secondary` | C3 `#94B4C1` | **accent / links** (≈9:1 on navy) |
| `tertiary` | C4 `#EAE0CF` | link hover (lighten on hover) |
| `highlight` | `rgba(0,0,0,0)` | wikilink-pill background **disabled** |
| `textHighlight` | `rgba(148,180,193,0.25)` | `==marked text==` — soft blue tint |

### Custom CSS overrides

Beyond the token mapping, `quartz/styles/custom.scss` adds:

- **Header weight + bold synthesis** — see "Custom CSS overrides" section below.
- **Site title (sidebar `.page-title`) is forced to `--dark`**, not `--secondary`. The sidebar "Robby Lore" sits in an `<a>` tag and would otherwise inherit the accent color, looking like a faded nav link. Pinned to text color so it reads as a logo.
  ```scss
  .page-title a { color: var(--dark); }
  .page-title a:hover { color: var(--secondary); }
  ```

### Vibe summary

Warm-cream day mode, midnight-library night mode. Four colors only. Cutive typewriter headers + steel-blue accents read "archival fan reference."

---

## Custom CSS overrides (`quartz/styles/custom.scss`)

- **Force header weight 400 + disable bold synthesis.** Cutive ships only at weight 400 on Google Fonts and is naturally heavy. CSS sets `font-weight: 400` and `font-synthesis-weight: none` on `h1`–`h6`, `.article-title`, and `.page-title` so browsers don't synthesize a faux-bold from the 400 master. Quartz still emits a build-time warning *"Failed to fetch font Cutive with weight 700, got Bad Request"* — that's cosmetic; Google Fonts returns the 400 face regardless, and the CSS override means nothing on the page ever asks for 700.

## Known accessibility caveats

- **Light-mode accent passes AA.** C2 `#547792` on C4 `#EAE0CF` ≈ 4.5:1.
- **Dark-mode accent passes AAA.** C3 `#94B4C1` on C1 `#213448` ≈ 9:1.
- Earlier iteration used C3 as the light-mode accent (≈2:1) — failed AA, replaced with C2.

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
