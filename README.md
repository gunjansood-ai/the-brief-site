# TheBrief — Marketing & Legal Site

Static HTML pages for TheBrief's privacy policy, support page, and a simple landing page. Hosted on GitHub Pages.

## Files

- `index.html` — Landing page (links to Privacy + Support)
- `privacy.html` — Privacy Policy (linked from App Store Connect)
- `support.html` — Support / FAQ page (linked from App Store Connect)
- `style.css` — Shared dark-mode styling that matches the TheBrief app brand

## Deploy to GitHub Pages (5 minutes)

### 1. Create a new public repo

On GitHub: **New repository → name it `the-brief-site` → Public → Create**.

### 2. Push these files

```bash
cd /Users/gunjansood/Documents/Projects/NewsApp/site
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/gunjansood-ai/the-brief-site.git
git push -u origin main
```

### 3. Enable GitHub Pages

In the new repo on GitHub: **Settings → Pages**.

- **Source:** Deploy from a branch
- **Branch:** `main` / `/ (root)`
- **Save**

Wait ~1 minute. GitHub will give you a URL like:

```
https://gunjansood-ai.github.io/the-brief-site/
```

### 4. Plug URLs into App Store Connect

| App Store Connect field | URL to paste |
| --- | --- |
| Privacy Policy URL | `https://gunjansood-ai.github.io/the-brief-site/privacy.html` |
| Support URL | `https://gunjansood-ai.github.io/the-brief-site/support.html` |
| Marketing URL (optional) | `https://gunjansood-ai.github.io/the-brief-site/` |

That's it. You can now click **Save** in App Store Connect.

## Custom Domain (Optional, Later)

When you're ready to swap from `gunjansood-ai.github.io/the-brief-site/` to something cleaner like `thebrief.app`:

1. Buy the domain (Cloudflare Registrar is cheapest and adds free DNS).
2. In your registrar, add these DNS records pointing to GitHub Pages:
   ```
   A     @     185.199.108.153
   A     @     185.199.109.153
   A     @     185.199.110.153
   A     @     185.199.111.153
   CNAME www   gunjansood-ai.github.io
   ```
3. In the repo: **Settings → Pages → Custom domain** → enter `thebrief.app` → enable HTTPS.
4. Update the URLs in App Store Connect.

## To Update Content

Edit the `.html` files directly. Push to `main`. GitHub Pages redeploys in ~30 seconds.

> **Reminder:** The Privacy Policy still has one placeholder — `[FILL IN: hosting/CDN provider]` in the Third-Party Services section. Update that to whatever you're using (e.g. Cloudflare, AWS S3, Vercel) before going public.
