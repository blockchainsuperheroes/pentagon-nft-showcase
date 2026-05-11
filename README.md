# Pentagon Profile & NFT Showcase 🛡️

A Linktree-style profile page + NFT showcase for the Pentagon Games ecosystem. Single HTML file, no build step — fork it and host your own.

**[Live Demo →](https://blockchainsuperheroes.github.io/pentagon-nft-showcase/?address=0x37224cFD71347Da6f097c94B8649f9C552f803c9)**

![Pentagon Profile](https://img.shields.io/badge/Pentagon-Profile%20%2B%20NFTs-gold?style=for-the-badge)

---

## What It Does

**Default view: Social Profile (Linktree-style)**
- Profile card with avatar, username, verified badge, VIP tier
- Wallet address with click-to-copy + QR code
- Customizable social links (your Twitter, Discord, Telegram, website, etc.)
- Chain breakdown showing NFT distribution

**NFTs tab: Full collection browser**
- NFT grid grouped by collection
- Filter by chain and collection
- Responsive image display (no cropping)
- Shareable URLs with `?address=0x...`

Uses the [Pentagon Verify API](https://verify.pentagon.games) for identity and [Pentagon NFT Data API](https://nft-data.pentagon.games) for multi-chain NFT indexing.

---

## Quick Start

### GitHub Pages (recommended)
1. Fork this repo
2. Go to **Settings → Pages → Source: main branch**
3. Live at `https://yourusername.github.io/pentagon-nft-showcase/`

### Any static host
```bash
git clone https://github.com/blockchainsuperheroes/pentagon-nft-showcase.git
open index.html
```

No npm. No build. No config.

---

## Customization

### Add Your Social Links
Edit the `SOCIAL_LINKS` array in `index.html`:

```javascript
const SOCIAL_LINKS = [
  { icon: '🐦', label: 'Twitter / X', url: 'https://x.com/YOUR_HANDLE' },
  { icon: '💬', label: 'Discord', url: 'https://discord.gg/YOUR_INVITE' },
  { icon: '📱', label: 'Telegram', url: 'https://t.me/YOUR_GROUP' },
  { icon: '🌐', label: 'Website', url: 'https://yoursite.com' },
];
```

Leave `SOCIAL_LINKS` empty to show default Pentagon Games links.

### Set a Default Wallet
Link directly with a URL param:
```
index.html?address=0xYOUR_WALLET_HERE
```

### Change Colors
Edit CSS variables:
```css
:root {
  --bg: #140d26;     /* background */
  --gold: #d4a84a;   /* accent */
  --purple: #9d7de0; /* secondary */
}
```

### Add Your Logo
Replace the avatar emoji in the `.avatar` element or add an `<img>` tag.

---

## Use Cases

- **Personal profile page** — your own web3 Linktree
- **peg.gg** — default template for Pentagon identity pages (e.g., `nftprof.peg.gg`)
- **pentagon.games/acc/username** — user profile pages
- **Community tools** — look up any wallet's Pentagon identity
- **Project showcase** — show your collection on your website

---

## API Reference

### Pentagon Verify API
```
GET https://verify.pentagon.games/api/user/verify?q={address_or_username}
```
Returns: username, VIP tier, verified status, account type

### Pentagon NFT Data API
```
GET https://nft-data.pentagon.games/api/v1/nft/owner/{address}
```
Returns: NFTs across all indexed chains (Pentagon, Ethereum, Polygon, BSC, Oasys, etc.)

### Rate Limits
| Tier | Limit | Access |
|------|-------|--------|
| Public | 10 req/min | Default |
| VIP1+ | 30-120 req/min | [Get API key](https://vip.pentagon.games/mydata) |

---

## Roadmap

- [ ] Username → wallet resolution
- [ ] peg.gg subdomain integration
- [ ] ENS / Pentagon name display
- [ ] Custom themes / light mode
- [ ] Activity feed tab

---

## License

MIT

---

Built by [Pentagon Games](https://pentagon.games) · [Discord](https://discord.gg/pentagongamesxp) · [Twitter](https://x.com/pentagongamesxp)
