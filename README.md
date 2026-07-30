# Google Sitemap Test Site

A minimal static site to verify **Google Search Console sitemap indexing** end-to-end.

**Live URL:** https://agenticsamir.github.io/google-sitemap-test/

---

## Files

| File | Purpose |
|---|---|
| `index.html` | Main page with full SEO meta tags |
| `sitemap.xml` | Standard XML sitemap |
| `robots.txt` | Allows all bots, references sitemap |

---

## Step-by-Step: GitHub Pages + GSC Setup

### Step 1 — Enable GitHub Pages

1. Go to **https://github.com/agenticsamir/google-sitemap-test**
2. Click **Settings** → **Pages** (left sidebar)
3. Under **Source**, select **Deploy from a branch**
4. Select branch: `main`, folder: `/ (root)`
5. Click **Save**
6. Wait ~60 seconds, then visit: `https://agenticsamir.github.io/google-sitemap-test/`

> ✅ You should see the live test page before proceeding.

---

### Step 2 — Add Site to Google Search Console

1. Go to **https://search.google.com/search-console/**
2. Click **+ Add Property** (top-left dropdown)
3. Choose **URL prefix** (not Domain)
4. Enter: `https://agenticsamir.github.io/google-sitemap-test/`
5. Click **Continue**

---

### Step 3 — Verify Ownership (HTML File Method)

1. GSC will show you a verification page — choose **HTML file** tab
2. Download the verification file (e.g., `google1234567890abcdef.html`)
3. Place it in this repo's root directory (same level as `index.html`)
4. Commit and push:
   ```bash
   git add google*.html
   git commit -m "chore: add GSC verification file"
   git push
   ```
5. Wait ~60 seconds for GitHub Pages to deploy
6. Back in GSC, click **Verify**

> ✅ GSC should confirm ownership.

---

### Step 4 — Submit the Sitemap

1. In GSC left sidebar → **Sitemaps**
2. In the input box, type: `sitemap.xml`
3. Click **Submit**

> ✅ Status should change from "Pending" to "Success" within a few minutes to hours.

---

### Step 5 — Monitor Indexing

- **Sitemaps report**: Check that the URL count shows `1`
- **URL Inspection tool**: Enter `https://agenticsamir.github.io/google-sitemap-test/` to check indexing status
- **Google index**: After a few days, search `site:agenticsamir.github.io/google-sitemap-test` to confirm it's indexed

---

## Common Issues

| Error | Cause | Fix |
|---|---|---|
| Sitemap could not be read | XML syntax error or wrong Content-Type | Validate at https://www.xml-sitemaps.com/validate-xml-sitemap.html |
| Couldn't fetch | Site not publicly accessible | Confirm GitHub Pages is live |
| URLs not in sitemap | URL in sitemap doesn't match canonical | Ensure `<loc>` URL exactly matches the live URL including trailing slash |
