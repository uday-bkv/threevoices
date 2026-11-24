# Three Voices

A monthly record of voice-AI use cases and implementation guides in autism
care, agriculture, and space technologies.

## Local development

Install Ruby and Bundler, then run:

```sh
bundle install
bundle exec jekyll serve
```

The site is configured with the `/threevoices` base path used by its GitHub
Pages project site.

## Publishing

The `Deploy to GitHub Pages` workflow builds the site on pushes to `main`.
Enable GitHub Pages for the repository using **GitHub Actions** as the build
and deployment source. The published URL is
<https://uday-bkv.github.io/threevoices/>.

## Adding an issue

1. Copy the case-data template in `_templates/new-issue/cases.yml` to
   `_data/threevoices/cases/YYYY-MM.yml` and add the issue to
   `_data/threevoices/issues.yml`.
2. Copy the two page templates in `_templates/new-issue/` to
   `issues/YYYY-MM/`, then set the issue slug, title, and permalink in each.
