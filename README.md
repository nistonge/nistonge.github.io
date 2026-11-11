# Niyah St. Onge — personal site

Plain HTML and CSS, no build step, no frameworks. Live at **https://nistonge.github.io**

```
index.html        home: intro, experience cards, about, contact
retrofit.html     City Structural seismic retrofit
research.html     Gu Research Group: coral hydrodynamics and fabrication
campanile.html    Campanile Commons
disc.html         El Cerrito BART redevelopment
style.css         all styling and the colour palette, shared by every page
assets/           images and the resume PDF
```

---

## Updating the live site

1. Go to `github.com/nistonge/nistonge.github.io`
2. **Add file → Upload files**, drag in whatever you changed
3. **Commit changes**

**You do not delete the old file first.** Uploading a file with the same name
and the same path replaces it and keeps the history. Only delete when you want
a file gone for good, or when you are renaming one.

One catch: the filename has to match exactly, capitals included. Uploading
`Index.html` next to `index.html` creates a second file instead of replacing
the first.

The site rebuilds a minute or two after you commit.

### One exception, this time only

The two research pages were merged into a single `research.html`. So on this
upload you DO need to delete the two files it replaced, or they will sit on the
site forever with nothing linking to them:

1. In the repo, click `coral.html`
2. Click the **...** menu at the top right of the file view, then **Delete file**
3. Commit
4. Do the same for `flume.html`

That is the only kind of situation where deleting is needed: a file that is
going away, not a file that is being updated.

---

## Images to add

Six image slots. None of them are required for the site to work, so add them
whenever you have them.

All of these are already in `assets/` and in place:

| File | Shows up as |
|---|---|
| `assets/portrait.jpg` | your photo in the circle on the home page |
| `assets/card-retrofit.jpg` | City Structural card |
| `assets/card-research.jpg` | Gu Research Group card |
| `assets/card-campanile.jpg` | Cal Sustainable Solutions card |
| `assets/card-disc.jpg` | DISC card |
| `assets/card-serc.jpg` | ready for the SERC card |

The card images are built as 800 by 600 tiles with the logo centred on its own
background colour, so the row stays even no matter how different the source
logos are. If you swap one, make a tile the same way rather than dropping in a
raw logo, otherwise it will be cropped to fill the box.

If an image file ever goes missing, that slot falls back to a drawn icon rather
than breaking the page.

---

## Changing the colours

All of it is the `:root` block at the top of `style.css`. One place, every page.

```css
--navy:#0C2033;          /* page background */
--navy-raised:#12304B;   /* cards and image frames */
--line:#1E4365;          /* hairline borders */

--white:#F5F2EC;         /* body text and headings */
--white-dim:#B9C6D2;     /* captions and secondary text */

--brown:#C8914F;         /* labels, links, accents */
--brown-bright:#DCA767;  /* hover */
--brown-deep:#8F6230;    /* the main button */
```

The site is a single dark theme now, so there is no second palette to keep in
sync. If you ever want the background darker or warmer, `--navy` is the only
line you need to touch.

---

## Editing the text

Each project is its own file, so to change the City Structural page you only
open `retrofit.html`. Every project page has the same structure:

- `<h1>` the project title
- `<p class="sub">` the line underneath with the org, year and tools
- `<h2>` a small section label
- `<p>` a paragraph
- `<figure>` an image with its caption

The home page card for each one is in `index.html`, inside `<div class="cards">`.
Each card holds the company name, your position, the project title and a one
line description. If you change a project title, change it in both places.

### Removing a project

Delete its `.html` file, delete its `<a class="card">` block in `index.html`,
and fix the `Previous` / `Next` links at the bottom of the two pages that
pointed at it.

### Adding a project

Copy an existing project file, rename it, replace the content, then copy one of
the `<a class="card">` blocks in `index.html` and point it at the new file.

---

## The resume

`assets/NiyahStOnge_Resume.pdf` is linked from the nav, the hero and the footer.

It deliberately has **no phone number on it**, because anyone on the internet can
download it. It carries your email, LinkedIn and this site's address instead. If
you replace it, keep the same filename and the three links keep working.

---

## Images and permissions

The City Structural drawing is published with supervisor permission. The project
location and the engineer of record's seal and signature are blacked out in the
image file itself, not hidden with CSS, so they cannot be recovered from the page.
No detail sheets are included.

The research figures are from the Gu Research Group.

---

## A custom domain, later

If you ever buy a domain: repository **Settings → Pages → Custom domain**, then
add the DNS records GitHub shows you. Nothing in these files has to change.
