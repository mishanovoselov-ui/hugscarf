# HugScarf landing (Astro)

Minimal fast landing page for `hugscarf.co` using Astro.

## 1) Install

```bash
npm install
```

## 2) Local development

```bash
npm run dev
```

Open: `http://localhost:4321`

## 3) Production build

```bash
npm run build
```

Output: `dist/`

## 4) Deploy to Cloudflare Pages

- Build command: `npm run build`
- Build output directory: `dist`
- Framework preset: `Astro`
- One-command deploy:

```bash
CLOUDFLARE_API_TOKEN=your_token CF_PAGES_PROJECT=your_project npm run deploy
```

Or pass project name as an argument:

```bash
CLOUDFLARE_API_TOKEN=your_token npm run deploy -- your_project
```

If you prefer interactive auth in local terminal:

```bash
npx wrangler login
CF_PAGES_PROJECT=your_project npm run deploy
```

## 5) Quick customization

- Main page: `src/pages/index.astro`
- Global styles: `src/styles/global.css`
- Meta and title: `src/layouts/BaseLayout.astro`

## 6) Lead collection setup (Mailchimp)

The site is connected by default to the existing **HugScarf Waitlist** embedded form, verified in Mailchimp on 2026-09-11. No environment configuration is needed for this form.

- Editor: https://us12.admin.mailchimp.com/audience/forms/embedded-form/editor?a_id=1080712&f_id=577454
- Audience: `a81d93b33e`; embedded form: `007d0de9f0`.
- The form posts the required `EMAIL` field, existing tag `10403120`, and the original bot-trap field. Mailchimp handles confirmations and errors on its hosted response page.
- Only Email Address is required in the existing embed. The form's other audience fields are disabled.

To use a different form, set `PUBLIC_MAILCHIMP_FORM_ACTION` to its complete HTTPS action URL (decode `&amp;` to `&`) and `PUBLIC_MAILCHIMP_TAGS` to its tag value, then rebuild. The original tag is not used automatically for an overridden form. An explicitly empty or invalid action disables signups safely. These are public embed identifiers, not API credentials.

Sending project update campaigns is a separate action in Mailchimp. No campaign or test subscription was sent while connecting the form. Published to https://www.hugscarf.co/ on 2026-09-11. Deployment: https://e89210bb.hugscurf.pages.dev. The formerly delayed popup is replaced by the permanent signup section. Existing production metadata, analytics, favicon and social preview image were preserved.

## 7) HS videos used in splash

- `public/hs-1.mp4`
- `public/hs-2.mp4`


## 8) SEO and AI-search update — 2026-09-11

Published changes: product-concept introduction, FAQ and partner contact; truthful Organization/WebSite/WebPage structured data instead of unsupported Product/Offer; per-page canonical and social metadata; noindex for design-system and 404; robots.txt preserving training exclusions; sitemap.xml; 404.html; sitemap-index.xml redirect to sitemap.xml.

Production remains https://hugscarf.co/. hugscurf.me is not configured. Mailchimp integration and existing analytics are preserved. The www-to-apex redirect needs an account-level Cloudflare rule (domain sources are unsupported in Pages _redirects). Cloudflare account-level Claude-SearchBot filtering is separate from this static deployment and requires log review. Search Console submission and real Core Web Vitals measurements remain follow-up work.

Source files saved to Drive and a complete release ZIP; direct publication does not push GitHub.
