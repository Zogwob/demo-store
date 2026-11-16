## Demo Store — HTML Online Store Template: Buyer Guide

### What you bought

A single-file HTML storefront: homepage, category browsing, product
catalogue, quick view, slide-out cart and demo checkout. No backend,
database or build step is needed to preview it: open `index.html` in a
browser. It is responsive on mobile and desktop and follows the system
dark mode. Fonts are Manrope (body) and DM Serif Display (headings),
loaded from Google Fonts with system fallbacks.

### Files in the package

- `index.html` — the whole store: markup, styles and script in one file
- `assets/` — 9 sample product photos (see below)
- `assets/IMAGE-CREDITS.txt` — what those photos are
- `README.md` — this guide

### Before you use it for a real store — read this first

"Demo Store" is a placeholder name. The store name, products,
testimonials and photos are sample content only and MUST be replaced
with your own before real use. Three flows are simulations in this
template and must be connected to your own services before real use:

- **Checkout** processes no payment, places no real order and sends no
  confirmation email. Order numbers starting with `DS-` are samples.
  Connect your own payment gateway, order system and email service.
- **Newsletter** validates the email on the page and shows the sample
  code `DEMO10`, but sends no email and stores no address. Connect your
  own email service (for example Mailchimp or a similar provider).
- **Track your order** shows a fixed sample status for any order number
  you type in. Connect your own order-tracking system (your order
  database, store platform or courier service) before customers can look
  up a real order.

### 1. Change the store name and texts

Search `index.html` for "Demo Store" and replace every occurrence with
your store name, including the announcement bar, hero, footer and the
demo disclaimer in the footer. Also rewrite the footer Help/Company
modal texts (shipping, returns, warranty, story, materials,
sustainability, wholesale, careers, contact) to match your real policies
— they are sample texts, not your policies.

### 2. Replace the products

All products live in one place: the `PRODUCTS` array near the bottom of
`index.html`, in the page script. Each product has these fields:

- `id` — short unique key, also used by the cart (for example `vase`)
- `name`, `desc`, `meta` — name, description and spec bullets
- `cat` — category code: `home`, `tech`, `accessories` or `beauty`
- `catLabel` — the label shoppers see (Home Living, Tech, Accessories,
  Beauty & Care)
- `price`, `old` — selling price and struck-through old price
  (`old: null` means no discount shown)
- `rating`, `reviews`, `badge` — rating, review count and badge text
  (for example "Bestseller", "New", "Save 24%")
- `img`, `alt` — image path and alt text

To add a product, copy one entry and give it a new unique `id`. To
remove one, delete its entry. Do not reuse an `id` twice.

### 3. Replace the photos

The 9 sample photos are real licensed photos from Pexels (free for
commercial use under the Pexels License — see `assets/IMAGE-CREDITS.txt`
for the photographers and photo pages). They are still samples of
products you do not sell — replace them with photos of your own real
products before real use.

Filenames in `assets/`:

- `vase.jpg`, `headphones.jpg`, `candle.jpg`, `tote.jpg`, `watch.jpg`,
  `sunglasses.jpg`, `backpack.jpg`, `lamp.jpg`, `serum.jpg`

Easiest route: keep the same filenames and overwrite the files with
your own photos. If you rename a photo, update the matching product's
`img` field in the `PRODUCTS` array to the new path.

### 4. Change colours, shipping threshold and promo text

- **Colours:** edit the CSS variables in `:root` at the top of the
  `<style>` block in `index.html` — `--bg`, `--surface`, `--accent`
  (deep green), `--gold`, `--sale` and the rest. Both light and dark
  mode values live there (the dark set is inside the
  `@media (prefers-color-scheme: dark)` block).
- **Free-shipping threshold:** change `var FREE_SHIP = 75;` in the page
  script, and update the matching texts ("Free worldwide shipping on
  orders over $75" in the announcement bar, feature strip and shipping
  modal) to the same amount.
- **Announcement / promo:** edit the announcement bar text at the top of
  the page body (currently "Autumn Edit: up to 25% off") and the promo
  section to match your own offer.

### 5. Connect the three simulated flows (required before real use)

1. **Payments + orders:** replace the demo checkout confirmation with
   your payment gateway's checkout and your order system, so a real
   payment creates a real order and a real confirmation email.
2. **Newsletter:** point the subscribe form at your email service's
   form endpoint or API, and remove or replace the on-page `DEMO10`
   sample code with your own welcome offer (or none).
3. **Order tracking:** point the track form at your order system or
   courier tracking, so an order number returns that order's real status
   instead of the fixed sample timeline.

Until those three are connected, this template is a storefront demo,
not a working shop — do not take real customer payments through it.

### 6. Categories — one thing to know

The catalogue filter chips cover All, Home, Tech, Accessories and
Beauty. The footer Shop links, however, list only All products, Home
Living, Accessories and Beauty & Care — there is no footer link for
Tech. So the one sample tech product (headphones) is reachable from the
Tech filter chip, "All products" and search, but not from a footer
category link. If you keep a tech product, add a matching footer link
(`data-cat-link="tech"`) the same way the other categories are wired,
or change its `cat` to one of the linked categories.
