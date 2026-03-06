# AGENTS.md

## Cursor Cloud specific instructions

This is a **documentation-only repository** (11 Markdown files, no source code). There are no package manager files, build systems, or application services.

### Lint

```
markdownlint-cli2 "**/*.md"
```

Pre-existing lint issues are all `MD013/line-length` warnings plus a couple of `MD029/ol-prefix` in `sensor-fusion.md`. These are in the original content and not regressions.

### Preview / "Run"

```
grip README.md 0.0.0.0:6419
```

Starts a GitHub-flavored Markdown preview server (Flask-based). Navigation between docs works via relative links (e.g. `localhost:6419/camera.md`). `grip` uses the GitHub API to render; if rate-limited, pass `--user` and `--pass` or a token. For offline rendering, `grip` falls back to its local renderer.

### Notes

- `grip` is installed to `~/.local/bin`; ensure `PATH` includes it (`export PATH="$HOME/.local/bin:$PATH"`).
- `markdownlint-cli2` is installed globally via npm.
- There are no automated tests, Docker services, or build steps for this repo.
