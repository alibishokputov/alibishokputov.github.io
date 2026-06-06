# Alibi Shokputov — Academic Website

Personal academic website for the 2025–2026 job market.
Deployed via **GitHub Pages** from the repository root.

## Live URL

`https://alibishokputov.github.io/`

(Replace `alibishokputov` with your actual GitHub username if different.)

---

## How to enable GitHub Pages

1. Push this repository to GitHub (name it `alibishokputov.github.io` for a user-root URL, or any other name for a project URL like `alibishokputov.github.io/repo-name`).
2. Go to **Settings → Pages** in the GitHub repository.
3. Under **Source**, select **Deploy from a branch**.
4. Choose **main** (or `master`) branch, **/ (root)** folder. Click **Save**.
5. GitHub will build and publish within ~60 seconds. The URL is shown at the top of the Pages settings screen.

---

## File structure

```
/
├── index.html              # Single-page site (all sections)
├── styles.css              # All styles
├── Alibi-Shokputov-CV.pdf  # CV — downloaded via button and embedded in CV section
└── README.md
```

---

## Editing content

All content lives in `index.html`. Each section has a clearly labelled `<section id="...">` block:

| Section | `id` |
|---|---|
| Hero / About | `top` (inside `<main>`) |
| Research | `research` |
| Publications & Conference Papers | `publications` |
| Teaching | `teaching` |
| Experience | `experience` |
| CV | `cv` |

Edit the HTML directly. No build step is required — GitHub Pages serves the files as-is.

### Update the CV PDF

Replace `Alibi-Shokputov-CV.pdf` with the new file (keep the same filename), then commit and push. The download button and inline viewer will automatically use the new file.

### Add a new publication

Open `index.html`, find the `<ol class="pub-list">` inside the **Publications** section, and prepend a new `<li class="pub-item">` with the citation. Bold your name with `<strong>Shokputov, A.</strong>`.

---

## Local preview

Open `index.html` directly in a browser, or run a local server:

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

The PDF embed requires a server (browsers block inline PDF from `file://` on some systems).

---

## Technical notes

- No framework, no build step, no dependencies beyond two Google Fonts families loaded from CDN.
- Responsive: tested at 375 px (mobile), 768 px (tablet), 1200 px (desktop).
- Accessible: semantic HTML5 landmarks, ARIA labels on interactive elements, sufficient color contrast (accent `#1d4e89` on white passes WCAG AA).
- SEO: `<title>`, `<meta name="description">`, and Open Graph tags are set in `<head>`. Update the `og:url` value in `index.html` once you know the final GitHub Pages URL.
