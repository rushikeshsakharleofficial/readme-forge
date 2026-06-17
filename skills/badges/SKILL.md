---
name: badges
description: Generate a verified shields.io badge row for the current project. Only adds badges for things that exist (CI badge needs a workflow file, npm badge needs a published package, license badge needs LICENSE file). Supports --dark for black backgrounds, --light for standard colors.
argument-hint: "[--dark] [--light] [--style for-the-badge|flat|flat-square]"
---

# Badge Generator

Generate a complete, verified badge row for the project.

## Rules

1. Only generate badges for things that actually exist.
2. Never invent badge IDs, workflow file names, or package names.
3. If a badge would require something that doesn't exist (no CI, no license file), skip it.

## Scan checklist

Run in parallel:

- `package.json` → extract `name`, `version`, `license`, `private` flag, `repository`
- `Cargo.toml` → extract `name`, `version`, `license`
- `pyproject.toml` → extract `name`, `version`, `license`
- `go.mod` → extract module name
- `.github/workflows/` → list workflow files (for CI badge)
- `LICENSE` → confirm exists (for license badge)
- `codecov.yml` or `.codecov.yml` → confirms coverage badge is valid

## Badge selection logic

| Badge | Include if |
|---|---|
| CI / Build | `.github/workflows/*.yml` exists — use the main CI file name |
| License | `LICENSE` file exists at root |
| npm version | `package.json` with no `"private": true` and `name` field |
| npm downloads | Same as above |
| PyPI version | `pyproject.toml` with public package |
| Crates.io | `Cargo.toml` |
| Go pkg | `go.mod` exists |
| Coverage | `codecov.yml` or Coveralls config exists |
| Claude Code Plugin | `.claude-plugin/plugin.json` exists |
| GitHub stars | Always (for any public GitHub repo) |

## Output format

Output a ready-to-paste badge block with:
- Correct URLs (no fabricated slugs)
- `--style for-the-badge` with `labelColor=000000` if `--dark` flag
- `--style flat` with default colors if `--light` flag
- Auto: `for-the-badge` for plugins/saas, `flat` for libraries/CLI

Followed by a note on what was skipped and why.
