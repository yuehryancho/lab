# lab

Source of the Cho lab website at <https://yuehryancho.github.io/lab/>: one bilingual page (`index.html`, English and 中文) served by GitHub Pages from `main`. The course pages live in [`teaching`](https://github.com/yuehryancho/teaching) and the root hub in [`yuehryancho.github.io`](https://github.com/yuehryancho/yuehryancho.github.io).

## Files

```
index.html               the whole site: styles, content, and the language toggle
img/                     hero, portraits, research summary, recruiting posters (WebP)
gallery/                 Lab life photos, numbered NN-short-name.webp
og-card.jpg              link preview card (1200 × 630)
favicon-*.png, apple-touch-icon.png
CV_Yueh_Cho.pdf          linked from the page; replace the file, keep the name
Lab_Intro_Yueh_Cho.pdf   lab introduction slides; same rule
```

## Editing the bilingual text

Every visible piece of text carries both languages, and the toggle swaps them in place.

- **Plain text:** `data-en="…"` and `data-zh="…"`. The element's own content repeats the English, so search engines and readers without JavaScript see English.
- **Text with links or italics:** `data-en-html="…"` and `data-zh-html="…"`, with the markup escaped (`<` → `&lt;`, `>` → `&gt;`, `"` → `&quot;`, `&` → `&amp;`). The element's own content holds the unescaped English HTML.
- To escape a snippet, paste it into this one-liner (macOS Terminal):
  `pbpaste | python3 -c 'import html,sys; print(html.escape(sys.stdin.read().strip()))' | pbcopy`
- After editing, open `index.html` in a browser, press 中 / EN, and check that both versions read correctly.

## Releasing a preprint or paper

The lab posts a preprint when it submits and deposits data and code when the paper comes out (stated under Join us → How we work). Work through the list below at each stage.

### At submission: preprint

1. Post to bioRxiv and note the DOI.
2. **Publications:** add an entry at the top of the "Cho lab at NTU (since July 2026)" list (search `CHO LAB AT NTU` in `index.html`). Label it `Preprint` and link the DOI. Once the first paper is listed, remove the "first original research papers … are in preparation" sentence.
3. **News:** copy the `NEWS TEMPLATE` pair to the top of the news list, in both languages.
4. **ORCID:** check that the preprint arrived through the Crossref auto-update. If it did not, add it with the DOI.
5. **CV:** update `CV_Yueh_Cho.pdf` and replace the file under the same name.
6. **Search:** in `yuehryancho.github.io/sitemap.xml`, set `lastmod` for `/lab/` to today's date.
7. **Social:** post on X, Bluesky, LinkedIn, and Threads with one key figure, the DOI link, and the lab link.

### On publication: journal version

1. **Publications:** replace the preprint entry with the journal version, using the format of the existing `.pub` lines: authors with corresponding authors marked `*` and Y. Cho in the `<em>` part, year, title linked to the DOI, journal in italics, volume and pages.
2. **Data and code:** confirm that the accessions are public. These include GEO/SRA for sequencing, PRIDE for proteomics, and Zenodo or GitHub for code. Add the accessions to the paper entry.
3. **Funding:** confirm that the paper acknowledges the grant number listed under Funding and support (for example NSTC 115-2311-B-002-024-MY3).
4. **News, CV, sitemap, and social:** repeat steps 3, 5, 6, and 7 from the preprint stage.
5. **Google Scholar:** about two weeks later, check the profile and merge the preprint and journal versions.
6. **NSTC profile:** add the paper to the publication list in the NSTC researcher profile (學術研發服務網).

### Before pushing

- Open the page locally, toggle both languages, and click the new links.
- Keep images in WebP under about 300 KB, with an `alt` text that says what the image shows.
