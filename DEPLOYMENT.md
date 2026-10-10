# AI Research Navigator — Deployment Guide

This guide explains how to deploy the **AI Research Navigator** frontend to **Vercel** or **GitHub Pages** (free, instant, CDN-backed).

---

## ⚡ Architecture & Deployment Overview

The frontend is completely self-contained and client-resilient:
- **Landing Page**: Located at [`frontend/landing.html`](file:///frontend/landing.html) with hero, interactive terminal sandbox, features, pipeline breakdown, and live benchmark cards.
- **Research Desk App**: Located at [`frontend/index.html`](file:///frontend/index.html) and [`frontend/app.html`](file:///frontend/app.html) featuring:
  - 30 curated foundational AI papers with BibTeX & APA export
  - Client-side citation-grounded synthesis engine (works offline & statically)
  - Refusal threshold verification
  - Dark / Light editorial scholarly themes
- **Config Files Included**:
  - [`vercel.json`](file:///vercel.json) — Ready-to-go Vercel rewrites and routing rules
  - [`.github/workflows/deploy-pages.yml`](file:///.github/workflows/deploy-pages.yml) — Automated GitHub Pages deployment pipeline

---

## 🚀 Option 1: Deploy to Vercel (Recommended — 2 Minutes)

Vercel provides instant global CDN hosting with automatic SSL and zero server management.

### Method A: Via Vercel Web Dashboard (No CLI needed)
1. Push your repository to **GitHub**:
   ```bash
   git add .
   git commit -m "Add landing page and deployment configurations"
   git push origin main
   ```
2. Go to **[vercel.com/new](https://vercel.com/new)** and sign in with GitHub.
3. Select your `AI-Research-Navigator` repository.
4. Keep the default settings (the included [`vercel.json`](file:///vercel.json) automatically maps `/` to the Landing Page and `/app` to the Research Desk).
5. Click **Deploy**.
6. Your site will be live at `https://your-project-name.vercel.app`.

### Method B: Via Vercel CLI
Run the following in the project root:
```bash
npx vercel
```
Follow the quick interactive prompts to publish instantly.

---

## 🐙 Option 2: Deploy to GitHub Pages (100% Free on GitHub)

The automated GitHub Actions workflow is already configured at [`.github/workflows/deploy-pages.yml`](file:///.github/workflows/deploy-pages.yml).

1. Commit and push your changes to GitHub:
   ```bash
   git add .
   git commit -m "Configure GitHub Pages deployment"
   git push origin main
   ```
2. In your GitHub repository, navigate to **Settings** > **Pages** (in the left sidebar).
3. Under **Build and deployment** → **Source**, select **GitHub Actions**.
4. GitHub Actions will trigger automatically under the **Actions** tab.
5. In ~1 minute, your site will be live at:
   ```
   https://<your-username>.github.io/<repository-name>/
   ```
6. The root URL automatically loads the **Landing Page**, and clicking **"Get Started"** opens the **Research Desk**.

---

## 🌐 Option 3: Deploy to Netlify (Drag & Drop)

1. Go to **[app.netlify.com/drop](https://app.netlify.com/drop)**.
2. Drag and drop the `frontend` folder into the upload box.
3. Your site is deployed immediately with a live public URL.

---

## 💻 Local Testing & Verification

To verify both the Landing Page and Research Desk locally:
```bash
python web_server.py
```
- **Landing Page**: [http://127.0.0.1:8000/](http://127.0.0.1:8000/)
- **Research Desk**: [http://127.0.0.1:8000/app](http://127.0.0.1:8000/app)
- Clicking **"Get Started"** or **"Launch App"** transitions directly into the Research Desk.
