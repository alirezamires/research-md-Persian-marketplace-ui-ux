# 07 — AI Implementation Guide (how to generate a Persian marketplace)

> Feed to coder agent with 01 + 06 + one site file.

## Step 0 — System prompt (paste)
```
You build RTL Farsi e-commerce. Always: <html dir="rtl" lang="fa">, Vazirmatn font,
fa-IR digits (۱۲۳...), تومان prices with ٬, logical CSS (ms/me/ps/pe/start/end, no left/right),
mobile-first 2-col grid → desktop 5-col. Header order (right→left): logo, search جستجو, login ورود|ثبت‌نام, cart سبد خرید.
```

## Step 1 — Scaffold routes
- `/` home, `/search?q=`, `/product-list/plp_*` (PLP), `/product/dkp-{id}` (PDP), `/checkout/cart`, `/incredible-offers`, `/sellers`, `/landings/[slug]` (Basalam), `/compare/[id]` (Torob price-list).
- Keep Digikala promo params: `?promo_name=&promo_position=&promo_creative=&bCode=` as data attrs.

## Step 2 — Build order (one at a time)
1. Header + mega-menu (`دسته‌بندی کالاها`) + address pill (`انتخاب آدرس`).
2. Home: hero slider → service circles → شگفت‌انگیزها countdown rail → banners → fresh rail.
3. Product card component (see 06) + price helper `fa-IR`.
4. PLP with filters (start-side drawer) + sort.
5. PDP: gallery (start) + info (end) + seller/guarantee + tabs + related rail.
6. Cart → address → shipping → Shaparak placeholder (`پرداخت امن از درگاه بانکی`).
7. Footer + Enamad seals + app badges (کافه‌بازار/مایکت/سیب‌اپ).

## Step 3 — Data mocks (Farsi)
- 12 products with real-style titles: `کپسول ژلاتینی نرم زینک پلاس فلکسان بسته 60 عددی`, prices `{old:1056000, new:108000, off:90}` → render fa.
- Shops: `فروشنده: دیجی‌کالا`, `غرفه: ...` for Basalam, shop list with `ارزان‌ترین` for Torob.

## Step 4 — QA (must pass)
- [ ] No `left/right` in CSS, carousel starts right, chevrons mirrored.
- [ ] All prices `toLocaleString('fa-IR') + ' تومان'`, countdown Persian digits.
- [ ] Search `جستجو`, empty states in Farsi, OTP/Postal inputs RTL.
- [ ] Lighthouse mobile + a11y: labels on search/cart, alt on images.

## Copy-paste tasks for subagents
- "Build header per research/02-digikala.md using tokens 06 + RTL 01."
- "Build price-list PDP per research/03-torob.md with نمودار قیمت."
- "Build booth page per research/04-basalam.md with گفت‌وگو CTA."
