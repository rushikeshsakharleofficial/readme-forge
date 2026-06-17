---
name: section
description: Generate or rewrite a single README section. Use when you want to add or update one section without regenerating the whole README.
trigger: /readme-forge:section
args:
  - name: section-name
    required: true
    values: [badges, hero, features, install, usage, api, config, contributing, license, changelog, structure]
  - name: --style
    values: [rich, minimal, dark]
    default: auto
---

# README Section Generator

Generate or rewrite a single README section. Does not touch the rest of the file.

## Usage

```text
/readme-forge:section features
/readme-forge:section install --style rich
/readme-forge:section api
/readme-forge:section badges --style dark
```

## Step 1 — Identify section

Parse the section name from args. Map to one of:

| Arg | What to generate |
|---|---|
| `badges` | Full badge row based on what exists in the project |
| `hero` | Centered hero block with title, tagline, badges |
| `features` | Features list or table |
| `install` | Installation instructions for the detected package manager |
| `usage` | Usage examples extracted from source/tests/examples |
| `api` | API reference table for the main exported functions/endpoints |
| `config` | Configuration table from .env.example or config files |
| `contributing` | Contributing section |
| `license` | License section and optionally create LICENSE file |
| `changelog` | Changelog section (link to CHANGELOG.md or generate from git log) |
| `structure` | Project structure tree |

## Step 2 — Scan what's needed

Only read the files relevant to the requested section. Don't scan the whole project.

- `badges`: check `.github/workflows/`, `LICENSE`, `package.json` version/name
- `features`: read `package.json` description, `src/index.ts` exports, `examples/`
- `install`: read `package.json` name, check lockfiles
- `usage`: read `examples/`, test files, entry point
- `api`: read exported function signatures from `src/index.ts` or route definitions
- `config`: read `.env.example`, config schema files
- `structure`: list directory tree depth 2

## Step 3 — Generate section

Output the section only — start from `## Section Title`, no surrounding context.

After output, state:
- What data was extracted
- What couldn't be verified (user should fill in)

## Step 4 — Insertion guidance

Tell the user where in the README to insert this section:
- "Insert after the badge row"
- "Insert before the ## Contributing section"
- "Replace the existing ## Features section"
