# Persian Marketplace UI/UX — AI Implementation Index

> Purpose: give an AI coder everything needed to clone the look, feel and flows of top Persian marketplaces. RTL-first, Farsi-native, mobile-heavy.
> Last verified: 2026-11-05 via live fetch + Playwright DOM snapshot.

## Sites covered
1. **Digikala** (`digikala.com`) — default marketplace, 60% of formal online retail, ~40M monthly users. Reference for PLP/PDP/cart.
2. **Torob** (`torob.com`) — price-comparison engine, search-first, no cart (outbound to shops).
3. **Basalam** (`basalam.com`) — social/artisan bazaar, vendor-first, chat + landing campaigns.
4. **Emalls** (`emalls.ir`) — price-comparison (oldest), traffic driver to shops.
5. **Divar / Sheypoor** — classifieds layer (ad-first, chat-first, no checkout).

## Files in this folder
- `01-rtl-foundation.md` — MUST READ. html dir/lang, fonts, digits, logical CSS, Tailwind config.
- `02-digikala.md` — header, mega-menu, home sections, product card, PLP/PDP/checkout spec.
- `03-torob.md` — search-first price comparison pattern.
- `04-basalam.md` — social bazaar: booths, landings, trust, chat.
- `05-emalls-divar.md` — Emalls + Divar/Sheypoor classified patterns.
- `06-design-tokens.md` — copy-paste tokens: colors, type scale, spacing, radius, shadows, components.
- `07-ai-implementation-guide.md` — prompts + page scaffolds to generate a Persian marketplace.

## How to use as AI context
1. Always inject `01-rtl-foundation.md` + `06-design-tokens.md` first.
2. Add one site file (02/03/04/05) depending on which UX you clone.
3. Follow `07-ai-implementation-guide.md` for page order: Header → Home → PLP → PDP → Cart/Checkout.
4. Never use `margin-left/right`, `text-align: left`. Use logical properties (see 01).

## Key findings (TL;DR for prompts)
- All: `<html dir="rtl" lang="fa">`, Persian digits `۰۱۲۳۴۵۶۷۸۹`, prices in تومان with `٬` thousand separator, no decimals.
- Digikala header (RTL order right→left): logo → search (`جستجو`) → notifications → `ورود | ثبت‌نام` → `سبد خرید`. Verified live.
- Digikala home order: promo hero slider → circular service shortcuts → `شگفت‌انگیزها` countdown + horizontal product rail → double banners → `سوپرمارکت` fresh offers.
- Product card: image 1:1, Farsi title 2-line clamp, discount `%` red badge + strikethrough old price + bold new price + تومان.
- Torob: no cart, big centered search `مقایسه قیمت میلیون‌ها محصول بین هزاران فروشگاه`, left list = lowest price shop, trust = `راهنمای خرید امن`, `پیگیری سفارش`.
- Basalam: top secondary nav (`طلای آنلاین`, `خرید اعتباری`, `خرید عمده`), quick-access icon grid, campaign landings `/landings/*`, product URL `/{vendor}/product/{id}`, trust strip: `پرداخت امن`, `تضمین بازگشت وجه`, `ارتباط مستقیم با آدم‌ها`.
