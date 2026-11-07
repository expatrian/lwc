# Living Word Church: Toy + Grocery Outreach 2026

Static donation page for Living Word Church's 2026 Christmas Toy + Grocery Outreach in San Pedro, Ambergris Caye, Belize. Donations are made in crypto through Nicky.

Live at https://lwc-sanpedro.vercel.app (Vercel project `lwc-sanpedro`, deployed from `main`). If a custom domain is added later, update `og:image`, `og:url` and the canonical link in `index.html`.

## Turning donations on

Open `index.html`, find this line near the bottom and paste the Nicky donation link between the quotes:

```js
const NICKY_DONATION_URL = "";
```

While it is empty, the page shows "Crypto donations open shortly" and the donate buttons scroll to the explanation instead of opening a checkout. The link must start with `https://`.

## Structure

- `index.html`: the whole page (markup, styles, the one script above)
- `media/`: photos (WebP, 480 and 739 px wide), video stills, the outreach video (H.264, 480p, title cards trimmed) and the share image
- `vercel.json`: cache headers for media and basic security headers
- `favicon.svg`: gift icon

No build step. Vercel serves the folder as-is; every push to `main` redeploys.
