<div align="center">

# README Forge

### Auto-generates production-quality README files from project context.

<a href="https://readme-typing-svg.demolab.com/?font=JetBrains+Mono&weight=600&size=20&duration=2400&pause=700&color=A78BFA&center=true&vCenter=true&width=720&height=44&lines=One+command.+A+README+worth+reading.;Stack-aware.+Never+generic.;library+%E2%86%92+cli+%E2%86%92+plugin+%E2%86%92+api+%E2%86%92+saas.;No+placeholders.+No+invented+facts.">
  <img src="https://readme-typing-svg.demolab.com/?font=JetBrains+Mono&weight=600&size=20&duration=2400&pause=700&color=A78BFA&center=true&vCenter=true&width=720&height=44&lines=One+command.+A+README+worth+reading.;Stack-aware.+Never+generic.;library+%E2%86%92+cli+%E2%86%92+plugin+%E2%86%92+api+%E2%86%92+saas.;No+placeholders.+No+invented+facts." alt="Typing tagline" />
</a>

<p>
  <img src="https://img.shields.io/badge/license-MIT-000000?style=for-the-badge&labelColor=000000&color=A78BFA" alt="MIT License" />
  <img src="https://img.shields.io/badge/Claude_Code-Plugin-000000?style=for-the-badge&labelColor=000000&color=A78BFA" alt="Claude Code Plugin" />
  <img src="https://img.shields.io/badge/skills-3-000000?style=for-the-badge&labelColor=000000&color=22D3EE" alt="3 Skills" />
  <img src="https://img.shields.io/badge/styles-rich%20·%20minimal%20·%20dark-000000?style=for-the-badge&labelColor=000000&color=F472B6" alt="3 Styles" />
  <img src="https://img.shields.io/badge/types-6-000000?style=for-the-badge&labelColor=000000&color=22D3EE" alt="6 Project Types" />
</p>

<sub><b>6 project types</b> · <b>3 output styles</b> · <b>SEO-optimized output</b> · <b>zero placeholder text</b></sub>

</div>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:000000,50:A78BFA,100:22D3EE&height=4&section=header" width="100%" />

> *"Every dev who's had Claude write a README knows the result: generic Tailwind purple, placeholder text, badges that 404, and a feature list that was invented on the spot."* README Forge ends that.

<div align="center">

<h2>What makes it different</h2>

<sub>Six things every other README generator gets wrong.</sub>

</div>

<table>
  <tr>
    <td width="33%" valign="top" align="center">
      <img src="https://img.shields.io/badge/-STACK--AWARE-A78BFA?style=for-the-badge&labelColor=000000" /><br /><br />
      <b>Reads Your Project First</b>
      <p align="left"><sub>Scans <code>package.json</code>, lockfiles, directory structure, CI configs, and entry points before writing a single word. Output reflects what's actually in the repo.</sub></p>
    </td>
    <td width="33%" valign="top" align="center">
      <img src="https://img.shields.io/badge/-ZERO%20PLACEHOLDERS-22D3EE?style=for-the-badge&labelColor=000000" /><br /><br />
      <b>No Invented Content</b>
      <p align="left"><sub>Every claim is verified. If a fact can't be found in the project, it goes into a <code>Maintainer TODOs</code> section with a precise question — never invented.</sub></p>
    </td>
    <td width="33%" valign="top" align="center">
      <img src="https://img.shields.io/badge/-6%20PROJECT%20TYPES-F472B6?style=for-the-badge&labelColor=000000" /><br /><br />
      <b>Type-Aware Structure</b>
      <p align="left"><sub>Library, CLI tool, SaaS app, Claude Code plugin, API/backend, open-source. Each has a different section order, different content priorities, different style defaults.</sub></p>
    </td>
  </tr>
  <tr>
    <td width="33%" valign="top" align="center">
      <img src="https://img.shields.io/badge/-3%20STYLES-A78BFA?style=for-the-badge&labelColor=000000" /><br /><br />
      <b>Rich, Minimal, or Dark</b>
      <p align="left"><sub><code>--style rich</code>: typing SVG hero, dark badges, 3-column feature tables. <code>--style minimal</code>: clean prose, flat badges, code first. <code>--style dark</code>: AMOLED-first with violet/cyan accents.</sub></p>
    </td>
    <td width="33%" valign="top" align="center">
      <img src="https://img.shields.io/badge/-SEO%20OPTIMIZED-22D3EE?style=for-the-badge&labelColor=000000" /><br /><br />
      <b>GitHub + Google Discoverable</b>
      <p align="left"><sub>Keyword-first H1, optimized opening paragraph (120–160 chars for snippet display), verified badge URLs, correct internal links. Output ranks.</sub></p>
    </td>
    <td width="33%" valign="top" align="center">
      <img src="https://img.shields.io/badge/-BADGE%20VERIFIED-F472B6?style=for-the-badge&labelColor=000000" /><br /><br />
      <b>Badges That Don't 404</b>
      <p align="left"><sub>Only adds a badge if the thing it represents exists: CI badge needs a workflow file, npm badge needs a published package, license badge needs a LICENSE file.</sub></p>
    </td>
  </tr>
</table>

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:22D3EE,50:A78BFA,100:000000&height=4&section=footer" width="100%" />

</div>

## Install

```bash
/plugin marketplace add rushikeshsakharleofficial/readme-forge
/plugin install readme-forge@readme-forge
```

Or via CLI:

```bash
claude plugin marketplace add rushikeshsakharleofficial/readme-forge
claude plugin install readme-forge@readme-forge
```

## Usage

```bash
# Auto-detect project type and generate
/readme-forge:readme

# Force a style
/readme-forge:readme --style rich
/readme-forge:readme --style minimal
/readme-forge:readme --style dark

# Force a project type
/readme-forge:readme --type library
/readme-forge:readme --type cli-tool
/readme-forge:readme --type plugin

# Update an existing README (preserve structure, refresh content)
/readme-forge:readme --update

# Generate only one section
/readme-forge:section features
/readme-forge:section install --style rich
/readme-forge:section api

# Generate badges only
/readme-forge:badges
/readme-forge:badges --dark
```

## Context-aware activation

| You type… | README Forge does… | You get… |
|---|---|---|
| `/readme-forge:readme` | Scans project, detects type + style | Full README matched to your stack |
| `/readme-forge:readme --style rich` | Forces Darkforge-style visual layout | Dark badges, typing hero, feature tables |
| `/readme-forge:readme --style minimal` | Forces clean prose layout | ripgrep/zustand-style, code first |
| `/readme-forge:readme --type cli-tool` | Overrides auto-detection | CLI-optimized: install-by-platform, flag table |
| `/readme-forge:readme --update` | Reads existing README | Refreshes stale sections, keeps structure |
| `/readme-forge:section api` | Scans exports and routes | API reference table for your endpoints |
| `/readme-forge:badges` | Checks CI, license, package | Verified badge row, no 404s |

## Project type auto-detection

| Signal in your project | Detected type |
|---|---|
| `.claude-plugin/plugin.json` | `plugin` |
| `bin` in `package.json` or `cmd/` directory | `cli-tool` |
| `next.config.*` or `vite.config.*` + `src/app/` | `saas-app` |
| `exports` / `main` in `package.json`, no framework in deps | `library` |
| `express` / `fastapi` / `hono` / `gin` in deps | `api` |
| Rust `lib.rs`, Go package (non-main) | `library` |
| Fallback | `open-source` |

## Skills

| Skill | Use |
|---|---|
| `/readme-forge:readme` | Generate or update a complete README |
| `/readme-forge:section <name>` | Generate one section: `badges`, `hero`, `features`, `install`, `usage`, `api`, `config`, `contributing`, `license`, `structure` |
| `/readme-forge:badges` | Generate a verified badge row |

## Architecture

<details>
<summary><b>Plugin structure</b> — click to expand</summary>

```
readme-forge/
├── .claude-plugin/
│   ├── plugin.json
│   └── marketplace.json
├── skills/
│   ├── readme/
│   │   ├── SKILL.md                    ← main brain: scan → classify → style → generate
│   │   └── references/
│   │       ├── 00-project-analysis.md  ← what to scan and how to interpret it
│   │       ├── 01-badges.md            ← complete badge catalog with verified URLs
│   │       ├── 02-sections.md          ← all section templates
│   │       ├── 03-style-guides.md      ← rich / minimal / dark / SEO rules
│   │       └── patterns/
│   │           ├── library.md          ← zustand/tRPC/vite style
│   │           ├── cli-tool.md         ← ripgrep/gh CLI style
│   │           ├── saas-app.md         ← Next.js / startup style
│   │           ├── plugin.md           ← Darkforge / linux-admin style
│   │           ├── api.md              ← Express / FastAPI style
│   │           └── open-source.md      ← scripts / configs / templates
│   ├── section/
│   │   └── SKILL.md                    ← single-section generator
│   └── badges/
│       └── SKILL.md                    ← badge-only generator
└── README.md
```

The `readme` skill loads `SKILL.md` first (lean brain — scan, classify, route). Reference and pattern files load on demand based on what your project is, keeping every interaction fast and token-efficient.

</details>

## Why README Forge

| | Other README generators | **README Forge** |
|---|---|---|
| **Content source** | AI imagination | **Verified project files** |
| **Project types** | Generic | **6 specialized patterns** |
| **Output styles** | One | **3 (rich, minimal, dark)** |
| **Badges** | Often 404 | **Only verified badges** |
| **SEO** | None | **Keyword-first H1, optimized snippet** |
| **Placeholder text** | Common | **Zero — uses Maintainer TODOs** |
| **Single section** | Full regen only | **`/readme-forge:section <name>`** |
| **Badges only** | Full regen only | **`/readme-forge:badges`** |

---

<div align="center">

<sub>MIT licensed. Write READMEs worth reading.</sub>

<sub>Built by <a href="https://github.com/rushikeshsakharleofficial"><b>Rushikesh</b></a>.</sub>

</div>
