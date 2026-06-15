---
deck_id: glassmorphism_tech
kind: deck
category: general
summary: Dark glassmorphism SaaS / tech-talk deck — deep-space base, frosted glass panels, neon blue-purple-cyan light flow. Tech sharing, product launch, internal training, data dashboards.
keywords: [毛玻璃, 科技感, 暗色, SaaS, 霓虹]
primary_color: "#0A0E27"
canvas_format: ppt169
replication_mode: fidelity
page_count: 11
page_types: [cover, chapter, content, ending]
# Per-page placeholder contract — silences checker advisory warnings for this
# style's vocabulary (semantic indexed slots instead of one big CONTENT_AREA).
placeholders:
  01_cover: ["{{TITLE}}", "{{SUBTITLE}}", "{{DATE}}", "{{AUTHOR}}"]
  02_chapter: ["{{CHAPTER_NUM}}", "{{CHAPTER_TITLE}}", "{{CHAPTER_DESC}}"]
  03_content: ["{{PAGE_TITLE}}", "{{STEP_1_TITLE}}", "{{STEP_2_TITLE}}", "{{STEP_3_TITLE}}", "{{STEP_4_TITLE}}", "{{STEP_5_TITLE}}", "{{STEP_6_TITLE}}"]
  04_content: ["{{PAGE_TITLE}}", "{{KPI_1_LABEL}}", "{{KPI_2_LABEL}}", "{{KPI_3_LABEL}}", "{{KPI_4_LABEL}}"]
  05_ending: ["{{THANK_YOU}}", "{{ENDING_SUBTITLE}}", "{{CONTACT_INFO}}"]
  03a_content_layered: ["{{PAGE_TITLE}}", "{{LAYER_1_TITLE}}", "{{LAYER_2_TITLE}}", "{{LAYER_3_TITLE}}", "{{LAYER_4_TITLE}}"]
  03b_content_split: ["{{PAGE_TITLE}}", "{{COL_1_TITLE}}", "{{COL_2_TITLE}}", "{{COL_3_TITLE}}"]
  03c_content_hub: ["{{PAGE_TITLE}}", "{{HUB_TITLE}}", "{{SPOKE_1_TITLE}}", "{{SPOKE_2_TITLE}}", "{{SPOKE_3_TITLE}}", "{{SPOKE_4_TITLE}}", "{{SPOKE_5_TITLE}}", "{{SPOKE_6_TITLE}}"]
  03d_content_matrix: ["{{PAGE_TITLE}}", "{{QUAD_1_TITLE}}", "{{QUAD_2_TITLE}}", "{{QUAD_3_TITLE}}", "{{QUAD_4_TITLE}}"]
  03e_content_roadmap: ["{{PAGE_TITLE}}", "{{MILESTONE_1_TITLE}}", "{{MILESTONE_2_TITLE}}", "{{MILESTONE_3_TITLE}}", "{{MILESTONE_4_TITLE}}"]
  03f_content_chart: ["{{PAGE_TITLE}}"]
---

# Glassmorphism Tech — Design Specification

## I. Template Overview

Dark glassmorphism deck for tech-forward communication: technical talks, product launches, internal training, SaaS dashboards, engineering deep-dives. Tone is **未来感、科技、轻盈悬浮、专业**.

At a glance this template is recognized by: a **deep-space navy field** washed with soft blue-purple-cyan radial light flows, **frosted glass panels** (translucent gradient fill + 1px white-opacity hairline edge), **neon accent strokes** (flowing blue `#5B8DEF` → purple `#A26BFA` → cyan `#3DDDFC`), and large weight-900 headlines. Iconography is the duotone phosphor set, whose two-layer backplate resonates with the glass layering.

**Theme mode**: dark. Every page starts on `#0A0E27`; light text sits on translucent glass, never on raw dark.

## II. Color Scheme

| Role | HEX | Use |
|------|-----|-----|
| Background | `#0A0E27` | Deep-space base — full-canvas `<rect>` on every page |
| Glass base | `#1A2150` | Frosted-panel fill, applied at `fill-opacity` 0.4–0.85 (never solid) |
| Primary | `#5B8DEF` | Flowing blue — titles accent, primary icons, primary chart series |
| Accent | `#A26BFA` | Flowing purple — key data, gradient midpoint, secondary layer |
| Secondary accent | `#3DDDFC` | Neon cyan — highlights, connectors, eyebrow text, "active" state |
| Body text | `#E8ECFF` | Primary readable text on glass |
| Secondary text | `#A8B0D0` | Captions, descriptions, axis labels |
| Tertiary text | `#6B7299` | Footers, footnotes |
| Success | `#4ADE80` | Positive deltas, terminal/last step, completed milestones |
| Warning | `#FB7185` | Negative deltas, failure modes, caution |
| Amber | `#F59E0B` | Mid-tier state (rare — failure-matrix only) |

**60-30-10 proportion rule**: deep-space base 60% / glass + body text 30% / neon accents 10%. Pages that violate this read as "too busy".

**Accent rotation discipline**: when stacking 3+ parallel elements (steps, layers, quadrants, milestones, spokes), rotate the neon accents in a fixed order — **blue → purple → cyan → green** — so each parallel unit stays distinct yet harmonic. The 5+6 element layouts cycle back through the three neons.

## III. Typography

Same-family CJK sans with heavy weight contrast; no mixed typefaces.

- **Title / headline**: `"Microsoft YaHei", "PingFang SC", sans-serif`, weight 900
- **Body**: `"Microsoft YaHei", "PingFang SC", Arial, sans-serif`, weight 400 (emphasis 600–800)
- **Code / monospace** (rare): `Consolas, "Courier New", monospace`

Headlines carry the signature accent treatment: either a **gradient fill** (`url(#titleGradient)`) for hero/section words, or a **6px gradient bar** (`rx="3"`) sitting at the title's left baseline. Eyebrows / kickers above titles are uppercase Latin in `#3DDDFC`, `letter-spacing` 3–5px — this uppercase-cyan-eyebrow is part of the identity, not a generic convention.

## IV. Signature Design Elements

These motifs ARE this template. Every page should carry at least the background flow + one glass panel + one neon accent.

### 1. Deep-space light-flow background (every page)

The atmosphere is built from layered radial gradients, **never** a flat fill. Reuse this pattern (anchor positions vary per page mood):

```xml
<defs>
  <radialGradient id="bgGlowA" cx="18%" cy="28%" r="55%">
    <stop offset="0%" stop-color="#5B8DEF" stop-opacity="0.18"/>
    <stop offset="100%" stop-color="#5B8DEF" stop-opacity="0"/>
  </radialGradient>
  <radialGradient id="bgGlowB" cx="82%" cy="74%" r="55%">
    <stop offset="0%" stop-color="#A26BFA" stop-opacity="0.16"/>
    <stop offset="100%" stop-color="#A26BFA" stop-opacity="0"/>
  </radialGradient>
</defs>
<g id="bg">
  <rect width="1280" height="720" fill="#0A0E27"/>
  <rect width="1280" height="720" fill="url(#bgGlowA)"/>
  <rect width="1280" height="720" fill="url(#bgGlowB)"/>
</g>
```

> When a project supplies an AI background image, the Executor inserts `<image href="../images/<name>.png" .../>` between the base `<rect>` and the glow rects, then overlays a `bgOverlay` linear scrim (`#0A0E27` at 0.6–0.78 opacity) so glass panels stay legible. The glow rects can remain on top for cohesion.

### 2. Frosted glass panel (the load-bearing component)

```xml
<linearGradient id="glassPanel" x1="0%" y1="0%" x2="100%" y2="100%">
  <stop offset="0%" stop-color="#5B8DEF" stop-opacity="0.18"/>
  <stop offset="100%" stop-color="#A26BFA" stop-opacity="0.08"/>
</linearGradient>
<linearGradient id="glassEdge" x1="0%" y1="0%" x2="100%" y2="0%">
  <stop offset="0%" stop-color="#FFFFFF" stop-opacity="0"/>
  <stop offset="50%" stop-color="#FFFFFF" stop-opacity="0.35"/>
  <stop offset="100%" stop-color="#FFFFFF" stop-opacity="0"/>
</linearGradient>

<rect x="160" y="240" width="960" height="280" rx="22"
      fill="url(#glassPanel)" stroke="#FFFFFF" stroke-opacity="0.18" stroke-width="1"/>
<!-- hairline highlight sitting on the panel's top edge -->
<rect x="178" y="241" width="924" height="1" fill="url(#glassEdge)"/>
```

Card radius `rx` 14–22; larger for hero panels, smaller for dense grids. The 1px top-edge highlight (`glassEdge`) is what makes a panel read as "lit glass" rather than a flat translucent box — keep it.

### 3. Title gradient + accent bar

```xml
<linearGradient id="titleGradient" x1="0%" y1="0%" x2="100%" y2="0%">
  <stop offset="0%" stop-color="#5B8DEF"/>
  <stop offset="50%" stop-color="#A26BFA"/>
  <stop offset="100%" stop-color="#3DDDFC"/>
</linearGradient>
```

Used for hero headline fills, the 6px title-bar accent, connector lines, and the hub core. A full-page left-aligned title always opens with the 6px bar; a centered hero/section title may skip the bar and fill the keyword itself with the gradient.

### 4. Neon connector (sequence / hub / timeline pages)

```xml
<linearGradient id="flowLine" x1="0%" y1="0%" x2="100%" y2="0%">
  <stop offset="0%"  stop-color="#5B8DEF" stop-opacity="0"/>
  <stop offset="10%" stop-color="#5B8DEF" stop-opacity="0.7"/>
  <stop offset="50%" stop-color="#A26BFA" stop-opacity="0.7"/>
  <stop offset="90%" stop-color="#3DDDFC" stop-opacity="0.7"/>
  <stop offset="100%" stop-color="#3DDDFC" stop-opacity="0"/>
</linearGradient>
```

Dashed (`stroke-dasharray="6 6"`) for hub spokes / timelines; solid gradient line for step axes. Spokes radiate from center in per-branch neon (blue / purple / cyan / green).

### 5. Deviation from generic SVG rules — DO NOT use `feGaussianBlur`

`shared-standards.md` permits `<filter>` for shadows, but **this template forbids `feGaussianBlur` as a frosted-glass blur** — PPT export is unstable. The "frosted" illusion comes from translucent gradient fills + the atmosphere layer (radial glows / optional AI background image), not from a blur filter. Soft drop shadows via `<feDropShadow>` are allowed on small decorative elements only, never on primary structure.

## V. Page Roster

11 pages: 5 core + 6 layout variants. Variant filenames use the letter-suffix convention under the content index.

| File | Type | What this page is |
|------|------|-------------------|
| `01_cover.svg` | Cover | Hero glass panel left-anchored on the light-flow field. Gradient-bar title (weight 900), cyan eyebrow, subtitle, accent underline, footer with date + page count. The template's canonical cover. |
| `02_chapter.svg` | Chapter / section opener | Breathing page — full-canvas scrim, centered uppercase cyan eyebrow, two-line section title (gradient keyword + plain), descriptive subtext, a row of 2–4 neon-accent "theme pill" chips previewing the section. For section transitions and big-statement moments. |
| `03_content.svg` | Content — numbered steps | Horizontal sequence of 6 step cards on a dashed neon axis. Each card: numbered node (rotating blue→purple→cyan→green), icon, title, divider, two-line description, output slot, accent action chip. The terminal step highlighted (green, brighter fill). Suits how-it-works / methodology / pipeline. |
| `04_content.svg` | Content — KPI cards | 2×2 grid of large metric cards. Each card: left accent bar, icon tile, uppercase metric eyebrow, metric label, **huge weight-900 number** + unit, delta triangle (green up/red down) vs. baseline, footnote line. Suits dashboard / quarterly recap / exec headline. |
| `05_ending.svg` | Ending / CTA | Breathing closing — centered eyebrow, two-line CTA title (plain + gradient), subtitle, dual action buttons (gradient primary + glass secondary, each with icon), centered footnote, footer. For calls-to-action and thank-you. |
| `03a_content_layered.svg` | Content variant — layered architecture | 4 horizontal layers; left badge column (rotating neon, icon + layer tag + layer name) and 3 module glass cards per row. Suits architecture / stack / multi-tier decomposition. |
| `03b_content_split.svg` | Content variant — comparison columns | 3 vertical feature columns (one elevated as "most common"); each column has a colored header band, icon, pattern tag, title, 3 bullet features, bottom "fits" chip. Suits pattern / tier / option comparison. |
| `03c_content_hub.svg` | Content variant — hub & spoke | One gradient core (icon + hub label) ringed by orbit guides + 6 spoke glass cards on dashed neon connectors. Suits platform / ecosystem / 1-core-N-capabilities. |
| `03d_content_matrix.svg` | Content variant — 2×2 matrix | Axis frame (shallow↔deep columns, high↔low rows) + 4 quadrant glass cards, each with colored header, icon, title, action chip, 3 bullet items. Suits SWOT / failure-mode / two-axis frameworks. |
| `03e_content_roadmap.svg` | Content variant — vertical roadmap | Vertical gradient timeline (4 milestones, last one green-checked) + a right-side success-criteria panel with 4 numbered gates. Suits project plan / rollout / maturity path. |
| `03f_content_chart.svg` | Content variant — line chart | Glass chart panel with dual-axis (left %, right currency) grid, 2 area+line series with node dots, 3 dashed annotation markers, bottom legend strip. Suits trend / before-after / dual-metric evolution. |

## VI. Placeholder Contract

Fixed-structure pages (cover / chapter / ending) use canonical names (`{{TITLE}}`, `{{SUBTITLE}}`, `{{DATE}}`, `{{AUTHOR}}`, `{{CHAPTER_NUM}}`, `{{CHAPTER_TITLE}}`, `{{THANK_YOU}}`, `{{CONTACT_INFO}}`, …).

Content variants use **semantic indexed slots** declared in the `placeholders:` frontmatter above (`{{STEP_1_TITLE}}`, `{{KPI_1_LABEL}}`, `{{LAYER_1_TITLE}}`, `{{SPOKE_1_TITLE}}`, `{{MILESTONE_1_TITLE}}`, `{{QUAD_1_TITLE}}`, `{{COL_1_TITLE}}`, …). This is an intentional deviation from the single `{{CONTENT_AREA}}` convention: these layouts are structurally regular (N cards / N steps / N quadrants), so per-slot placeholders advertise the page's exact slot count and let the Strategist fill them by position. The frontmatter declaration makes the registrar and quality checker treat these as the template's authoritative vocabulary.
