# ZPad Official Website

Source for **[zpad.app](https://zpad.app)** — the official site of [ZPad](https://github.com/pekaboo/ZPad), a native macOS focus panel (terminal + browser, one hotkey away).

## Pages

| Page | Purpose |
|---|---|
| `index.html` | Landing — hero, live interactive demo, bento feature summary, pricing |
| `docs.html` | User guide (14 chapters) |
| `faq.html` | FAQ (5 categories, FAQPage JSON-LD) |
| `changelog.html` | Release timeline |
| `support.html` | Self-serve support + bug report template |
| `demo.html` | Standalone interactive demo |
| `privacy.html` / `eula.html` / `refund.html` | Legal |

## Deploy

GitHub Pages, deployed automatically on push to `main`:

```bash
git add . && git commit -m "..." && git push
```

Custom domain `zpad.app` is wired via the `CNAME` file + a DNS CNAME record pointing at `neo-idea.github.io` (DNS-only, no proxy).

> This site was migrated out of the [ZPad](https://github.com/pekaboo/ZPad) app repo (`website/`) to keep app code and marketing deploys independent.
