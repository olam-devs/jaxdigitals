# JAXDIGITALS website

A one-page website for JAXDIGITALS, plus a privacy policy page. It exists so that
Meta (Facebook / WhatsApp) can check the business during **business verification**
and the **WhatsApp display name** review, and so the WhatsApp app has the
**privacy policy URL** it needs before it can go Live.

- `index.html`: services, how it works, about, contact
- `privacy.html`: privacy policy, with a "Delete my data" section (`#data-deletion`)
- `assets/`: style sheet, logo, icons, fonts (Inter and Cormorant Garamond, SIL
  Open Font License) and `og-image.png`, the picture WhatsApp shows when the link is shared

Plain HTML and CSS: no build step, no tracking, no cookies.

## Before publishing: fill in the business details

Every blank is highlighted in yellow on the page and marked in the code. Find them with:

```bash
grep -n "todo\|TODO_" index.html privacy.html
```

| Blank | Where |
|---|---|
| Registered business name (exactly as on the BRELA certificate) | About section, privacy policy |
| BRELA registration number | About section |
| WhatsApp number (`TODO_WHATSAPP_NUMBER` in the links: digits only, e.g. `2557XXXXXXXX`) | Hero button, contact, privacy |
| Phone number (`TODO_PHONE_NUMBER`: `+2557XXXXXXXX`) | Contact, privacy |
| Email (`TODO_EMAIL`) | Contact, privacy |
| Physical address and opening hours | Contact, privacy |
| How long guest data is kept (now 90 days after the event) | Privacy policy, "How long we keep it" |

The name, address and phone must match the business documents Meta checks.

## Publish on GitHub Pages

1. Push this folder to `https://github.com/olam-devs/jaxdigitals` (branch `main`).
2. On GitHub, open the repo → **Settings → Pages**. Under "Build and deployment",
   choose **Deploy from a branch**, branch **main**, folder **/ (root)**, and **Save**.
3. After a minute or two the site is live at **https://olam-devs.github.io/jaxdigitals/**
   and the privacy policy at **https://olam-devs.github.io/jaxdigitals/privacy.html**.

## Use it with Meta

- Business portfolio → **Business info → Website**: the site address.
- Developer app → **App settings → Basic → Privacy policy URL**: the `privacy.html` address.
- If Meta asks for a **data deletion URL**: `privacy.html#data-deletion`.

## Own domain (recommended)

A domain such as `jaxdigitals.co.tz` or `jaxdigitals.com` looks more trustworthy
to Meta and lets you have an email like `info@jaxdigitals.co.tz`, which Meta can
use to verify the business. To use one: buy the domain, add a file named `CNAME`
containing the domain, set the DNS records GitHub's Pages docs list for a custom
domain, and then replace `https://olam-devs.github.io/jaxdigitals/` in the
`canonical` and `og:` tags of both pages with the new address.
