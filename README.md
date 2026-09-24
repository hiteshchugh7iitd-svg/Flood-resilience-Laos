# School Flood Resilience Evidence Platform — Lao PDR

Static site. No build step, no server-side code, no database. Upload the contents
of this folder to any static host and open `index.html`.

## Contents

    index.html      the platform (all twelve tabs)
    school-map.html the national GIS map, embedded by the Hazard Map tab
    study-area-map.html  the study-area map (Namtha and Nale), embedded in Field Evidence
    support.js      the rendering runtime index.html loads
    favicon.svg     site icon
    robots.txt      crawler policy (indexing allowed)
    data/
      SOP-Flood-Response-MOES.pdf   47-page draft SOP, linked from the Draft SOP tab
      site-data.json                district, school and hazard data
      survey.json                   the three questionnaires, items and anonymised answers
    _ds/industry-.../
      styles.css, _ds_bundle.js     the design system both pages link

Total about 2.5 MB.

## Publishing

Any of these work as-is, because every path in the site is relative:

- **GitHub Pages** — commit this folder to a repository, then Settings → Pages →
  deploy from branch. If you commit it as a subfolder, set the Pages source to
  that folder. One catch: GitHub Pages runs Jekyll, which ignores files and
  folders whose names begin with an underscore, so `_ds/` would be dropped.
  Add an empty file named `.nojekyll` at the repository root to switch Jekyll
  off. (It is already included here.)
- **Netlify / Cloudflare Pages / Vercel** — drag the folder onto the dashboard.
  Build command: none. Publish directory: this folder.
- **University or institutional web space** — copy the folder in over SFTP.
  Keep the internal folder structure exactly as it is.

Open it over `http://` or `https://`, not `file://`. The map is embedded in a
frame and the PDF is linked, and browsers block both from a local file path.

## Requirements

Modern browser. Two things load from the network and degrade gracefully without
it: the Noto Sans Lao webfont (Lao text falls back to a system font) and the
map's OpenStreetMap basemap tiles (the districts, rivers, boundaries, fieldwork
sites and all interaction are drawn from data carried inside the page, so the map
still works — it simply has no photographic backdrop).

## Data currency

Administrative and school data current to 28 August 2026. Field responses
collected 10–11 September 2026, Luang Namtha and Nalae districts. The draft SOP
is a draft for ministerial consideration, not an issued instrument.

The SOP PDF in this folder is a compressed copy: the original 13.9 MB vector file
was re-rasterised at about 200 dpi to 1.3 MB so the whole site fits common
hosting limits. The pages and their text are identical; colour is not retained.
Keep the original for formal submission.
