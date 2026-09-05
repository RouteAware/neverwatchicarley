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

## ✅ SHOP IS LIVE (2026-08-30, built by Hale via browser after Alexander's signup)
- **Shop: https://neverwatchicarley-com-shop.fourthwall.com** — site set LIVE
  (password page off), theme installed, 5 products PUBLIC:
  Compliance Tee $27 (black) · Compliance Tee (White) $27 · Warning Sticker
  $6 (3x3/4x4/5.5 — 15x3.75 banner size removed, art cropped ugly) ·
  Regulation Mug $16/19/22 (11/15/20oz) · Bureau Hoodie $52. All deadpan copy
  from this doc, verbatim.
- Site teaser swapped → live link ("The bureau now accepts your money →"),
  CLI-deployed to neverwatchicarley.com, verified.
- Notes: hoodie needed a fresh draft (first one corrupted mid-session —
  Fourthwall designer's resize/position menus are flaky; when a publish
  silently fails, reload the details page and retry, or rebuild the draft).
- ✅ POLISH DONE 2026-08-30 (portfolio Fourthwall pass): stock "Bold new
  looks" text banner deleted (with its "Become a member" button); brand
  Image banner installed (masters: merch-art/shop-banner-wide.png +
  shop-poster-*.png — seal + hazard stripes + "This is your only warning");
  theme colors set to brand (Primary #ffd400, bg #f4f4f0, text #111,
  ink-on-yellow buttons). ALSO: a duplicate PUBLIC "Bureau Hoodie"
  (slug bureau-hoodie-2, the corrupted-draft twin) was found and set
  PRIVATE — storefront now shows exactly 5 products. Alexander still owed:
  payout connection check (Settings → Billing and payouts) + optional
  shop.neverwatchicarley.com CNAME (Settings → Domain → Connect domain).


## 2026-09-05 — Comfort Colors migration (portfolio polish, Hale)
- Both Compliance Tees rebuilt from the catalog on **Comfort Colors 1717**
  (Black + White), house print standard applied: **seal 4.06" left chest
  (Fit to area → Left chest) + full-area warning wordmark on the back** (two
  prints, base $21.40). Price $27 → **$32** per the locked table — NOTE that
  yields only **$10.60/sale** because the tee is now two-print; the old
  single-print $27 made ~$15. Owner call whether to go to $38 (=$16.60/sale,
  what the other two-print tees in the portfolio earn).
- New ids: Compliance Tee (black) `2e898ff1-d40c-4dfb-990e-511c4d27dabb` on
  `/products/compliance-tee`; Compliance Tee (White)
  `e67c3430-082b-4a18-871f-dcd4833fd0d9` on `/products/compliance-tee-white`.
  Old Bella tees parked **Private** on `compliance-tee-bc` /
  `compliance-tee-white-bc` (rollback = swap URLs + statuses back).
- Hoodie / mug / sticker untouched.
- Hero: square card `merch-art/shop-hero-card-v3.png` (1350², seal + hazard
  stripes + "THIS IS YOUR ONLY WARNING.", source shop-hero-card-v3.html) SHIPPED 2026-09-05
  as an "Image with text" split section (heading "This is your only warning.",
  button "Comply" → /collections/all); the old cover-crop Image banner is
  HIDDEN, not deleted (rollback = un-hide). Verified desktop + Mobile toggle.
- Domain: Namecheap CNAME `shop.neverwatchicarley.com → shops.fourthwall.com`
  added 2026-09-04 via hale-tools/namecheap_dns.py.
- Gotcha: this shop's product page re-mounts ~8-10s after load — wait 12s
  before opening Change URL / the status popover, and use `find` refs, not
  coordinates, or the typing lands in nothing.

## ORIGINAL SETUP CLICKS (done 2026-08-30, kept for reference)
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
