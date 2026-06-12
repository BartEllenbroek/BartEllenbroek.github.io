# NEST website

A small website for the NEST research group (Bart Ellenbroek and Jiun Youn, School of Psychological Sciences,
Te Herenga Waka—Victoria University of Wellington).

The site is three pages that share one stylesheet:

```
nest-website/
├── index.html            ← home (Welcome, News, Research, People preview, Collaborations preview, Publications, Contact)
├── people.html           ← full team page with biographies + alumni
├── collaborations.html   ← full collaborations page with map + directory
├── styles.css            ← all the styling for every page (edit design here once)
└── images/               ← the pictures
    ├── NEST.jpg
    ├── Nest_image_2.jpg
    └── Jiun_Youn.jpg
```

No build step, no frameworks. Edit the `.html` files in any text editor, save, done. Because
all three pages link to `styles.css`, a design change there updates the whole site at once.

---

## How the pages fit together

The home page shows *previews* — a couple of photos under People, and the map under
Collaborations — each with a link through to the full page. So as the group grows, the home
page stays short and the detail lives on `people.html` and `collaborations.html`.

The "Read bio →" links on the home page jump straight to a person's entry on the People page
(using anchors like `people.html#bart-ellenbroek`).

---

## Editing the content

Each file is split into clearly commented sections — search for the big banner comments
like `<!-- ===== NEWS ===== -->` or `<!-- ===== DIRECTORY ===== -->`.

Common edits:

- **Add a news item** — `index.html`, NEWS section: copy one `<li class="news-item"> … </li>`
  block to the top of the list and change the date and text. Newest first.
- **Add a group member** — two small steps:
  1. `people.html` — copy the commented TEMPLATE block (just below Jiun's entry), give it a
     unique `id`, and fill in name, role and bio. Drop a square photo in `images/` and point
     the `<img src="images/…">` at it (or use the placeholder portrait with initials).
  2. `index.html` (optional) — if you want them shown on the home page too, copy one
     `<a class="person-card"> … </a>` block in the People section and point its `href` at the
     new person's anchor, e.g. `people.html#firstname-lastname`.
- **Add an alumnus** — `people.html`, add an `<li>` under the Alumni list.
- **Add a collaborator** — `collaborations.html`, DIRECTORY section: copy an `<li>` into the
  right regional group (`<strong>` for the name/lab, `<span>` for institution and place). Then
  nudge a coloured dot on the map `<svg>` to roughly the right spot — the viewBox is 360 wide
  × 180 tall, x runs west→east, y runs north→south.
- **Research blurbs** — `index.html`, edit the text inside each `<article class="specimen">`.

### Things worth replacing (placeholders)

- **Jiun Youn's biography** — `people.html` has a placeholder paragraph waiting.
- The **contact email** — currently `bart.ellenbroek@vuw.ac.nz` on `index.html`. Confirm/replace.
- The **collaborator and alumni entries** are all placeholders.

---

## Publishing on GitHub Pages (free)

You already have an account: **github.com/BartEllenbroek**. Two options.

### Option A — a clean URL: `bartellenbroek.github.io`  (recommended)

1. On GitHub, create a new **public** repository named exactly:
   **`BartEllenbroek.github.io`**
2. Upload everything in this folder (the three `.html` files, `styles.css`, and the
   `images` folder) to the repo
   — drag-and-drop in the browser via *Add file → Upload files*, then *Commit*.
3. Go to **Settings → Pages**. Under *Build and deployment*, set **Source: Deploy from a
   branch**, branch **`main`**, folder **`/ (root)`**, and Save.
4. Wait a minute, then visit **https://bartellenbroek.github.io**

### Option B — a project site: `bartellenbroek.github.io/nest`

Same steps, but name the repo **`nest`** (or anything you like). The site then lives at
`https://bartellenbroek.github.io/nest`. Use this if you'd rather keep the personal
`.github.io` address free for something else.

### Updating the live site later

Edit `index.html` (locally or directly on GitHub via the pencil icon), commit the change,
and the site rebuilds itself within a minute or two.

### A custom domain (optional)

If the group ever gets its own domain (e.g. `nestlab.nz`), you can point it at the GitHub
Pages site under **Settings → Pages → Custom domain**.

---

## Notes on the design

- Palette and type are drawn from the group's ink illustrations — aged paper, sepia line
  work, and a single fly-agaric red accent — styled like a natural-history field monograph.
- Typefaces (Fraunces, Hanken Grotesk, IBM Plex Mono) load from Google Fonts, so an internet
  connection is needed to see them exactly as designed; sensible fallbacks are in place.
- The site is responsive, keyboard-accessible, and respects reduced-motion settings.
