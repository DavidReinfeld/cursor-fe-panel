# Field Engineering Team Presentation

A reveal.js slide deck for **Building a World-Class Field Engineering Team**. Single-file, no build step — open `index.html` in a browser or deploy to GitHub Pages.

## Local preview

Open the file directly:

```bash
open index.html
```

Or serve it locally (recommended for hash routing):

```bash
python3 -m http.server 8080
# visit http://localhost:8080
```

## Keyboard navigation

| Key | Action |
|-----|--------|
| `→` / `Space` | Next slide |
| `←` | Previous slide |
| `ESC` | Slide overview |
| `F` | Fullscreen |

## Deploy to GitHub Pages

### Option A — Deploy from the `main` branch (simplest)

1. Push this repo to GitHub.
2. In the repo, go to **Settings → Pages**.
3. Under **Build and deployment → Source**, select **Deploy from a branch**.
4. Choose branch **`main`** and folder **`/ (root)`**, then click **Save**.
5. After a minute or two, the site will be live at:

   ```
   https://<your-username>.github.io/<repo-name>/
   ```

   For this repo that would be:

   ```
   https://davidreinfeld.github.io/cursor-fe-panel/
   ```

### Option B — Deploy with GitHub Actions (optional)

If you prefer a workflow file, create `.github/workflows/pages.yml`:

```yaml
name: Deploy to GitHub Pages

on:
  push:
    branches: [main]

permissions:
  contents: read
  pages: write
  id-token: write

jobs:
  deploy:
    runs-on: ubuntu-latest
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    steps:
      - uses: actions/checkout@v4
      - uses: actions/configure-pages@v5
      - uses: actions/upload-pages-artifact@v3
        with:
          path: .
      - id: deployment
        uses: actions/deploy-pages@v4
```

Then in **Settings → Pages**, set Source to **GitHub Actions**.

## Structure

The deck currently contains section title slides only (no sub-slides yet):

| Slide | Content |
|-------|---------|
| 0 | Title — Building a World-Class Field Engineering Team |
| 1 | Part 1: Recruiting, Assessing & Retaining |
| 2 | Part 2: Building a Culture of Excellence |
| 3 | Part 3: 10 · 20 · 30 Day Impact Plan |
| 4 | Part 4: Metrics & Measuring Impact |
| 5 | Close — Let's Build Something Exceptional |

## Tech stack

- [reveal.js 5.1](https://revealjs.com/) (CDN)
- [Inter](https://fonts.google.com/specimen/Inter) via Google Fonts
- Cursor brand colors (`#0A0A0A` background, `#6B46F6` accent)
