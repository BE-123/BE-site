# Beta Endeavors — Website

A responsive 3-page website for [betaendeavors.com](https://betaendeavors.com) built with pure HTML, CSS, and vanilla JS. No build tools, no dependencies, no frameworks — just drop and deploy.

---

## Files

```
betaendeavors/
├── index.html     ← Home page
├── about.html     ← About / bio page
├── contact.html   ← Contact page with email form
└── README.md
```

---

## How to Add Your Photo

1. Save your headshot as `arun-gupta.jpg` (or `.png`) in the same folder as `about.html`
2. Open `about.html` and find this comment:
   ```html
   <!-- TO ADD YOUR PHOTO: Replace the .photo-placeholder div below with: -->
   ```
3. Replace the entire `<div class="photo-placeholder">...</div>` block with:
   ```html
   <img src="arun-gupta.jpg" alt="Arun Gupta" class="photo-actual" />
   ```

---

## Deploying to GitHub Pages (Free Hosting)

This is the easiest way to get the site live at `betaendeavors.com`.

### Step 1 — Create the GitHub Repo

1. Go to [github.com](https://github.com) and sign in (or create an account)
2. Click **New repository**
3. Name it anything, e.g. `betaendeavors-site`
4. Set it to **Public**
5. Click **Create repository**

### Step 2 — Upload the Files

**Option A — via GitHub web interface (easiest):**
1. In your new repo, click **Add file → Upload files**
2. Drag all 3 HTML files (and your photo if you have it) into the upload box
3. Click **Commit changes**

**Option B — via Git command line:**
```bash
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/betaendeavors-site.git
git push -u origin main
```

### Step 3 — Enable GitHub Pages

1. In your repo, go to **Settings → Pages**
2. Under **Source**, select **Deploy from a branch**
3. Choose branch: `main`, folder: `/ (root)`
4. Click **Save**

GitHub will give you a URL like `https://yourusername.github.io/betaendeavors-site/` — your site is live!

### Step 4 — Connect Your Custom Domain (betaendeavors.com)

1. Still in **Settings → Pages**, scroll to **Custom domain**
2. Type `betaendeavors.com` and click **Save**
3. Go to your domain registrar (GoDaddy, Namecheap, etc.) and add these DNS records:

   **A Records** (point `@` to GitHub's IPs):
   ```
   185.199.108.153
   185.199.109.153
   185.199.110.153
   185.199.111.153
   ```

   **CNAME Record** (for `www`):
   ```
   www → yourusername.github.io
   ```

4. DNS changes can take up to 48 hours to propagate
5. Once propagated, check **Enforce HTTPS** in GitHub Pages settings for a free SSL certificate

---

## Contact Form Note

The contact form uses `mailto:` — when submitted, it opens the visitor's email client pre-filled with their message, addressed to `hello@betaendeavors.com`. This works without any server or backend.

If you'd prefer a proper server-side form (so it works without the visitor's email app), consider [Formspree](https://formspree.io) — free tier supports 50 submissions/month and requires only a small code change.

---

## Customization Tips

- **Accent color**: Change `--gold: #c9a84c` in each file's `:root` block
- **Bio text**: Edit the paragraphs in `about.html` inside `.bio-body`
- **Services**: Edit the 6 cards in `index.html` inside `.services-grid`
- **Timeline**: Edit entries in `about.html` inside `.timeline`
