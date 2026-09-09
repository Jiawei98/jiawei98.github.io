# Personal website — Jiawei Huang

## Files

| File | Purpose |
|---|---|
| `index.html` | The whole site. All styling is inside this one file. |
| `CV_Jiawei_Huang.pdf` | Linked from the "Curriculum vitae" button. |
| `profile.jpg` | Your headshot, cropped to the frame the page uses. |

To swap the photo later, replace `profile.jpg` with another file of the same
name. Crop it to roughly 4:5 (portrait), around 640 × 800 px, and keep it under
about 200 KB so the page stays fast. If the file is ever missing the page still
works — it shows your initials in a tinted block instead.

## Deploying to GitHub Pages

Your CV already points at `jiawei98.github.io`, so these instructions assume you
want the site at that address. It is free and needs no build step.

### The simple way, no command line

1. Go to github.com and sign in.
2. Create a new repository named exactly `jiawei98.github.io`. The name has to
   match your username — that is what makes GitHub serve it as a website.
   Set it to Public.
3. On the empty repository page, click **uploading an existing file**.
4. Drag in `index.html`, `CV_Jiawei_Huang.pdf`, and `profile.jpg`.
5. Click **Commit changes**.
6. Wait one or two minutes, then open `https://jiawei98.github.io`.

If the repository already exists, open it, click **Add file → Upload files**,
and drop the same three files in. GitHub will ask you to confirm replacing
`index.html` — that is fine.

### The command line way

```bash
cd path/to/this/folder
git init
git add .
git commit -m "Personal website"
git branch -M main
git remote add origin https://github.com/jiawei98/jiawei98.github.io.git
git push -u origin main
```

To update later: edit the file, then

```bash
git add .
git commit -m "Update publications"
git push
```

### If the page does not appear

Open the repository's **Settings → Pages**. Source should be
"Deploy from a branch", branch `main`, folder `/ (root)`. Save. Deployment takes
a minute or two, and the page can be cached — try a hard refresh
(Cmd+Shift+R or Ctrl+Shift+R).

## Using your own domain

If you buy a domain (for example `jiaweihuang.com`), add a file named `CNAME`
to the repository containing just the domain name, then point the domain's DNS
A records at GitHub's IP addresses listed in the GitHub Pages documentation.
Not necessary — `jiawei98.github.io` is a perfectly normal academic web address.

## Editing the content

Everything is plain HTML. To add a publication, copy an existing block and
change the text:

```html
<li class="entry">
  <div class="entry-marker">2027</div>
  <div class="entry-body">
    <p class="authors"><b>Jiawei Huang</b>, Coauthor Name</p>
    <p class="entry-title">Title of the paper</p>
    <p class="entry-meta"><em>Journal Name</em>, 1(1), 1–20. <a href="https://...">Article</a></p>
  </div>
</li>
```

When a paper moves from under review to published, move its block into the
Published list and change the marker from "Under review" to the year.

Update the date in the footer at the bottom of `index.html` when you make
changes, and remember to replace `CV_Jiawei_Huang.pdf` whenever you revise
the CV itself.
