# Portfolio site — Alessia Fant

`index.html` is the full portfolio (self-contained, images embedded). Publish it to GitHub Pages.

## 1. Create the repo on GitHub
Go to github.com → New repository. Name it `portfolio` (or anything). Public. Don't add a README (this folder already has one).

## 2. Push (run in this folder)
Replace `<username>` with your GitHub username.

```bash
cd "/Users/alessiafant/Documents/CV/portfolio-site"
git init
git add index.html README.md
git commit -m "Portfolio site"
git branch -M main
git remote add origin https://github.com/<username>/portfolio.git
git push -u origin main
```

## 3. Turn on GitHub Pages
On GitHub: repo → Settings → Pages → Build and deployment → Source: "Deploy from a branch" → Branch: `main`, folder `/ (root)` → Save.
After ~1 minute the site is live at `https://<username>.github.io/portfolio/`.

## 4. Custom domain (the GoDaddy domain from Mattia)
Once you have the domain (say `work.alessiafant.com`):

- On GitHub: Settings → Pages → Custom domain → type the domain → Save. (GitHub adds a `CNAME` file to the repo.)
- On GoDaddy DNS:
  - **Subdomain** (e.g. `work.` or `www.`): add a **CNAME** record, host = the subdomain, value = `<username>.github.io`.
  - **Apex/root domain** (e.g. `alessiafant.com` with no prefix): add four **A** records pointing to:
    `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
- Back on GitHub Pages, tick **Enforce HTTPS** (after DNS propagates, a few minutes to a few hours).

## Updating later
Replace `index.html`, then:
```bash
git add index.html && git commit -m "Update" && git push
```
