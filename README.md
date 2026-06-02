# Engine Finder (static)

A single-file, no-build version of Engine Finder. Everything (UI, engine catalogue, chat and recommendation logic) lives in `public/index.html` and runs entirely in the browser — no server, no API key, no sign-in.

## Files

```
public/
  index.html      ← the whole app
vercel.json        ← tells Vercel to serve the public/ folder as a static site
README.md
```

## Deploy on Vercel from GitHub

1. Create a new GitHub repo and upload these files (keep the `public/` folder and `vercel.json` at the repo root).
2. Go to **vercel.com → Add New → Project** and import the repo.
3. Framework Preset: **Other** (no build step needed). Leave Build Command empty.
4. Click **Deploy**. Your site goes live at `your-project.vercel.app`.

`vercel.json` already points Vercel at the `public/` folder, so there is nothing else to configure.

## Test it locally

Just open `public/index.html` in any browser. Or serve the folder:

```bash
cd public && python3 -m http.server 8000   # then visit http://localhost:8000
```

## Edit the engines

Open `public/index.html` and find the `ENGINES` array near the top of the `<script>` block. Each entry has a description, strengths, license, pricing, context window, link and per-task scores (0–100). Change those and the chat, recommendations and cards all update.

Data reflects the frontier as of June 2026 — verify current pricing and limits on each vendor's site.
