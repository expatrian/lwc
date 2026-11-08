# Living Word Church: Christmas Toy Campaign 2026

Static donation page for Living Word Church's 2026 Christmas Toy + Grocery Outreach in San Pedro, Ambergris Caye, Belize. Donations are made in crypto through Nicky.

Live at https://lwc-sanpedro.vercel.app (Vercel project `lwc-sanpedro`, deployed from `main`). If a custom domain is added later, update `og:image`, `og:url` and the canonical link in `index.html`.

## Donation settings

Near the bottom of `index.html`:

```js
const NICKY_PAYMENT_ORDER_URL = "https://pay.nicky.me/payment-order/NS66C";
const NICKY_PROFILE_URL = "https://pay.nicky.me/s/NS66C";
const NICKY_SETTLEMENT_ASSET = "USD";
const CAMPAIGN_REFERENCE = "Christmas Toy Campaign 2026";
const MIN_AMOUNT = 1;
```

"Donate with Nicky" opens a pop-up with the disclaimer and the amounts $10, $20, $50, $100 and "Other amount". Each choice opens
`NICKY_PAYMENT_ORDER_URL?amount=…&settlementAsset=USD&reference=Christmas%20Toy%20Campaign%202026` in a new tab.
The preset amounts are the `data-amount` buttons in the pop-up markup. Browsers that can't show the pop-up go to `NICKY_PROFILE_URL`.

"Donate by check" opens a pop-up with the mailing address.

## Structure

- `index.html`: the whole page (markup, styles, the one script above)
- `media/`: photos (WebP, 480 and 739 px wide), video stills, the outreach video (H.264, 480p, title cards trimmed) and the share image
- `vercel.json`: cache headers for media and basic security headers
- `media/caye-bank-logo.png`: Caye International Bank logo (supplied file); band colour `--caye-green` #0F6735 sampled from it
- `favicon.svg` and `media/lwc-logo.svg`: Living Word Church logo (vector redraw from the church's video artwork; replace with the official file when available)

No build step. Vercel serves the folder as-is; every push to `main` redeploys.
