# Financiaro Retirement — Annuity quiz funnel

Static, dependency-free lead funnel for US annuity leads. Three HTML files, no build step.

| File | Role |
|---|---|
| `index.html` | 5-question quiz → email opt-in → phone opt-in (TCPA) |
| `typ.html` | Thank-you page for **qualified** leads (55+ **and** $250K+) |
| `typ-nq.html` | Thank-you page for **non-qualified** leads (under 55 and/or under $250K) |

## Configure

In `index.html`, top of the `<script>`:

```js
var WEBHOOK_URL = "";   // Zapier / Make / CRM endpoint — receives the lead as JSON
var TYP_URL    = "typ.html";
var TYP_NQ_URL = "typ-nq.html";
```

The lead payload includes every answer, `fname`, `lname`, `email`, `phone`, `qualified` (true/false) and `stage` (`email` or `phone`), so the webhook fires once at the email step and once at the phone step.

In `typ.html`: `BOOKING_URL` (Calendly or similar).
In `typ-nq.html`: `REVIEW_URL` (secondary offer).

## Deploy

Any static host (GitHub Pages, Netlify, Vercel, Cloudflare Pages). Each file is a standalone page; the only external request is Google Fonts (Poppins). Self-host the font as WOFF2 for best mobile scores.

## Before going live

- Replace the illustrated advisor avatar with a licensed photo.
- Replace the "As featured in" image with your actual press logos.
- Have compliance review the TCPA consent text and the disclaimer.
