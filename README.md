# ZPad Official Website

Source for **[zpad.app](https://zpad.app)** — the official site of ZPad, a native macOS focus panel (browser + terminal + editor, one hotkey away).

> ZPad is **commercial, closed-source software**. This repository contains marketing/documentation pages only — no application source code.

## Pages

| Page | Purpose |
|---|---|
| `index.html` | Landing — hero typewriter, live interactive panel demo, feature spec grid, pricing |
| `download.html` | Download page (DMG: `https://zpad.app/ZPad.dmg`) |
| `get.html` | No-index download redirect (meta-refresh + JS fallback) → `ZPad.dmg` |
| `docs.html` | User guide (14 chapters) |
| `faq.html` | FAQ (5 categories, FAQPage JSON-LD) |
| `changelog.html` | Release timeline |
| `support.html` | Self-serve support paths + bug report template |
| `privacy.html` / `eula.html` / `refund.html` | Legal |

## Design

The site uses the **“Field Manual”** design language — a technical-editorial system: warm ivory paper, near-black ink, a single vermilion accent, Fraunces display type with Geist UI/mono. Shared tokens and components live in [`assets/site.css`](assets/site.css); direction notes in [`DESIGN.md`](DESIGN.md).

The interactive demo on `index.html` is the page itself: the panel engine summons a faithful mock of the real ZPad panel from the screen edge (hot zone, `⌘⌥P`, hover-to-keep-open, manual mode). Its behavior mirrors the shipping app — treat that engine as load-bearing and verify it end-to-end after any change.

## Deploy

Static hosting, deployed automatically on push to `main`:

```bash
git add . && git commit -m "..." && git push
```

Custom domain `zpad.app` is wired via the `CNAME` file and DNS.

## Content rules

- **No third-party code-hosting links.** ZPad is a paid product — pages must not reference repositories, issue trackers, or release hosts.
- Download CTAs point to `download.html`; support/contact points to `support.html` or `hello@zpad.app`.
- The download button targets `https://zpad.app/ZPad.dmg` — update hosting there when a new build ships.
- Facts stay in sync everywhere: **$69 founding lifetime price (first 500, then $99)**, **3 Macs per license**, 30-day trial, 14-day refund, macOS 15.1+ / Apple Silicon (arm64).
- Icons are inline SVG only — no emoji in page UI.
