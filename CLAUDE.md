# CLAUDE.md: quinmonson/website

Academic website for J. Quin Monson (Professor of Political Science, Brigham Young University).
Built from the GaryKing.org/mysite prompt and the owner's information form, using the structure of the
Matthew Fails site the owner chose as a design model. Read `WEBSITE_PRINCIPLES.md` and `UPDATING.md` before changing anything.

## Workflow
1. `git pull` first; the owner may edit on github.com.
2. Make the change in `hugo-site/`.
3. Build and preview locally, check the affected pages, and show the owner.
4. Commit and push only after the owner approves.

## Local build and preview
Hugo extended >= 0.148.2, Go, and Node 20+.
```bash
cd hugo-site
export PATH=$PWD/node_modules/.bin:$PATH
npm install
hugo --gc --minify -d /tmp/site/website && npx pagefind --site /tmp/site/website
cd /tmp/site && python3 -m http.server 8765   # http://localhost:8765/website/
```

## Owner decisions
- Writing style: avoid dashes in site copy unless necessary.
- Footer credit `params.mysite.credit: false`; invisible marker `discovery: true` (from the form).
- The form asked to share name, institution, and email with the mysite team AFTER the site is published. Not yet done.
- Pages: Home (intro + research areas), Bio & C.V., Research, Presentations, Media, Contact. No People, Teaching, Software, or Data pages (nothing provided on the form).
- Citations use "J. Quin Monson" (`params.owner.name`); display name is "Quin Monson".
- Content was parsed from the Oct 7 2026 C.V. Search for `FLAG FOR OWNER` for open questions.
