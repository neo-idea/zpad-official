# ZPad Official Website

Source for **[zpad.app](https://zpad.app)** — the official site of ZPad, a native macOS focus panel (terminal + browser, one hotkey away).

> ZPad is **commercial, closed-source software**. This repository contains marketing/documentation pages only — no application source code.

## Pages

| Page | Purpose |
|---|---|
| `index.html` | Landing — hero, live interactive demo, bento feature summary, pricing |
| `download.html` | Download landing page (DMG: `https://zpad.app/ZPad.dmg`) |
| `docs.html` | User guide (14 chapters) |
| `faq.html` | FAQ (5 categories, FAQPage JSON-LD) |
| `changelog.html` | Release timeline |
| `support.html` | Self-serve support + bug report template |
| `demo.html` | Standalone interactive demo |
| `privacy.html` / `eula.html` / `refund.html` | Legal |

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
