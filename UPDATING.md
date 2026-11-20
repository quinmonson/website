# Updating Your Website

Everything on the site is plain text files you can edit right on GitHub.
Open a file on github.com, click the pencil icon, edit, and click **Commit changes**.
The site rebuilds and goes live by itself about two minutes later.
You can watch progress under the repository's **Actions** tab.

All site files live in the `hugo-site/` folder.

## Before you go further: please review these

- **Flags.** Search the repository for `FLAG FOR OWNER` to see every spot where something needs your check.
  Flags are hidden comments and never show on the site.
- **Research areas** on each paper were assigned automatically from the titles. Fix any that look wrong
  by editing the `research_areas:` line in that paper's `index.md`.

## Add a new paper

1. Go to `hugo-site/content/publication/` and click **Add file → Create new file**.
2. Name it `your-short-slug/index.md`, e.g. `oil-and-coups/index.md`.
   The folder name becomes the web address (`…/publication/oil-and-coups/`). **Never rename it later.**
3. Paste and fill in:

```yaml
---
title: "Paper Title"
date: 2026-05-01
authors: ["J. Quin Monson", "Co Author"]
publication_types: ["journal_article"]  # or book, edited_book, book_chapter, report, working_paper
status: "Forthcoming"                    # optional: shown instead of the year
publication: "Journal Name 12 (3): 45–67"
doi: "10.xxxx/xxxxx"
abstract: "Paste the abstract here."
links:
  - name: "Publisher's Version"
    url: "https://doi.org/10.xxxx/xxxxx"
  - name: "Article (PDF)"
    url: "files/my-paper.pdf"            # no leading slash
research_areas: ["public-opinion"]       # see list below
---
```

4. Upload the PDF to `hugo-site/static/files/` with the same filename.
5. Optional: drop a journal cover image named `featured.jpg` into the paper's folder.

The "See Also" links, the Research page, the homepage research areas, and search all update automatically.

## Add a conference presentation

Create `hugo-site/content/talk/<short-slug>/index.md` with `title`, `date`, `authors`,
`publication_types: ["presentation"]`, and `event: "the 2027 annual meeting of the ..."`. Copy any existing talk as a template.

## Add a media link

Edit `hugo-site/content/media/index.md` and add a line under the right heading, following the existing pattern.

**Research area names:** `public-opinion`, `campaigns-elections`, `survey-methods`, `religion-politics`. To rename an area or add a new one, edit
`hugo-site/data/research_areas.json`.
Research areas appear as a filter on the Research page.

## Update your bio or contact page

The short homepage intro is `content/_index.md`; the full bio is `content/bio/index.md`; contact details are `content/contact/index.md`.
Name, title, email, Google Scholar, and C.V. path come from `hugo.yaml` under `params.owner`.
To replace the C.V., upload the new PDF to `static/files/` as `monson-cv.pdf`, overwriting the old file.
The short link `…/cv/` always points there.

## Replace your photo

Your headshot is `hugo-site/assets/media/bio-photo.jpg`. It is used on the homepage.
To swap it, upload a new photo with **exactly that name**, overwriting the old file.
It is displayed as a portrait rectangle (4:5), cropped from the top. Upload a large, high-quality JPEG, at least 1200×1500 pixels, already cropped to 4:5; the site makes the smaller sizes automatically. If you delete the file, a "QM" circle appears instead.

## Change a button label

All labels (e.g. "Download C.V. (PDF)") live in `hugo-site/i18n/en.yaml`.

## Footer credit / hidden marker

In `hugo-site/hugo.yaml`, under `params.mysite`:
`credit: true` shows a small "Created using GaryKing.org/mysite" line in the footer (currently off).
`discovery: false` removes the invisible marker.

## Coming back after a while

- **Small text edits:** edit the file on github.com and commit. The site updates about two minutes later.
- **Bigger changes:** ask Claude to make the change in the quinmonson/website repository.
  Claude reads `CLAUDE.md` in this repository, updates its copy from GitHub, previews the change for you, and publishes when you approve.
- **New computer:** `gh repo clone quinmonson/website`, then ask Claude to set up the local preview. `CLAUDE.md` has the steps.

## Preview locally (optional)

With Hugo extended ≥ 0.148.2 and Node installed, run from `hugo-site/`:
`npm install`, then `hugo server`. Open http://localhost:1313/website/
