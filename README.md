# THINK FIRST website - deploy guide

This is a ready-to-run Vite + React + Tailwind project containing the THINK FIRST demo site.
It has already been build-tested and works.

## Fastest path: Vercel (recommended)

1. Create a free account at https://vercel.com (sign in with GitHub is easiest).
2. Create a new **empty** GitHub repository (e.g. `think-first-site`).
3. Upload this whole folder to that repository (drag-and-drop on github.com works,
   or use `git init && git add . && git commit -m "init" && git push` if you're
   comfortable with git).
4. In Vercel: **Add New... > Project**, import that GitHub repo.
5. Vercel auto-detects Vite. Leave all settings default. Click **Deploy**.
6. In ~1 minute you get a live link like `think-first-site.vercel.app`.
7. To rename the free subdomain: Project Settings > Domains > add
   `thinkfirst.vercel.app` (or whatever is available).
8. To use a real domain later (e.g. `thinkfirst.i2i.com`, once you own `i2i.com`):
   Project Settings > Domains > Add Domain > follow the CNAME instructions shown -
   free, takes about 5-10 minutes to propagate.

## Even faster (no GitHub account needed): Netlify Drop

1. Run these two commands here or on your own machine:
   ```
   npm install
   npm run build
   ```
2. Go to https://app.netlify.com/drop
3. Drag the generated `dist` folder onto the page.
4. You get a live link instantly (e.g. `random-name-123.netlify.app`).
   This method is the quickest for a one-off demo, but re-deploying updates
   means dragging the folder again each time - Vercel + GitHub is better if
   you expect more changes from Claude going forward.

## For Claude to update the live site later

Whoever has edit access just needs to:
1. Get the updated `src/App.jsx` file from Claude (same file format as before).
2. Replace `src/App.jsx` in the GitHub repo with the new version.
3. Push - Vercel rebuilds and redeploys automatically within ~1 minute.

No other files in this project need to change for content/design updates -
`src/App.jsx` is the entire site.

## What's inside

- `src/App.jsx` - the whole site (single file, same code as the Claude artifact)
- `src/main.jsx`, `src/index.css` - React + Tailwind entry points (no need to touch)
- `tailwind.config.js`, `postcss.config.js`, `vite.config.js` - build configuration
- `package.json` - dependencies (react, react-dom, lucide-react)

## Local preview (optional)

```
npm install
npm run dev
```
Opens the site locally so you can check it before deploying.
