# AGENTS.md

## Cursor Cloud specific instructions

This is a **documentation-only repository** (Markdown files documenting hardware/software bring-up for an ECE191 autonomous car). There is no application source code.

### Docs framework

The site uses [MkDocs](https://www.mkdocs.org/) with the [Material](https://squidfunk.github.io/mkdocs-material/) theme. Config is in `mkdocs.yml`. The `docs/` directory contains symlinks to the root-level `.md` files (MkDocs requires a separate docs dir).

### Key commands

| Task | Command |
|------|---------|
| Dev server | `mkdocs serve --dev-addr 0.0.0.0:8000` |
| Build | `mkdocs build` (output in `site/`) |
| Lint | `markdownlint-cli2 "**/*.md"` |

### Notes

- `mkdocs` and `markdownlint-cli2` are installed via the update script (pip / npm global).
- The `.markdownlint-cli2.jsonc` config excludes `site/` and `docs/` (symlinks) from linting.
- Pre-existing lint warnings are mostly `MD013/line-length`; these are in the original content.
- The MkDocs 2.0 compatibility warning from Material is informational only and does not affect the build.
