# Resume (Jekyll)

Esteban Casas’s résumé site, built with [Jekyll](https://jekyllrb.com/) and the **Pillar** theme by [Xiaoying Riley / 3rd Wave Media](http://themes.3rdwavemedia.com/).

**Live site:** [https://ecasasni.github.io/resume/](https://ecasasni.github.io/resume/)

## Prerequisites

- **Ruby 3.0+** (recommended: 3.2 or 3.3). Ruby 2.6 is too old for current gem dependencies (for example `ffi`).
- [Bundler](https://bundler.io/)

## Local setup

From the repository root:

```bash
bundle install
bundle exec jekyll serve
```

Open **http://127.0.0.1:4000/resume/** (this project sets `baseurl: "/resume"` in `_config.yml` for GitHub Pages).

Useful options:

```bash
bundle exec jekyll serve --livereload
bundle exec jekyll serve --baseurl ""   # site root at http://127.0.0.1:4000/ instead of /resume/
```

After changing `_config.yml` (for example `theme_skin`), restart the server so settings reload.

### Tooling notes

- The Gemfile lists **`bigdecimal`** so Ruby 3.4+ does not warn when Liquid loads it from the standard library.
- **`sass.silence_deprecations`** in `_config.yml` suppresses Dart Sass “slash division” warnings from vendored Bootstrap 4 SCSS. Removing it does not break the build; it only brings back noisy warnings.

## What to edit

| Area | File |
|------|------|
| Name, tagline, SEO, theme color, `baseurl` | `_config.yml` |
| Profile, summary, experience, skills, awards | `_data/data.yml` |
| Career summary body + tech strip | `summary` and `summary_stack` in `_data/data.yml` (see `_includes/summary.html`) |
| Avatar | Put the image in `assets/images/` and set `header.avatar` in `_data/data.yml` |

Theme colors are SCSS skins under `_sass/skins/`; which skin loads is controlled by `theme_skin` in `_config.yml`.

## Theme credit

Pillar is designed by Xiaoying Riley at [3rd Wave Media](http://themes.3rdwavemedia.com/).

## License

This project is licensed under the [MIT license](LICENSE.txt).
