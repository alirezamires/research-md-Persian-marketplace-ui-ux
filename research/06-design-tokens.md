# 06 — Design Tokens (copy-paste for AI)

> Drop into `globals.css` / Tailwind config. RTL-safe (logical props only).

## Colors
```css
:root{
  --bg:#ffffff; --surface:#f1f2f4; --border:#e0e0e6; --text:#0c0c0c; --muted:#62666d;
  --primary:#ef4056; /* Digikala red / discount / CTA */
  --primary-dark:#c81e32;
  --success:#34c759; --fresh:#2e7d32; /* supermarket */
  --gold:#f9bc00; /* طلا و نقره دیجیتال */
  --star:#f9a825;
}
```
- Tailwind: `primary:#ef4056`, `surface:#f1f2f4`, `muted:#62666d`.
- Discount badge: `bg-[#ef4056] text-white text-xs rounded-md px-1.5 py-0.5`.
- Old price: `text-[#62666d] line-through text-xs`. New: `font-bold text-base`.

## Typography
```css
body{font-family:"Vazirmatn","IRANSansX","Digikala","Tahoma",sans-serif; line-height:1.9;}
h1{font-size:22px;font-weight:800} h2{font-size:18px;font-weight:700}
.product-title{font-size:14px; display:-webkit-box; -webkit-line-clamp:2; -webkit-box-orient:vertical; overflow:hidden;}
.price{font-size:16px;font-weight:800} .price small{font-size:12px;font-weight:400}
```
- Digits: always `fa-IR`. Helper JS: `const fa = n => Number(n).toLocaleString('fa-IR')`.

## Spacing / Radius / Shadow
- Container: `max-w-[1440px] mx-auto px-4`. Section gap `my-6`. Card gap `gap-3`.
- Radius: cards `12px`, buttons `8px`, pills `999px`, search `12px`.
- Shadow card: `0 1px 4px rgba(0,0,0,.08)`. Header sticky `position:sticky; top:0; z-index:50; background:#fff; border-block-end:1px solid var(--border)`.

## Components (Tailwind snippets)
```html
<!-- Search -->
<div class="flex items-center gap-2 bg-[#f1f2f4] rounded-xl ps-3 pe-2 py-2">
  <span>🔍</span>
  <input placeholder="جستجو" class="bg-transparent flex-1 outline-none text-sm" />
</div>
<!-- Product card -->
<a class="bg-white rounded-xl border p-3 flex flex-col gap-2">
  <img class="aspect-square object-contain" loading="lazy" />
  <p class="product-title">...</p>
  <div class="flex items-center gap-2"><span class="bg-[#ef4056] text-white text-xs rounded px-1.5">۹۰٪</span><del class="text-xs text-gray-500">۱٬۰۵۶٬۰۰۰</del></div>
  <div class="font-bold">۱۰۸٬۰۰۰ <small class="font-normal text-xs">تومان</small></div>
</a>
<!-- Countdown -->
<div dir="rtl" class="flex items-center gap-1 font-bold"><span>۰۵</span>:<span>۲۱</span>:<span>۱۰</span></div>
<!-- Trust strip -->
<div class="grid grid-cols-2 md:grid-cols-4 gap-3 text-center text-xs text-gray-600">
  <div>🛡️ پرداخت امن از درگاه بانکی</div><div>↩️ تضمین بازگشت وجه</div><div>💬 ارتباط مستقیم</div><div>🎧 پشتیبانی آنلاین و تلفنی</div>
</div>
```

## RTL guard (stylelint)
- Disallow: `margin-left/right`, `padding-left/right`, `border-left/right`, `text-align:left`, `float:left/right`, `left:/right:` offsets. Allow only `inline-start/end`, `ms-/me-/ps-/pe-/start-/end-`.
