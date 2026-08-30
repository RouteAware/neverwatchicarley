# NWIC merch — the automated shop (Fourthwall)

_Staged by Hale 2026-08-29. Alexander's part ≈ 20 min of clicks; everything
else is prepped here. Deadpan rules apply to ALL product copy._

## Why Fourthwall (verified 2026-08-29)
- **$0/month free plan**; hosted storefront (no Shopify bill, no code).
- **Fully automated**: they print, ship, process payment, handle customer
  support AND act as **Merchant of Record — sales tax is their problem**
  (huge for a solo operator).
- You set retail price over base cost and keep the margin (card processing
  2.9% + $0.30). Example: Bella+Canvas tee base ≈ $11.75.
- Printful alternative rejected: needs an external storefront (Shopify = a
  monthly bill) for the same shirts.
- Sources: fourthwall.com/print-on-demand · ecomm.design/fourthwall-pricing ·
  printful.com/printful-vs-fourthwall

## Print files (merch-art/, all transparent PNG, verified at the byte level)
| File | Size | Use on |
|---|---|---|
| print-shirt-seal-wordmark.png | 4500×6300 | light garments, poster |
| print-shirt-seal-wordmark-dark.png | 4500×6300 | BLACK/dark garments (paper-white ink) |
| print-seal.png | 4500×4500 | stickers, mugs, hats (light) |
| print-seal-dark.png | 4500×4500 | dark products |
| seal*.svg / seal-wordmark*.svg | vector masters | source of truth — edit these, re-render |

Re-render command (headless Chrome, transparent):
`"/Applications/Google Chrome.app/Contents/MacOS/Google Chrome" --headless --disable-gpu --default-background-color=00000000 --window-size=4500,6300 --screenshot=OUT.png "file://$PWD/IN.svg"`

## v1 product lineup + suggested retail (deadpan names locked)
| Product | Art | Base (est.) | Retail | Margin (pre-fees) |
|---|---|---|---|---|
| **Compliance Tee** (black) | wordmark-dark | ~$12 | $27 | ~$15 |
| **Compliance Tee** (white/paper) | wordmark | ~$12 | $27 | ~$15 |
| **Warning Sticker** (die-cut) | seal | ~$3 | $5 | ~$2 |
| **Regulation Mug** | seal + tagline | ~$8 | $18 | ~$10 |
| **Bureau Hoodie** (black) | wordmark-dark | ~$25 | $48 | ~$23 |

## Product copy (paste as-is — the deadpan never breaks)
- **Compliance Tee** — "A garment for the compliant. Wearing it does not
  grant authority. It simply lets others know you were warned, and listened."
- **Warning Sticker** — "Adheres to most surfaces. The warning transfers to
  anyone who reads it. Apply responsibly."
- **Regulation Mug** — "Holds approximately one serving of liquid while you
  reflect on your choices. Dishwasher safe. The warning is permanent."
- **Bureau Hoodie** — "Official cold-weather compliance wear. The hood does
  not exempt the wearer from the warning."
- Store description — "Official merchandise of the warning. Every purchase
  funds the continued operation of this notice. This is not a threat. It is
  a statement of operational reality."

## ALEXANDER'S CLICKS (one-time, ~20 min, phone or desktop)
1. Go to **fourthwall.com** → Get started → create the account with
   info@alexandermhughes.com. (Accounts/payments are yours by our rules.)
2. Shop name: **Never Watch iCarley** · handle: `never-watch-icarley` (or
   nearest available). Skip themes — defaults are fine; Hale restyles later.
3. When asked to connect payout: your bank via their flow (Recursis account).
4. Products → Create product → upload from `~/Desktop/NWIC-Site/merch-art/`:
   the 5 products in the table above (dark art on dark garments, light on
   light). Paste names/copy/prices from this doc verbatim.
5. Settings → Domain → add custom domain: **shop.neverwatchicarley.com**.
   Fourthwall shows a CNAME target. Then in Namecheap (this domain's DNS is
   Namecheap BasicDNS — verified 2026-08-29): Domain List →
   neverwatchicarley.com → Advanced DNS → Add record → type **CNAME**,
   host **shop**, value = the target Fourthwall showed → save.
   (Optional shortcut: skip the custom domain entirely — the built-in
   *.fourthwall.com shop URL works fine for launch.)
6. Tell Hale "shop is live at <link>" — everything below is his.

## HALE'S FOLLOW-UPS (after the shop exists)
- Verify shop.neverwatchicarley.com resolves + certs (or the fourthwall URL).
- Swap the site's "Store opening soon" teaser → real store link (keep deadpan:
  "The Bureau now accepts your money.").
- Order screenshots pass: click-test the storefront, check product mockups.
- Update ROADMAP + HALE.md; note first-sale date when it happens.

## Standing rules for the shop
- Deadpan never breaks — product copy, order emails (Fourthwall templates
  stay default/plain), everything.
- Never name the real show; no show imagery, no lookalike characters — our
  art is ONLY the original prohibition-TV mark and wordmark. (Parody words
  are one thing; merch with a show's IP is a costlier fight. Our mark is
  100% original — keep it that way.)
- Prices honest, shipping honest, no fake scarcity/drops.
