# 03 — Torob Pattern (price-comparison)

> Source: live fetch `https://torob.com/` 2026-11-05.
> Use when user says "like Torob / price comparison / ترب".

## Positioning
- Not a store. Slogan: `ترب | بهترین قیمت بازار` + sub `مقایسه قیمت میلیون‌ها محصول بین هزاران فروشگاه`.
- No cart/checkout. CTA = outbound to cheapest shop. Trust via transparency, not fulfillment.

## Header / Nav (verified)
- Top utility links: `راهنمای خرید امن`, `پیگیری سفارش`, `پشتیبانی`, `درباره ترب`, `پیشنهاد ویژه`, `نصب اپلیکیشن`.
- Auth: `ورود / ثبت نام`. Seller links: `ترب‌پی`, `لیست فروشگاه‌ها`, `ثبت نام فروشگاه`, `پنل فروشگاه‌ها`.
- Category row (no mega-menu, simple links): `موبایل و کالای دیجیتال`, `لپ‌تاپ، کامپیوتر، اداری`, `هایپر مارکت`, `لوازم خانگی`, `مد و پوشاک`, `زیبایی و بهداشت`, `صوتی و تصویری`, `خودرو`, `سلامت و پزشکی`, `فرهنگی هنری`, `ورزش`, `اسباب بازی`, `کودک و نوزاد`, `تجهیزات ساختمان`, `ابزارآلات`, `سفر و کمپینگ`, `حیوانات`, `صنعتی`, `ارز و طلا`, `لوازم فروشگاهی`, `سایر دسته‌ها`.

## Home
- Centered hero: big logo `ترب` + giant search input (like Google). No hero slider, no discount rails.
- Below: category tiles + `پیشنهاد ویژه` + app install banner.
- Minimal color: white bg, red accent `#d32f2f` for price/CTA, gray text.

## Search / PLP
- Search suggest: product names + images + price-from `از ۱۲٬۰۰۰٬۰۰۰ تومان`.
- Results: product cards with `از {min_price}` + `ارزان‌ترین فروشنده` + shop count `۱۲ فروشنده`.
- Filters: `فقط موجود`, `فروشگاه‌های معتبر`, city, price range.

## PDP (price list page — core pattern)
```
[gallery + title + specs summary]
[sort: ارزان‌ترین]
[row 1: shop name | rating | location | shipping | price تومان | خرید → outbound]
[row 2: ...]
[price history chart: نمودار قیمت]
[مشخصات فنی + نظرات]
```
- Each row: shop score stars, `عملکرد`, `ارسال`, return policy. CTA button `خرید از {shop}` opens shop site (track click).
- Price history: line chart, crucial for volatile IR market — AI must include `نمودار تغییر قیمت (۳۰ روز)`.

## Trust / Safety
- `راهنمای خرید امن` page, `پیگیری سفارش / شکایت` flow `/feedback/complaints/1/`, verified shop badge.
- No payment handling. Warn: `ترب واسط پرداخت نیست — پرداخت در فروشگاه انجام می‌شود`.

## AI prompt snippet
> Build RTL price-comparison page like Torob: centered search "مقایسه قیمت میلیون‌ها محصول", category links, results with "از {price} تومان", PDP as shop price-list sorted ارزان‌ترین with نمودار قیمت, outbound خرید buttons, no cart. Vazirmatn, fa-IR digits.
