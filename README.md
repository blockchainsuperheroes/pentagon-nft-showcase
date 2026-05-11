# Pentagon NFT Showcase 🖼️

A ready-to-deploy single-page template that displays any wallet's NFT collection across all Pentagon-indexed chains. No build step, no framework — just HTML, CSS, and vanilla JavaScript.

**[Live Demo →](https://blockchainsuperheroes.github.io/pentagon-nft-showcase/?address=0x37224cFD71347Da6f097c94B8649f9C552f803c9)**

![Pentagon NFT Showcase](https://img.shields.io/badge/Pentagon-NFT%20Showcase-gold?style=for-the-badge)

---

## What This Does

Paste any wallet address and instantly see:
- **All NFTs** across Pentagon Chain, Ethereum, Polygon, BSC, Oasys, and more
- **Grouped by collection** with count badges
- **Filterable by chain** and collection via dropdowns
- **Shareable links** — `?address=0x...` in the URL auto-loads that wallet

Powered by the [Pentagon NFT Data API](https://nft-data.pentagon.games), which indexes 370,000+ NFTs across 14+ chains.

---

## Quick Start

### Option 1: GitHub Pages (recommended)
1. Fork this repo
2. Go to **Settings → Pages → Source: main branch**
3. Your page is live at `https://yourusername.github.io/pentagon-nft-showcase/`
4. Share links like: `https://yourusername.github.io/pentagon-nft-showcase/?address=0xYOUR_WALLET`

### Option 2: Local / Any hosting
1. Clone or download this repo
2. Open `index.html` in any browser — it works offline-ish (needs API access)
3. Or drop it on any static host: Netlify, Vercel, S3, your own server

```bash
git clone https://github.com/blockchainsuperheroes/pentagon-nft-showcase.git
cd pentagon-nft-showcase
open index.html
```

That's it. No `npm install`. No build. No config.

---

## Customization

Everything is in a single `index.html` file. Easy to tweak:

### Colors
Edit the CSS variables at the top:
```css
:root {
  --bg: #140d26;        /* page background */
  --gold: #d4a84a;      /* accent color */
  --purple: #9d7de0;    /* secondary accent */
  --text: #f5eefc;      /* main text */
}
```

### Add Your Logo
Replace the hero `<h1>` with your own branding:
```html
<div class="hero">
  <img src="your-logo.png" alt="My Project" style="height: 60px; margin-bottom: 16px;" />
  <h1>My <span class="accent">Project</span> Collection</h1>
</div>
```

### Add More Chains
Add entries to the `CHAINS` object in the `<script>` section:
```javascript
const CHAINS = {
  3344:  { name: 'Pentagon', class: 'chain-pentagon' },
  1:     { name: 'Ethereum', class: 'chain-ethereum' },
  // Add your chain:
  42161: { name: 'Arbitrum', class: 'chain-arbitrum' },
};
```

### Default Wallet
Pre-fill a wallet by adding it to the URL:
```
index.html?address=0xYOUR_WALLET_HERE
```

### Use as a Profile Page
Host this as your personal NFT profile — perfect for:
- **peg.gg pages** (e.g., `nftprof.peg.gg`)
- **pentagon.games/acc/username** profiles
- Your own domain pointing to your collection

---

## API Reference

This template uses the **Pentagon NFT Data API** — a public, multi-chain NFT indexer.

### Endpoint

```
GET https://nft-data.pentagon.games/api/v1/nft/owner/{address}
```

### Parameters
| Param | Type | Default | Description |
|-------|------|---------|-------------|
| `address` | path | required | Wallet address (0x...) |
| `page` | query | 1 | Page number |
| `limit` | query | 50 | Results per page (max 50) |

### Response
```json
{
  "owner": "0x37224cFD71347Da6f097c94B8649f9C552f803c9",
  "total": 17,
  "page": 1,
  "limit": 50,
  "nfts": [
    {
      "chain": 3344,
      "collection": "Gunnies PFP",
      "contractAddress": "0x7a8a3236e...",
      "image": "https://storage.googleapis.com/pgpublic-access/gunnies-pfp/10073.png",
      "name": "Emerald #10073",
      "owner": "0x37224cFD...",
      "tokenId": "10073",
      "updatedAt": "2026-05-09T15:50:05+00:00"
    }
  ]
}
```

### Chains Indexed
| Chain ID | Network |
|----------|---------|
| 3344 | Pentagon Chain |
| 1 | Ethereum |
| 137 | Polygon |
| 56 | BSC |
| 5555 | Oasys |
| + more | Being added |

### Rate Limits

| Tier | Limit | How to Get |
|------|-------|-----------|
| Public (no key) | 10 req/min | Default — just use the API |
| VIP1 | 30 req/min | [Get a VIP API key](https://vip.pentagon.games/mydata) |
| VIP2 | 60 req/min | VIP2 membership |
| VIP3 | 120 req/min | VIP3 membership |

For higher limits, generate an API key at [vip.pentagon.games/mydata](https://vip.pentagon.games/mydata) and pass it as an `X-API-Key` header.

---

## Use Cases

- **Personal NFT showcase** — your own mini-OpenSea for your collection
- **Project profile pages** — show holders' NFTs on your project site
- **peg.gg integration** — default template for Pentagon identity pages
- **Portfolio tracking** — simple, no-login-required portfolio viewer
- **Community tools** — let members look up each other's holdings

---

## Roadmap

- [ ] Username lookup (resolve `nftprof` → wallet address)
- [ ] peg.gg subdomain integration
- [ ] Collection metadata (floor price, total supply)
- [ ] Theme switcher (light/dark)
- [ ] Export as image/PDF

---

## License

MIT — do whatever you want with it.

---

Built by [Pentagon Games](https://pentagon.games) · [Discord](https://discord.gg/pentagongamesxp) · [Twitter](https://x.com/pentagongamesxp)
