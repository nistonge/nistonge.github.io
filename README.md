# Niyah St. Onge — personal site

A single-page portfolio site. Plain HTML and CSS, no build step, no frameworks.
Everything lives in `index.html` and the `assets/` folder.

```
index.html          the whole site
assets/             project images (optimized JPGs)
README.md           this file
```

---

## Putting it on GitHub Pages

You only have to do this once. After that, editing the site means editing
`index.html` and pushing.

### 1. Make the repository

On github.com, click **New repository**.

Name it exactly:

```
YOURUSERNAME.github.io
```

Replace `YOURUSERNAME` with your GitHub username, in lowercase. The name has to
match your username exactly or Pages will not pick it up as a user site.

Set it to **Public**. Do not add a README, a .gitignore or a license, since this
folder already has what it needs.

### 2. Upload the files

The easy way, no command line:

1. On the empty repository page, click **uploading an existing file**.
2. Drag in `index.html`, `README.md`, and the whole `assets` folder.
3. Scroll down and click **Commit changes**.

The command line way, if you prefer it. From inside this folder:

```bash
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/YOURUSERNAME/YOURUSERNAME.github.io.git
git push -u origin main
```

### 3. Turn on Pages

In the repository, go to **Settings → Pages**. Under "Build and deployment",
set **Source** to `Deploy from a branch`, **Branch** to `main`, folder `/ (root)`,
and click **Save**.

Wait two or three minutes. Your site will be live at:

```
https://YOURUSERNAME.github.io
```

If you see a 404 at first, give it another few minutes. The first build is the
slow one.

---

## Editing it later

Everything is in `index.html`. The parts you are most likely to want to change:

| What | Where to look |
|---|---|
| Your headline and intro | inside `<header class="hero">` near the top |
| A project's text | inside the `<section>` with that project's `id` |
| Project order | move a whole `<section>` block up or down |
| What the nav links to | the `<nav>` block |
| Colors and fonts | the `:root` block in `<style>` |
| Contact details | the `<footer>` at the bottom |

Each project is one `<section>` with a comment above it saying which one it is,
so they are easy to find.

To remove a project entirely, delete its whole `<section>` block and its link in
the nav. Nothing else will break.

---

## Adding your resume

There is deliberately no resume link on the site yet. Your resume PDF has your
phone number on it, and a public site means anyone can download it.

If you want one up there anyway:

1. Make a copy of your resume with the phone number removed, leaving just your
   email and LinkedIn.
2. Save it as `assets/resume.pdf`.
3. In `index.html`, find the `<div class="links">` block in the hero and add:

```html
<a href="assets/resume.pdf">Resume</a>
```

---

## A custom domain, later

If you ever buy a domain, Pages supports it. Settings → Pages → Custom domain,
then add the DNS records GitHub shows you. Nothing in these files has to change.

---

## Images and permissions

The City Structural drawing is published with supervisor permission. The project
location and the engineer of record's seal and signature are blacked out in the
image file itself, not hidden with CSS, so they cannot be recovered from the page.
No detail sheets are included.

The research figures are from the Gu Research Group.
