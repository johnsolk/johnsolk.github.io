# johnsolk.github.io — site redesign

This folder contains the redesigned personal/professional site for Lisa K. Johnson,
meant to replace the current contents of the `johnsolk.github.io` repository
(a GitHub Pages user site).

## What's in here

```
index.html              Homepage (hero, About, Connect)
publications.html       Full publications page (journal articles, book chapter, presentations)
files/
  Johnson_CV_2026.pdf   CV, linked from the "CV" button on the homepage
```

No build step — this is plain HTML/CSS (Google Fonts loaded via CDN link tags,
no JS framework, no bundler). It can be served as-is by GitHub Pages.

## Deploying to johnsolk.github.io

1. Clone the existing repo: `git clone https://github.com/johnsolk/johnsolk.github.io.git`
2. **Remove the old site contents** (this replaces the previous Pandoc-generated site,
   including the old `about.html`, `blog/` index if it's not being kept, and any old
   `files/` contents that aren't still referenced).
   - Keep `blog/` as-is if the Jekyll/blog subfolder should stay — the nav's
     "The Fiddle" link points to `https://johnsolk.github.io/blog/`, so that path
     needs to keep working.
3. Copy `index.html`, `publications.html`, and the `files/` folder from this package
   into the repo root, replacing anything with the same names.
4. Commit and push to the branch GitHub Pages serves from (usually `main` for a
   `<username>.github.io` repo — check Settings → Pages in the GitHub repo if unsure).
5. GitHub Pages will publish automatically after the push; the live site is at
   `https://johnsolk.github.io/`.

## Notes / things to double check after deploying

- **Internal links** between `index.html` and `publications.html` use relative
  paths (`publications.html`, `index.html`), so they'll only resolve correctly
  once both files sit in the same directory (the repo root).
- **The CV link** points to `files/Johnson_CV_2026.pdf` (relative path) — make sure
  the `files/` folder is copied in alongside the HTML files, not nested differently.
- **External links** (GitHub, ORCID, Google Scholar, DOIs, old employer/advisor
  pages) were checked and updated as of this session, but it's worth a periodic
  click-through since academic/institutional URLs tend to drift over time.
- **Fonts**: the pages load Fraunces, Inter, and IBM Plex Mono from Google Fonts
  via `<link>` tags in the `<head>`. If you want to self-host fonts instead of
  depending on the Google Fonts CDN, that would need to be added separately.
