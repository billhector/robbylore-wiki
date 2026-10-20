# Robby Lore — Design Decisions

Source of truth for the visual design of **robbylore.org**. If `quartz.config.yaml`, brand docs, or any rendered output disagrees with this file, this file wins and the downstream is the bug.

The site is built with **Quartz v5**. Quartz's theming surface is `quartz.config.yaml` `configuration.theme.{typography, colors.{lightMode,darkMode}}`. The schema uses **fixed token names** (`light`, `lightgray`, `gray`, `darkgray`, `dark`, `secondary`, `tertiary`, `highlight`, `textHighlight`) — these names are about **role**, not about value (e.g. `dark` is the *text* color in light mode).

---

## Locked decisions (typography 2026-05-29; colors 2026-10-20)

### Typography

| Role | Family | Weights | Origin | Notes |
|---|---|---|---|---|
| Headers (`theme.typography.header`) | **Cutive** | 400 only | Google Fonts | Typewriter-style serif, naturally heavy. Reads "encyclopedia entry" / fan-archive. |
| Body (`theme.typography.body`) | Source Sans Pro | default (400/600 + italics) | Google Fonts | Quartz default body; kept for legibility. |
| Code / mono (`theme.typography.code`) | **JetBrains Mono** | 400 only | Google Fonts | Replaces the prior IBM Plex Mono default. |

**Font origin:** `googleFonts` (not self-hosted). This intentionally diverges from PROFILE.md's "self-hosted woff2" preference — switching Quartz to local fonts is a larger refactor and not warranted yet.

**Weight pinning gotcha.** Quartz's `formatFontSpecification` in `quartz/util/theme.ts` defaults to `[400, 700]` for any `header`-role font and `[400, 600]` for `code`-role. If you specify a font as a bare string (`header: Cutive`), Quartz auto-fetches both default weights from Google Fonts. When the font only ships at one weight (Cutive only has 400; we want JetBrains Mono only at 400), the missing-weight fetch fails with "Bad Request" on every build. **Always use the object form when pinning weights:**

```yaml
typography:
  header:
    name: Cutive
    weights: [400]
  code:
    name: JetBrains Mono
    weights: [400]
```

After this fix, the Google Fonts URL in `<head>` emits a bare `family=Cutive` (no `;wght@…` suffix) and the build is warning-free.

### Colors — "Marquee" (adopted 2026-10-20)

Comedy-club neon: aubergine ink, magenta links, yellow highlighter. Replaced the 2026-05-29 navy/steel/cream palette, which read as washed out, and whose light-mode link (`#547792` on `#EAE0CF`) measured **3.63:1** and failed WCAG AA (earlier docs wrongly said ≈4.5:1).

No longer a strict 4-color rule: one neutral ramp (aubergine ↔ off-white) + one accent (magenta) + one highlighter (yellow in light, magenta tint in dark).

#### Light mode

| Token | Value | Role | Contrast on bg |
|---|---|---|---|
| `light` | `#FFF9F2` | **page background**: warm off-white | — |
| `dark` | `#170F1D` | headings / strong | 17.9:1 |
| `darkgray` | `#22172A` | body text | 16.4:1 |
| `gray` | `#6A5870` | muted text | 6.2:1 |
| `lightgray` | `#E8D9E4` | rules / borders (decorative) | 1.3:1 |
| `secondary` | `#B5176E` | **accent / links**: magenta | 6.1:1 |
| `tertiary` | `#7A0D49` | link hover (darken) | 10.1:1 |
| `highlight` | `rgba(0,0,0,0)` | wikilink-pill background **disabled** | — |
| `textHighlight` | `rgba(255,214,0,0.45)` | `==marked text==`: yellow highlighter | — |

#### Dark mode

| Token | Value | Role | Contrast on bg |
|---|---|---|---|
| `light` | `#170F1D` | **page background**: aubergine-black | — |
| `dark` | `#FFF9F2` | headings / strong | 17.9:1 |
| `darkgray` | `#F1E8EE` | body text | 15.6:1 |
| `gray` | `#B9A8C2` | muted text | 8.4:1 |
| `lightgray` | `#3A2A44` | rules / borders (decorative) | 1.4:1 |
| `secondary` | `#FF5FAE` | **accent / links**: hot pink | 6.7:1 |
| `tertiary` | `#FFB3D7` | link hover (lighten) | 11.3:1 |
| `highlight` | `rgba(0,0,0,0)` | wikilink-pill background **disabled** | — |
| `textHighlight` | `rgba(255,95,174,0.25)` | `==marked text==`: magenta tint | — |

Not themed by these tokens: code-block syntax colors (`github-light`/`github-dark` via the syntax-highlighting plugin) and Quartz's built-in callout colors.

### Custom CSS overrides

Beyond the token mapping, `quartz/styles/custom.scss` adds:

- **Header weight + bold synthesis** — see "Custom CSS overrides" section below.
- **Site title (sidebar `.page-title`) is forced to `--dark`**, not `--secondary`. The sidebar "Robby Lore" sits in an `<a>` tag and would otherwise inherit the accent color, looking like a faded nav link. Pinned to text color so it reads as a logo.
  ```scss
  .page-title a { color: var(--dark); }
  .page-title a:hover { color: var(--secondary); }
  ```

### Vibe summary

Off-white day mode, aubergine night mode, magenta links, yellow highlighter. Cutive typewriter headers keep the "archival fan reference" read; the neon accent adds comedy-club energy.

---

## Custom CSS overrides (`quartz/styles/custom.scss`)

- **Force header weight 400 + disable bold synthesis.** Cutive ships only at weight 400 on Google Fonts and is naturally heavy. CSS sets `font-weight: 400` and `font-synthesis-weight: none` on `h1`–`h6`, `.article-title`, and `.page-title` so browsers don't synthesize a faux-bold from the 400 master. Kept as defense-in-depth even after the typography weight pinning above means no part of the pipeline asks for @700 anymore.
- **Site title to text color.** `.page-title a { color: var(--dark) }` so the sidebar "Robby Lore" reads as a logo, not a faded link.

## Known accessibility caveats

- **All text tokens pass AA in both modes** (ratios in the Colors tables; computed with the WCAG relative-luminance formula).
- `lightgray` is decorative only (borders/rules); never use it for text.
- History: the 2026-05-29 palette's light-mode link was 3.63:1 (failed AA); an iteration before that used `#94B4C1` as the link (≈2:1).

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
