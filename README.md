# 🥝 NZ Slang Quiz

A static multiple-choice quiz web app built from the **NZ Youth Slang** dataset.
Pure HTML/CSS/JS — no framework, no build server needed — ready to deploy on
GitHub Pages.

## What it does

- Shows a Kiwi slang term and asks you to pick the correct meaning (or reverse:
  pick the term from a meaning).
- 4 multiple-choice options per question, distractors drawn from the same
  category where possible.
- Score tracking, progress bar, and the real example sentence revealed after
  each answer.
- Filter by category and choose round length (10 / 20 / 50 questions).
- Keyboard shortcuts: `1-4` or `A-D` to answer, `Enter` / `→` for next.

## Project layout

```
docs/                 ← the deployable site (GitHub Pages serves this)
  index.html
  app.js
  data.js             ← generated quiz data (window.SLANG_DATA)
scripts/
  build-data.py       ← regenerates docs/data.js from the CSV
NZ YOUTH SLANG  (Clean) - Sheet1.csv   ← source data
```

## Regenerating the data

If you edit the CSV, rebuild the embedded data file:

```bash
python3 scripts/build-data.py
```

This rewrites `docs/data.js` with one deduplicated entry per term.

## Run locally

```bash
python3 -m http.server 4173 --directory docs
# then open http://localhost:4173
```

## Deploy to GitHub Pages

1. Create a repo and push this project.
2. In the repo, go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to *Deploy from a branch*.
4. Pick branch `main` and folder **`/docs`**, then **Save**.
5. Your quiz goes live at `https://<username>.github.io/<repo>/` within a minute.

No build step runs on GitHub — the site is fully static.
