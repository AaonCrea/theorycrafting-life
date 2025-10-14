# Theorycrafting.life — Starter (Hugo, no external theme)

This is a zero-cost starter site designed to deploy on **Cloudflare Pages** with **no external theme**. It uses a minimal set of Hugo layouts so you can build and publish immediately.

## Quick Start

1) Install tools (desktop):
- Git: https://git-scm.com
- Hugo: https://gohugo.io/getting-started/installing

2) Run locally:
```bash
hugo server
```
Visit http://localhost:1313

3) Create a GitHub repo and push:
```bash
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/YOURNAME/theorycrafting-life.git
git push -u origin main
```

4) Deploy on Cloudflare Pages:
- Cloudflare Dashboard → Pages → Create Project → “Connect to Git”
- Select your repo.
- Build command: `hugo`
- Output directory: `public`
- Framework preset: Hugo
- Deploy.

5) Connect your domain:
- Cloudflare Pages → Your Project → Custom Domains → Add `theorycrafting.life`

## Editing Content

All content is Markdown under `/content`:
- `/workshop` — leadership portfolio & promotion assets
- `/forge` — systems & optimization
- `/journal` — reflections
- `/about` — who you are

Create a new post:
```bash
hugo new journal/your-post-title.md
```

## Styling

Basic styles live in `static/css/styles.css`. Adjust colors and spacing as you like.

## Notes

- This starter avoids external themes to keep things simple and deployable anywhere.
- You can always add a theme later (update `config.toml` and layouts).
- Cloudflare Pages will rebuild the site every time you push to GitHub.