# 01 — RTL Foundation (required for all AI output)

> Copy these rules into every generation prompt. Verified: Digikala serves `dir="rtl" lang="fa"`, body font `Digikala, sans-serif`, bg `#fff`.

## 1. Document shell
```html
<!DOCTYPE html>
<html dir="rtl" lang="fa">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>فروشگاه اینترنتی — مثال</title>
  <!-- Persian font: Vazirmatn (open) or Digikala/IRANSans equivalent -->
  <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/rastikerdar/vazirmatn@v33.003/Vazirmatn-font-face.css">
  <style> body{font-family:"Vazirmatn","IRANSans","Tahoma",sans-serif} </style>
</head>
```

## 2. Direction rules (critical)
- NEVER use `margin-left`, `margin-right`, `padding-left/right`, `float: left`, `text-align: left`, `border-left/right`.
- USE logical properties: `margin-inline-start/end`, `padding-inline`, `inset-inline-start/end`, `text-align: start`, `border-start-start-radius`.
- Tailwind: enable `rtl` — use `ms-`, `me-`, `ps-`, `pe-`, `start-0`, `end-0`, `text-right` default. Example: `class="ms-3 me-auto text-right"`.
- Icons that imply direction (back, next, cart arrow, chevron) MUST be mirrored: `transform: scaleX(-1)` in RTL or use `rtl:rotate-180`.
- Horizontal carousels scroll from right to left. First item at `inline-start`. Countdown `05:21:10` renders with Persian digits `۰۵:۲۱:۱۰`.

## 3. Typography (Farsi)
- Font stack: `"Vazirmatn","Digikala","IRANSansX","IRANSans","Tahoma",sans-serif`. Digikala uses custom `Digikala` face — Vazirmatn is the open substitute.
- Numbers/prices: Persian digits `۰۱۲۳۴۵۶۷۸۹`. Convert in code: `n.toLocaleString('fa-IR')`.
- Prices: thousand separator `٬` (U+066C), no decimals, suffix `تومان`. Example: `۱٬۰۵۶٬۰۰۰ تومان`. Strikethrough old price small gray, new price bold black/red.
- Titles: product titles 2-line clamp, `line-height: 1.9` for Farsi readability. Body 14px, title 14-16px, price 16-18px bold.
- Inputs/placeholders in Farsi: search placeholder `جستجو`, button `ورود | ثبت‌نام`, cart `سبد خرید`, address `انتخاب آدرس`.

## 4. Layout grid
- Container: `max-w-[1440px] mx-auto px-4`. Desktop 4-5 cols product grid, mobile 2 cols.
- Header (RTL right→left): logo (start) | search grows center | actions (end): bell, login, cart.
- Mega-menu trigger: `دسته‌بندی کالاها` + hamburger at start edge. Opens full-width panel with 3 columns: categories → subcats → banners.
- Footer: 4 cols in RTL: About / Support / Buy-Sell / Apps + trust seals (Enamad, Samandehi) at bottom.

## 5. Forms, dates, address
- Phone: `۰۹xx xxx xxxx`, OTP 5-digit inputs auto-advance RTL.
- Address: province → city → postal code `کد پستی ۱۰ رقمی`, address picker modal `انتخاب آدرس` before add-to-cart availability.
- Calendar/Jalali note: display Jalali dates, keep `<time datetime="ISO">` for machines.
- Payment: redirect to Shaparak PSP, show `پرداخت امن از درگاه بانکی`. No card-on-file in MVP.

## 6. AI checklist before shipping
- [ ] `<html dir="rtl" lang="fa">` present?
- [ ] No physical `left/right` in CSS?
- [ ] All numbers via `fa-IR`?
- [ ] Search placeholder `جستجو`, cart `سبد خرید`?
- [ ] Carousel starts from right?
- [ ] Fonts load Vazirmatn with `font-display: swap`?
