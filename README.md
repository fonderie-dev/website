# Fonderie website

Source of <https://fonderie-dev.github.io/website/>: a static Hugo site with
its own templates and stylesheet and no theme module. The only script is the
cookie-free Plausible statistics snippet served from the maintainer's own
analytics server; there are no third-party requests.

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
and the organisation profile. Its `repo` and `site` front matter link the
repository and the atelier's project site, which is built from that
repository's `docs/`.

`content/impressum.md` and `content/datenschutz.md` hold this site's Impressum
and privacy notice.

## Licence

Templates, stylesheet and tools: Apache-2.0, see [LICENSE](LICENSE). Text and
the Fonderie mark: © 2026 R. Heller.
