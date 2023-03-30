# ruzickap.github.io

[![GitHub Actions status - Lint Code Base](https://github.com/ruzickap/ruzickap.github.io/actions/workflows/mega-linter.yml/badge.svg)](https://github.com/ruzickap/ruzickap.github.io/actions/workflows/mega-linter.yml)

## Overview

My personal site and blog...

[**ruzickap.github.io →**](https://ruzickap.github.io/)

- Main Page: <https://blog.ruzicka.dev>, <https://ruzickap.github.io>
- Dev Page: <https://ruzickap-github-io.pages.dev>

[![Build and Deploy](https://github.com/ruzickap/ruzickap.github.io/actions/workflows/gh-pages-build.yml/badge.svg?branch=main)](https://github.com/ruzickap/ruzickap.github.io/actions/workflows/gh-pages-build.yml)

## Theme Source

Chirpy:

- [GitHub](https://github.com/cotes2020/jekyll-theme-chirpy)
- [Example and tips/best practices](https://chirpy.cotes.page/)

## Building / Testing Locally

On Ubuntu / Intel-based Mac:

```bash
bundle install
bundle exec jekyll s
```

Using Docker:

```bash
docker run --rm -it --volume="${PWD}:/srv/jekyll:Z" --publish 4000:4000 jekyll/jekyll jekyll serve
```

Megalinter:

```bash
mega-linter-runner --flavor documentation \
  -e "'DISABLE_LINTERS=REPOSITORY_DEVSKIM,SPELL_CSPELL'" \
  -e BASH_SHFMT_ARGUMENTS="--indent 2 --space-redirects" \
  -e FORMATTERS_DISABLE_ERRORS="false" \
  -e HTML_HTMLHINT_FILTER_REGEX_EXCLUDE="^index.html" \
  -e JSON_PRETTIER_FILTER_REGEX_EXCLUDE="^.markdown-link-check.json" \
  -e MARKDOWN_MARKDOWNLINT_CONFIG_FILE=".markdownlint.yml" \
  -e PRINT_ALPACA="false" \
  -e REPORT_OUTPUT_FOLDER="/tmp/" \
  -e RUBY_RUBOCOP_FILTER_REGEX_EXCLUDE="^_plugins" \
  -e SPELL_CSPELL_FILTER_REGEX_INCLUDE="(^README.md|^_posts/)" \
  -e SPELL_MISSPELL_FILTER_REGEX_EXCLUDE="^_data/locales" \
  -e YAML_PRETTIER_FILTER_REGEX_EXCLUDE="(^_data/|^_config.yml)" \
  -e YAML_V8R_FILTER_REGEX_EXCLUDE="(^_data/|^_config.yml)"
```
