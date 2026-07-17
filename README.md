# Fisqua documentation

Source for the Fisqua documentation site at <https://docs.fisqua.org>.

Fisqua is a workspace for archival description, import, and publication,
developed at the UCSB Archives, Memory, and Preservation Lab and Neogranadina.

The site is a bilingual (English / Spanish) [Jekyll](https://jekyllrb.com/)
site built on the [just-the-docs](https://just-the-docs.com/) theme. English
pages live under `/docs/`, Spanish under `/guia/`.

## Building locally

```bash
bundle install
bundle exec jekyll serve --port 4002
```

The site is published to GitHub Pages on every push to `main`.
