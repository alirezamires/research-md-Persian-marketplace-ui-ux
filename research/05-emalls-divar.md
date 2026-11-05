# 05 — Emalls + Divar/Sheypoor (comparison + classifieds)

## A. Emalls (`emalls.ir`) — comparison mall
> Fetch timed out 2026-11-05 (JS-heavy), pattern from secondary research + seller docs.

- Type: `موتور جست‌وجوی کالا` / `پاساژ مجازی` — same job as Torob, older UI, denser.
- Flow: search → compare specs → outbound to shop via XML feed. No cart. Revenue = referral clicks.
- Seller requirement: live site + XML price feed (`اتصال خودکار به پنل فروشگاه و بروزرسانی قیمت و موجودی`).
- AI clone: same as Torob (03) but denser spec table, `نمایش رقابتی در کنار برندهای دیگر`, emphasis on `مشخصات فنی` comparison matrix.
- Differentiator to note in UI: Emalls shows shop logos in grid; Torob shows list. Provide both views.

## B. Divar (`divar.ir`) / Sheypoor — classifieds (ad-first)
> Not fetched live (known pattern, high traffic #2 after Digikala).

- No PDP prices fixed, no cart, no checkout. Core = `ثبت آگهی رایگان` + search + chat.
- Home: search + city picker (`تهران`, `مشهد`...) + category icons (خودرو، موبایل، خانه، خدمات، استخدام) + ad grid with `قیمت توافقی / مقطوع` + `فوری` badge + image + district (`سعادت‌آباد`).
- Ad page: photos swipe, `تماس`, `چت`, `نشان کردن`, safety tips `هشدارهای خرید امن`, report button, seller `آگهی‌های این فروشنده`.
- Trust: phone verification, `نشان تأیید هویت`, meeting in public, no online payment.
- App-first: bottom tab bar (آگهی‌ها، جست‌جو، +ثبت، چت‌ها، حساب من).

## When to use which
- Fixed-price new goods + fulfillment → Digikala (02).
- Price hunt across shops → Torob/Emalls (03 + this).
- Handmade/small sellers + chat → Basalam (04).
- Used/local/services/jobs → Divar/Sheypoor (this file).

## AI prompt snippet (classifieds)
> Build RTL classifieds like Divar: city picker + search, category icons, ad grid with توافقی/فوری badges, ad page with تماس/چت CTAs, no cart, bottom mobile tabs. Vazirmatn, fa-IR.
