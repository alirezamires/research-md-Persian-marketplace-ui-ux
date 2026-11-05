# 02 — Digikala Pattern (default marketplace clone)

> Source: live Playwright snapshot 2026-11-05 `https://www.digikala.com/` + computed style `{dir:rtl, lang:fa, font:Digikala}`.
> Use this file when the user says "like Digikala".

## Header (verified DOM order)
```
[banner promo top] (promo_name, promo_position=all_mega_menu_top, bCode tracking)
[logo دیجی‌کالا] [search textbox placeholder=جستجو] [اعلان‌ها bell] [ورود | ثبت‌نام button → /users/login/?backUrl=/] [سبد خرید → /checkout/cart/]
nav: [دسته‌بندی کالاها] [شگفت‌انگیزها → /incredible-offers/] [سوپرمارکت] [طلا و نقره دیجیتال → /wealth/] [پرفروش‌ترین‌ها → /best-selling/] [دیجی‌استایل] ... [در دیجی‌کالا بفروشید!] ... [انتخاب آدرس]
```

AI spec:
- Sticky header, white, `border-b`. Search: rounded-lg gray bg `#f1f2f4`, icon at `inline-start`, full-width on mobile below logo row.
- Login button: outlined black, `border`, `ورود | ثبت‌نام`. Cart icon with badge count at `inline-end`.
- Address pill: `📍 انتخاب آدرس` small text under nav (left end in RTL).

## Home sections (exact order to replicate)
1. **Hero slider** — full-width, 8-12 slides, links with `?promo_name=&promo_position=home_slider_new_v2&promo_creative=&bCode=`. Autoplay 5s, dots at bottom-center, arrows mirrored.
2. **Service shortcuts** — 8-10 circular icons horizontal scroll: `دیجی‌استایل`, `طلا و نقره دیجیتال`, `سوپرمارکت`, `اشتراک پلاس`, `وام بانکی، اعتبار خرید`, `تخفیف روشنایی`, `در دیجی‌کالا بفروش`, `فروشگاه‌های حضوری` + `مشاهده همه / بیشتر`. Each: 64px circle image + 12px label.
3. **شگفت‌انگیزها (Incredible offers)** — red bg `#ef4056` section, countdown `۰۵:۲۱:۱۰` (HH:MM:SS fa digits), `مشاهده همه → /incredible-offers/`, horizontal product rail.
4. **Double banners** — 2 promo banners `/landing/*`.
5. **Fresh / سوپرمارکت incredible** — green-tinted, same card pattern, link `/fresh/incredible-offers/`.
6. **Category tiles + brand strip + best-selling rails** (repeat rails per category).

## Product card (copy this)
```html
<a href="/product/dkp-5487416/...?variant_id=...&product_id=..." class="product-card">
  <img src="..." alt="{farsi title}" loading="lazy" aspect="1/1" />
  <p class="title line-clamp-2">{title fa}</p>
  <div class="price-row">
    <span class="badge-discount">۹۰٪</span>
    <del class="old">۱٬۰۵۶٬۰۰۰</del>
  </div>
  <div class="new">۱۰۸٬۰۰۰ <small>تومان</small></div>
</a>
```
- Discount badge: red pill `#ef4056` white text. Old price gray strikethrough 12px. New price bold 16px black + `تومان`.
- Real example: `کپسول ژلاتینی نرم زینک پلاس ... ۹۰٪ ۱٬۰۵۶٬۰۰۰ → ۱۰۸٬۰۰۰`.

## PLP (`/product-list/plp_*?sort=`)
- Filters drawer (right side in RTL = `inline-start`): brand, price range slider (تومان), `موجودی`, `ارسال سریع`, rating.
- Sort bar: `پربازدیدترین | پرفروش‌ترین | ارزان‌ترین | گران‌ترین | جدیدترین`. Default `پیشنهاد خریدارن`.
- URL preserves `?sort=7` etc. for AI routing.

## PDP (`/product/dkp-{id}/{slug}?variant_id=`)
- Breadcrumb RTL: `خانه / موبایل / ...`.
- Gallery right (start), info left (end): title, rating stars + `دیدگاه‌ها`, price box, seller box `فروشنده: دیجی‌کالا`, `گارانتی`, color/size variants, `افزودن به سبد` red button.
- Tabs: `مشخصات فنی | دیدگاه‌ها | پرسش‌ها`. Specs table 2-col striped.
- Cross-sell rail: `کالاهای مرتبط`.

## Cart / Checkout
- `/checkout/cart/` → address → shipping (express / normal) → payment (Shaparak redirect).
- Show `هزینه ارسال`, `سود شما از تخفیف`, progress steps RTL.

## Promo tracking (keep for analytics parity)
- All home links carry `promo_name, promo_position, promo_creative, bCode`. Preserve as `data-promo` attrs in AI output.

## AI prompt snippet
> Build RTL Farsi marketplace homepage like Digikala: sticky header with logo+جستجو+ورود|ثبت‌نام+سبد خرید, mega-menu دسته‌بندی کالاها, hero slider, circular services, شگفت‌انگیزها countdown rail with discount cards (٪ badge, old/new تومان prices). Use Vazirmatn, fa-IR digits, logical CSS.
