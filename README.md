# Sadhana App website (bhakti.glitgrace.in)

Static site for the Sadhana App landing page + legal pages. No build step — plain HTML/CSS/JS, ready for GitHub Pages.

## Files

```
index.html            Home / landing page
privacy-policy.html   Privacy Policy
terms.html            Terms & Conditions
refund-policy.html    Refund Policy
content-policy.html   Content Policy (AI & content standards)
data-deletion.html    Account & data deletion
css/style.css         Shared design system
js/main.js            Mobile nav toggle
CNAME                 Custom domain for GitHub Pages (bhakti.glitgrace.in)
```

## 1. Push to GitHub

Create a **new repo** for this subdomain (e.g. `bhakti-web`), separate from your `glitgrace.in` root repo, so each subdomain can have its own GitHub Pages source:

```bash
git init
git add .
git commit -m "Sadhana App website"
git branch -M main
git remote add origin https://github.com/<your-username>/bhakti-web.git
git push -u origin main
```

## 2. Enable GitHub Pages

Repo → **Settings → Pages** → Source: `Deploy from a branch` → Branch: `main` / `/(root)` → Save.
Under **Custom domain**, enter `bhakti.glitgrace.in` and save (this writes the same value already in the `CNAME` file, so GitHub keeps it on future deploys). Tick **Enforce HTTPS** once it's available (can take a few minutes after DNS verifies).

## 3. Point the subdomain at GitHub Pages

In your DNS provider for `glitgrace.in`, add a **CNAME record**:

| Type  | Host / Name | Value                     |
|-------|-------------|----------------------------|
| CNAME | `bhakti`    | `<your-username>.github.io` |

This makes `bhakti.glitgrace.in` resolve to your repo's Pages site, while `glitgrace.in` itself (and any other subdomains) can keep pointing at their own repos independently.

DNS changes can take anywhere from a few minutes to a few hours to propagate.

## 4. Before going live — update these placeholders

- **Google Play link**: `https://play.google.com/store/apps/details?id=com.yash.bhakti` — this will 404 until the app is published; it will start working automatically the moment the listing goes live, so no code change needed later.
- **Support email**: currently `support@glitgrace.in` — make sure this inbox exists/forwards somewhere you check, since it's the contact address on all legal pages.
- **Effective dates**: each legal page has an "Effective date" — bump these whenever you materially change a policy.
- **Payment partner name** in `terms.html` and `refund-policy.html` if needed.

## Design notes

Temple-at-dusk palette: oxblood maroon, marigold gold, brass accents on warm ivory. Display type is Cormorant Garamond; body is Mukta. Diya flames, mandala, and scalloped dividers are intentional signature elements — keep them if you restyle.
