# alvinholbrook.com

Personal site — About, Writing, Podcast Appearances, Photography, Contact.
Built with Jekyll, hosted free on GitHub Pages.

## Adding content

- **A new story:** copy `_stories/example-story.md`, rename it, fill in the
  front matter (title, publication, date, link). It shows up on `/writing/`
  automatically. Delete the example file once you have real ones.
- **A new podcast appearance:** same idea, in `_appearances/`.
- **Photography:** drop images into `assets/images/photography/` and add an
  `<img>` line in `photography/index.md`.
- **Bio / résumé:** edit `index.md` directly. Drop your résumé PDF into
  `assets/` as `resume.pdf`.
- **Contact email / footer links:** edit `_config.yml`.

## Running locally (optional)

You don't need this to edit content — you can edit files directly on
GitHub.com and the live site rebuilds itself. This is only if you want to
preview changes before pushing:

```bash
bundle install
bundle exec jekyll serve
```

Then open http://localhost:4000

## Deploying

Push to `main` on GitHub. GitHub Pages rebuilds and redeploys automatically
within a minute or two — no other steps required.
