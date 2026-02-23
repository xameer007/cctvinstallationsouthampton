# ShieldCCTV Southampton — Website

Professional CCTV installation landing page for Southampton & Hampshire.  
Built as a static HTML site — no framework, no build step, instant deployment.

---

## 🗂️ Project Structure

```
shieldcctv/
├── public/
│   ├── index.html          ← Main landing page (homepage)
│   ├── privacy-policy.html ← Privacy policy (GDPR required)
│   ├── cctv-policy.html    ← ICO-compliant CCTV usage policy
│   ├── 404.html            ← Custom not-found page
│   ├── robots.txt          ← Search engine crawler rules
│   ├── sitemap.xml         ← XML sitemap for SEO
│   ├── favicon.svg         ← SVG favicon (all modern browsers)
│   └── site.webmanifest    ← PWA manifest (mobile homescreen)
├── vercel.json             ← Vercel routing & headers config
├── package.json            ← Project metadata & dev scripts
└── README.md               ← This file
```

---

## 🚀 Deploy to Vercel

### Option A — Vercel CLI (recommended)

**1. Install Vercel CLI**
```bash
npm install -g vercel
```

**2. Login to Vercel**
```bash
vercel login
```

**3. Deploy from the project root**
```bash
cd shieldcctv
vercel
```

Follow the prompts:
- Set up and deploy: `Y`
- Which scope: select your account
- Link to existing project: `N`
- Project name: `shieldcctv-southampton` (or your choice)
- Directory: `./` (press Enter)

**4. Deploy to production**
```bash
vercel --prod
```

---

### Option B — GitHub + Vercel Dashboard (zero-CLI)

1. Push this project to a GitHub repository:
```bash
git init
git add .
git commit -m "Initial commit — ShieldCCTV Southampton"
git remote add origin https://github.com/YOUR_USERNAME/shieldcctv.git
git push -u origin main
```

2. Go to [vercel.com](https://vercel.com) → **Add New Project**
3. Import your GitHub repository
4. Vercel will auto-detect the `vercel.json` config
5. Click **Deploy** — live in ~30 seconds

---

## 🌐 Custom Domain Setup

After deploying, connect your domain in the Vercel dashboard:

1. Go to your project → **Settings** → **Domains**
2. Add `shieldcctv.co.uk` and `www.shieldcctv.co.uk`
3. Update your domain registrar DNS with the records Vercel provides:

| Type  | Name | Value                    |
|-------|------|--------------------------|
| A     | @    | 76.76.21.21              |
| CNAME | www  | cname.vercel-dns.com     |

DNS propagation typically takes 10–60 minutes.

---

## 🔧 Before Going Live — Update These

Replace placeholder values in `public/index.html` and other files:

| Placeholder | Replace With |
|---|---|
| `023 8000 0000` | Your real phone number |
| `07700 000 000` | Your real emergency number |
| `info@shieldcctv.co.uk` | Your real email address |
| `shieldcctv.co.uk` | Your real domain |
| `SO14 7FJ` | Your real postcode |
| `Company No. 09876543` | Your real Companies House number |
| `VAT No. GB 123 456 789` | Your real VAT number |
| `ICO Reg. ZB123456` | Your real ICO registration number |
| `Checkatrade profile URL` | Your real Checkatrade URL |

Also update `public/sitemap.xml` with your real domain, and `public/robots.txt` with the correct sitemap URL.

---

## 📈 SEO Checklist After Launch

- [ ] Submit `sitemap.xml` to Google Search Console
- [ ] Submit `sitemap.xml` to Bing Webmaster Tools
- [ ] Verify ownership via Google Search Console
- [ ] Set up Google Analytics (add GA4 tracking ID to `index.html`)
- [ ] Register/claim Google Business Profile listing for Southampton
- [ ] Verify Checkatrade profile links match the live URL
- [ ] Test Schema.org structured data at: [schema.org/validator](https://validator.schema.org)
- [ ] Test Core Web Vitals at: [pagespeed.web.dev](https://pagespeed.web.dev)
- [ ] Test mobile usability at: [search.google.com/test/mobile-friendly](https://search.google.com/test/mobile-friendly)

---

## 🔒 Security Headers

The following security headers are configured in `vercel.json` and applied automatically on deployment:

- `X-Content-Type-Options: nosniff`
- `X-Frame-Options: DENY`
- `X-XSS-Protection: 1; mode=block`
- `Referrer-Policy: strict-origin-when-cross-origin`
- `Permissions-Policy: camera=(), microphone=(), geolocation=()`

---

## 🛠️ Local Development

To preview the site locally before deploying:

```bash
npm install
npm run dev
```

Then open [http://localhost:3000](http://localhost:3000)

---

## 📄 Pages

| URL | File | Purpose |
|-----|------|---------|
| `/` | `index.html` | Main landing page |
| `/privacy-policy` | `privacy-policy.html` | UK GDPR privacy policy |
| `/cctv-policy` | `cctv-policy.html` | ICO CCTV usage policy |
| `/404` | `404.html` | Custom error page |

---

## 📊 Charts

Charts use [Chart.js 4.4.1](https://www.chartjs.org/) loaded via CDN. All data is sourced from:
- **Southampton City Council** Safe City Strategic Assessment 2024/25
- **ONS** Crime in England and Wales: year ending March 2025
- **data.police.uk** (via CrimeRate.co.uk & Crystal Roof, Nov 2025)
- **UK Home Office** Research Report 44

---

## ⚡ Performance Notes

- No server-side rendering — pure static HTML
- Fonts loaded via Google Fonts with `rel="preconnect"` for speed
- Chart.js loaded from Cloudflare CDN
- Vercel's global edge network serves files from the nearest datacenter
- Target Lighthouse score: 90+ (Performance, SEO, Accessibility)
