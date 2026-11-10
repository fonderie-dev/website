# Fonderie website

Source of <https://fonderie-dev.github.io/website/>: a static Hugo site with
its own templates and stylesheet, no theme module, no JavaScript and no
third-party requests.

## Build locally

Requires Hugo extended ≥ 0.146 (CI pins 0.169.0) and Python 3.

```sh
hugo server                                  # preview at http://localhost:1313/website/
hugo --gc --minify --panicOnWarning          # production build into public/
python3 tools/check_links.py public /website/
```

Pushes to `main` build, check internal links and deploy to GitHub Pages.
Pull requests build and check without deploying.

## Layout

```
content/              pages; ateliers/ holds one page per atelier
data/principes.yaml   short principles shown on the home page
layouts/              templates (home, section, page, ateliers/page, 404)
assets/css/main.css   the only stylesheet; light and dark follow the system
static/images/        mark, favicons and the social preview image
tools/check_links.py  internal link and anchor check for the built site
```

An atelier's status stamp comes from `status` in its front matter (0 scaffold,
1 draft, 2 usable, 3 released). Keep it in step with the repository README
and the organisation profile.

The Impressum is the one on <https://r-heller.github.io/website/impressum/>;
`content/datenschutz.md` covers this site.

## Licence

Templates, stylesheet and tools: Apache-2.0, see [LICENSE](LICENSE). Text and
the Fonderie mark: © 2026 R. Heller.
