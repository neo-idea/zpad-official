# ZPad Site — Design System "Field Manual" (v2)

Direction in one line: **a technical field manual for a precision tool — warm ivory
paper, near-black ink, one vermilion signal color, serif display type, hairline
datasheet rules — with the living product demo floating dark above the paper.**

This replaced the previous "Ethereal Glass" direction (dark canvas, red glow,
glassmorphism) in the 2026 site redesign.

## Why this direction

- The product is a native, engineered tool (Swift + SwiftUI, not Electron). The
  site reads like the printed manual that ships with good instruments:
  numbered sections, spec tables, restrained color, honest typography.
- Almost every AI-generated template site is dark-with-glow; ivory paper with
  ink rules is the fastest visual differentiator, and it photographs the dark
  demo panel beautifully (device-on-desk contrast).
- One accent color only. Vermilion is used for signal, never decoration:
  kickers, key indices, the caret, the primary CTA's action chip, prices.

## Tokens

Defined once in `assets/site.css` (`:root`), consumed by all ten pages.

| Token | Value | Use |
|---|---|---|
| `--paper` | `#F7F4ED` | page canvas |
| `--paper-2` / `--paper-3` | `#F0ECE2` / `#E9E4D7` | recessed bands, code chips |
| `--plate` | `#FCFAF4` | card surface |
| `--ink` | `#1C1712` | text, primary buttons, rules |
| `--ink-2` / `--ink-3` / `--ink-4` | `#51483F` / `#7C7266` / `#A69D8F` | text ramp (all ≥ 4.5:1 on paper for body sizes) |
| `--accent` | `#D9481F` | vermilion — fills, marks, large text |
| `--accent-ink` | `#A93A11` | accessible accent for small text/links |
| `--green` / `--amber` | `#1E7A44` / `#92600A` | semantic only (tips, warnings) |
| `--line` / `--line-strong` | ink @ 15% / 34% | hairlines and structural rules |
| radii | 8 / 12 / 18 px | print-like, never pill (except chips) |
| `--ease` | `cubic-bezier(.32,.72,0,1)` | all motion |

## Typography

- **Display:** Fraunces (serif, optical sizing), 600 weight, tight tracking —
  headlines and numerals. Italic used sparingly for one emphasized word.
- **UI/body:** Geist 400–650.
- **Mono voice:** Geist Mono — kickers, section indices, labels, code, footer
  meta. The mono voice *is* the brand's terminal heritage.
- Load via one Google Fonts link; `display=swap`; system fallbacks first paint.

## Component language

- **Buttons:** primary = solid ink with paper text + vermilion circular action
  chip (arrow). Ghost = 1px ink border. No gradients, no glows.
- **Sections:** every section opens with a hairline rule, mono kicker left,
  `01 / 02 / 03` index right (datasheet numbering).
- **Cards:** `--plate` surface, 1px `--line` border, 12px radius, no shadows
  (shadow only on hover lift and the demo panel).
- **Tables:** ruled spec tables inside 1px wrappers — the pricing and privacy
  pages lean on these instead of card spam.
- **Icons:** inline SVG, 1.8 stroke, ink or accent. **No emoji icons anywhere.**
- **kbd:** physical keycap look (paper gradient, 2.5px bottom edge).

## The demo panel (index.html only)

The interactive panel mirrors the real macOS app, so it keeps its **own dark
chrome** (`rgba(30,30,34,.78)` glass, terminal green/amber palette, app-red tab
highlights) defined inline in `index.html` — deliberately *not* part of
`assets/site.css`. Dark app on ivory paper is the signature composition.
Its behavior contract (hot-zone summon, poll-based auto-close, ⌘⌥P manual mode,
typing-keeps-open) must never be broken; see the QA checklist in README.

## Motion

- Reveal = 14px rise + fade, 0.7s. No blur transitions.
- All motion respects `prefers-reduced-motion` (global kill switch in
  `assets/site.css`).
- Hover never changes layout (transform/border/shadow only).

## Accessibility bar

- Body text ≥ 4.5:1; large display text ≥ 3:1.
- Full keyboard path: skip link, visible focus rings (vermilion), details/summary
  FAQs, no hover-only affordances.
- Every page: canonical URL, OG/Twitter meta, JSON-LD where applicable.
