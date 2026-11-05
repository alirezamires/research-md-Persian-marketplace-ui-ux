# 04 — Basalam Pattern (social / artisan bazaar)

> Source: live fetch `https://basalam.com/` 2026-11-05.
> Use when user says "like Basalam / social shop / غرفه / bazaar".

## Positioning
- Slogan: `باسلام؛ بازار بی‌مرز` + `بازار بی‌مرز و پر از زندگی!` — human, chatty tone (vs Digikala formal).
- Vendor = `غرفه` (booth), not seller. Buyer talks to real people. Categories skew food/handmade/fashion.

## Header (verified)
- Logo SVG + `دسته‌بندی‌ها` + `سبد خرید`.
- Secondary nav (unique): `طلای آنلاین`, `خرید اعتباری`, `خرید عمده`, `خرید سازمانی` (B2B + BNPL + gold — high-trust tickets).
- Quick-access icon grid (campaign-driven, changes weekly): `تخفیف‌ها`, `ارسال رایگان`, `موتور قسطی`, `بی‌واسطه`, `مواد غذایی`, `حراج`, `لوازم تحریر`, `طلا قسطی`, `خرده‌ریزه‌های ارزون`, `لوازم ورزشی`, `لوازم آرایشی قسطی`, `بازار پوشاک`, `اینستاگرامی‌ها`, `وام ۱۰۰ میلیونی`, `سلام‌پرو`.

## Home
- No big hero slider. Instead: campaign icon grid → `تخفیف‌های هیجان‌انگیز` product rail → banner trio → trust strip.
- Product card same as Digikala but with vendor name under title: `{title} — از غرفه {name}` + chat button `گفت‌وگو`.
- Example: `همزن دسینی مدل 268 — 3٬700٬000 ٪5 → 3٬515٬000` with vendor link `/{vendor}/product/{id}`.

## Booth (vendor page — core pattern, no Digikala equivalent)
```
[booth banner + avatar + name + followers + rating]
[درباره غرفه | محصولات | نظرات | شرایط ارسال]
[chat CTA: گفت‌وگو با غرفه‌دار] [دنبال کردن]
[product grid]
```

## Landing campaigns (`/landings/*`)
- Every campaign is a landing: `/landings/gold-bnpl-v2`, `/free-shipping-fashion`, `/cheap-general-products`, `/stationery-aban`.
- AI must support CMS landings with `?utm_source=basalam&utm_medium=...` tracking.

## Trust strip (verified footer top)
- `پرداخت امن از درگاه بانکی` / `تضمین بازگشت وجه توسط باسلام` / `ارتباط مستقیم با آدم‌ها` / `پشتیبانی آنلاین و تلفنی`.
- Footer cols: About (`مجله باسلام`, `درباره باسلام`, `قوانین و شرایط بازار`, `اکوسیستم سلام`) / Support (`تماس با ما`, `سوالات متداول`, `پیگیری سفارش‌ها`) / Buy-Sell (`فروش در باسلام`, `کیف پول من`, `مدیریت غرفه`) / Apps (`کافه‌بازار`, `مایکت`, `سیب‌اپ`).
- Seals: Enamad, Samandehi, Qom STP. Email capture: `ایمیلت رو وارد کن تا از تخفیف‌ها باخبر بشی + ارسال`.

## Verified live 2026-11-05 (Playwright)
- PDP: `https://basalam.com/sepahi_online_sales/product/21026913` → title `خرید و قیمت همزن دسینی مدل 268 از غرفه سپاهی آنلاین`, h1 product, has chat + booth, CTAs: `افزودن به سبد`, `ایجاد غرفه`, `عضویت ورود`. Pattern: `خرید و قیمت {product} از غرفه {vendor}` + URL `/{vendor}/product/{id}`.

## AI prompt snippet
> Build RTL social bazaar like Basalam: secondary nav (طلای آنلاین، خرید اعتباری، خرید عمده), icon campaign grid, product rails with غرفه name + chat button, booth page with گفت‌وگو CTA, trust strip (پرداخت امن، بازگشت وجه، ارتباط مستقیم). Warm tone, Vazirmatn, fa-IR prices.
