# Steven Baker Lab site — setup notes

This is a customized al-folio site, already filled in with your real content:
Home (bio + news feed), Research (4 questions, inline-cited), People (5 current
members + 2 alumni), Contact (merged with Opportunities). No Publications,
Blog, CV, or Teaching pages — kept to the four pages we planned.

## Get it live — step by step

1. **Create a new, empty repo on GitHub** (not a fork — this folder is already
   your customized copy). Name it whatever you like, e.g. `baker-lab-site`.

2. **Push this folder to it.** Easiest from within a GitHub Codespace opened
   on your new empty repo — drag these files in, or from a terminal:
   ```
   git init
   git add .
   git commit -m "Initial site"
   git branch -M main
   git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
   git push -u origin main
   ```

3. **Turn on GitHub Pages:** repo Settings → Pages → Source: GitHub Actions.
   Al-folio ships with a deploy workflow, so every push after this rebuilds
   the live site automatically.

4. **Preview locally before you push (optional but recommended):**
   ```
   bundle install
   bundle exec jekyll serve
   ```
   Opens at `localhost:4000`. Needs Ruby installed, or just do this inside
   a Codespace instead of your own machine.

## Things I flagged with TODO in the files — do these before launch

- **Photos.** I copied the default al-folio placeholder image to `steve.jpg`,
  `himadri.jpg`, `mike.jpg`, `etienne.jpg`, `jillian.jpg` in `assets/img/`
  just so the site builds without errors. Replace all five with real photos
  before this goes live — right now they're all the same stock silhouette.

- **Domain name.** `_config.yml` and `CNAME` are both set to a placeholder,
  `sfbakerlab.com` — swap both to whatever you actually register. Given the
  Susan Baker / David Baker naming collision we discussed, I'd stick with
  something that includes your first name or "sfbkr," not bare "bakerlab."

- **Google Scholar ID.** `_data/socials.yml` has a blank `scholar_userid` —
  grab it from your Scholar profile URL. Also blank: `github` and `orcid` —
  fill in if you want those icons to show.

- **Email + address.** Currently your real Lovelace info (`contact.md` and
  `about.md`). Swap to your Loyola/Stritch details once you have them.

- **Publications page.** Deliberately not included — see the earlier
  discussion about not padding a young lab's site with a thin pub list.
  `_bibliography/papers.bib` is still there and pre-populated with your
  5 papers in case you want to turn a real Publications page back on later
  (al-folio's original `_pages/publications.md`, which I removed, is the
  template for that if/when you want it back).

## Where everything lives, if you want to edit further

- `_config.yml` — site title, description, URL, keywords
- `_pages/about.md` — Home page content + bio
- `_pages/research.md` — the 4 research questions
- `_pages/profiles.md` + `_pages/people-*.md` — People page + individual bios
- `_pages/contact.md` — Contact/Opportunities
- `_news/*.md` — the news items shown on the homepage (add a new dated file
  for each new update — most recent date shows first, automatically)
- `_data/socials.yml` — email, Bluesky, Scholar, etc.
- `assets/img/` — all photos
