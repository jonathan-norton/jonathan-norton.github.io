# DESIGN.md — Portfolio Design System

Direction: **"Krimson"** — crimson + cream, warm editorial. Brand colors carry the Kappa network signal; layout and feel come from the three reference designs (Liam Basil structure, NewsGHT whitespace, Bento cards).

All components must use these tokens. No raw hex codes, font names, or shadow values in component code — reference CSS variables only (per CLAUDE.md donor rule).

---

## 1. Colors

| Token | Value | Use |
|---|---|---|
| `--color-bg` | `#F5F0E6` | Page background (cream) |
| `--color-surface` | `#FDFBF6` | Cards, elevated surfaces (lighter cream) |
| `--color-primary` | `#9E1B32` | Crimson — buttons, links, accents, active nav |
| `--color-primary-hover` | `#7E1628` | Crimson darkened for hover states |
| `--color-text` | `#231F1C` | Body text (warm near-black) |
| `--color-text-muted` | `#6B6259` | Secondary text, captions, labels |
| `--color-border` | `#E2D9C8` | Card borders, dividers, hairlines |
| `--color-on-primary` | `#FDFBF6` | Text on crimson backgrounds |

Rules:
- Crimson is an **accent**, not a canvas. Large fills are cream; crimson appears in buttons, links, small labels, and at most one large moment (footer CTA band).
- Never place crimson text on cream at small sizes for long passages — body text is always `--color-text`.
- No pure white (`#FFFFFF`) and no pure black (`#000000`) anywhere.

## 2. Typography

| Token | Value |
|---|---|
| `--font-heading` | `"Source Serif 4", Georgia, serif` |
| `--font-body` | `"Inter", system-ui, sans-serif` |

Type scale (desktop / mobile):

| Token | Size | Weight | Font |
|---|---|---|---|
| `--text-hero` | 64px / 40px | 600 | Source Serif 4 |
| `--text-h2` | 40px / 30px | 600 | Source Serif 4 |
| `--text-h3` | 24px / 20px | 600 | Source Serif 4 |
| `--text-body` | 17px / 16px | 400 | Inter |
| `--text-small` | 14px | 400 | Inter |
| `--text-label` | 12px, uppercase, +0.08em tracking | 600 | Inter |

Rules:
- Line-height: 1.1 for hero/h2, 1.3 for h3, 1.6 for body.
- Max body text width: 65ch.
- Source Serif 4 is headings only. Never for body, buttons, or nav links.

## 3. Spacing & Layout

Base unit: 4px. Scale: 4, 8, 12, 16, 24, 32, 48, 64, 96, 128.

| Token | Value |
|---|---|
| `--space-section` | 128px desktop / 80px mobile between sections |
| `--space-card-pad` | 32px desktop / 24px mobile inside cards |
| `--container-max` | 1152px, centered, 24px side padding on mobile |

Whitespace philosophy (from NewsGHT reference): generous. When in doubt, add space rather than a divider.

## 4. Radii & Shadows

| Token | Value | Use |
|---|---|---|
| `--radius-card` | 24px | Project cards, image frames (Bento-style softness) |
| `--radius-button` | 9999px (full pill) | All buttons (from Tailark donor) |
| `--radius-image` | 24px | Portrait/photos (NewsGHT rounded frame) |
| `--shadow-card` | `0 1px 2px rgba(35,31,28,0.06), 0 8px 24px rgba(35,31,28,0.06)` | Cards on hover only |

Rules: flat by default, shadow appears on hover as affordance. No glows, no gradients.

## 5. Components

**Buttons**
- Primary: crimson fill, `--color-on-primary` text, pill, 48px height, Inter 600.
- Secondary: transparent, 1px `--color-primary` border, crimson text, pill.
- Hover: primary → `--color-primary-hover`; secondary → crimson fill at 8% opacity.

**Sticky nav** (from Tailark donor skeleton)
- Transparent over hero; on scroll: `--color-bg` at 80% opacity + backdrop blur, hairline bottom border.
- Links: Inter, `--color-text-muted`, hover → `--color-text`. Resume button (primary) always visible, far right.

**Project cards** (Bento reference)
- `--color-surface` fill, 1px `--color-border`, `--radius-card`, `--space-card-pad`.
- Contents: label (text-label, crimson) → title (h3) → 2–3 lines body → metric line → GitHub link with arrow.
- Hover: `--shadow-card` + border darkens slightly. No lift/scale animation.

**About section** (NewsGHT reference)
- Two columns: text left, rounded portrait right. Stacks on mobile, image first.

**Footer CTA** (Liam Basil reference)
- The one large crimson moment: full-width crimson band, cream text, big Source Serif 4 closing line, secondary-style buttons inverted (cream border/text).

**Motion**
- Transitions: 150–200ms ease on color/border/shadow only. No scroll animations, no entrance reveals, no parallax. Content is visible immediately (recruiter skim rule).

## 6. Decision Log

| # | Date | Decision | Why |
|---|---|---|---|
| 1 | Jul 2026 | Single-page site, sections: Hero → Projects → About → Contact/footer | Recruiters skim in 10–30s; every click loses some; content volume doesn't justify multi-page |
| 2 | Jul 2026 | SEO targets name searches ("Jonathan Norton" + FSU/software engineer), not topic keywords | Recruiters Google the name after seeing the resume; topic rankings irrelevant at this scale |
| 3 | Jul 2026 | Contact info in hero AND footer | Catch both early bouncers and full readers |
| 4 | Jul 2026 | NSBE Senator held off site until Oct 2026 | Match resume; avoid site/resume mismatch |
| 5 | Jul 2026 | Layout/feel from 3 references: Liam Basil (structure, hero+CTA, closer), NewsGHT (whitespace, 2-col about), Bento (rounded cards) | User-selected references win on layout per brief |
| 6 | Jul 2026 | Brand direction B "Krimson": crimson #9E1B32 + cream #F5F0E6, Source Serif 4 + Inter | No pre-existing brand kit; Kappa colors carry real network story; matches warm editorial feel of references |
| 7 | Jul 2026 | Tailark hero-section-5 accepted as donor: keep header + hero skeleton; drop video, logo cloud, InfiniteSlider, ProgressiveBlur, framer-motion, react-use-measure | CLAUDE.md donor rule; dependency diet; video/logo-cloud are SaaS patterns, wrong for recruiter portfolio |
| 8 | Jul 2026 | Context-menu component rejected | No use case on a portfolio; skipped per donor rule 4 |
| 9 | Jul 2026 | Remaining sections (cards, about, footer CTA) hand-built from references | Paywall on 21st.dev; components were a shortcut, not a requirement |
| 10 | Jul 2026 | No scroll/entrance animations | Content must be instantly readable on recruiter skim |
| 11 | Jul 2026 | Crimson as accent only, one large crimson moment (footer band) | Keeps site calm/editorial; prevents fan-site look |
| 12 | Jul 2026 | About portrait: straight-on suit headshot (IMG_2287) over smiling campus photo | Sharper, cleaner background, vertical framing fits rounded frame; matches serious-portrait style of NewsGHT reference. Smiling photo kept as alternate for other channels |
| 13 | Jul 2026 | Heading font: Fraunces -> Source Serif 4 | Fraunces hooked capital J looked off at hero size on "Jonathan"; Source Serif 4 keeps the warm editorial feel with conventional glyphs |

*(Append new rows as decisions are made. Never delete rows — strike through and add a superseding row.)*
