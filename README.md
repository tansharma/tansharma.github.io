# tansharma.com

Source for [tansharma.com](https://tansharma.com): a portfolio of apps, open-source tools and works in progress. It is plain static HTML and one stylesheet, served by GitHub Pages from `main`. There is no build step.

## Preview

```bash
python3 -m http.server 8000
```

Then open <http://localhost:8000>.

## Adding a project

- **It has its own site** (an app, or a project with docs): copy a `<li class="project-card">` in `index.html` into the right section and point its title link at that site. Copy the icon to `assets/icons/<name>.png`.
- **It doesn't**: copy `projects/counter.html` to `projects/<name>.html`, rewrite the hero, feature cards and project facts, then add a card in `index.html` that links to it. With no app icon, use the two-letter monogram tile.
- **Private or unreleased**: add a `project-card--wip` card under Work in progress, with a name and one line only. Don't link to private repositories.

## Changing the styles

Every page links `site.css?v=N`. After editing `site.css`, bump `N` on every page so browsers fetch the new stylesheet instead of a cached one (GitHub Pages lets browsers cache files for 10 minutes):

```bash
sed -i '' -E 's/site\.css\?v=[0-9]+/site.css?v=NEW/' *.html projects/*.html
```
