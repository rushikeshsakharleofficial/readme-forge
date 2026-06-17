# Style Guides

## Rich / Dark Style (Darkforge-inspired)

Based on analysis of: Darkforge plugin README, Next.js README, shadcn/ui.

### Layout pattern
```
1. <div align="center"> block
   - Logo image (optional)
   - H1 title
   - H3 tagline
   - Typing SVG (optional, violet A78BFA color)
   - Badge row (for-the-badge, black background)
   - Stat sub-line
   </div>
2. Capsule-render wave divider
3. "What makes it different" section → 3-column HTML table
4. Feature deep-dives in collapsible <details> blocks
5. Comparison table vs alternatives
6. Context-aware activation or usage table
7. Install section (code block)
8. Design tokens / config (if relevant)
9. Architecture (collapsible)
10. Star history + contributors
11. License footer (centered)
```

### Badge row template
```markdown
<p>
  <img src="https://img.shields.io/badge/license-MIT-000000?style=for-the-badge&labelColor=000000&color=A78BFA" alt="MIT License" />
  <img src="https://img.shields.io/badge/version-1.0.0-000000?style=for-the-badge&labelColor=000000&color=22D3EE" alt="Version" />
  <img src="https://img.shields.io/badge/Claude_Code-Plugin-000000?style=for-the-badge&labelColor=000000&color=A78BFA" alt="Claude Code Plugin" />
</p>
```

### Feature 3-column table template
```html
<table>
  <tr>
    <td width="33%" valign="top" align="center">
      <img src="https://img.shields.io/badge/-FEATURE-A78BFA?style=for-the-badge&labelColor=000000" /><br /><br />
      <b>Feature Title</b>
      <p align="left"><sub>One to two sentences explaining the feature. Focus on what makes it valuable.</sub></p>
    </td>
    <td width="33%" valign="top" align="center">
      <img src="https://img.shields.io/badge/-FEATURE-22D3EE?style=for-the-badge&labelColor=000000" /><br /><br />
      <b>Feature Title</b>
      <p align="left"><sub>One to two sentences.</sub></p>
    </td>
    <td width="33%" valign="top" align="center">
      <img src="https://img.shields.io/badge/-FEATURE-F472B6?style=for-the-badge&labelColor=000000" /><br /><br />
      <b>Feature Title</b>
      <p align="left"><sub>One to two sentences.</sub></p>
    </td>
  </tr>
</table>
```
Alternate badge colors per row: violet (A78BFA) → cyan (22D3EE) → pink (F472B6).

### Collapsible details block
```markdown
<details>
<summary><b>Section Title</b> — click to expand</summary>

Content here.

</details>
```

### Comparison table
```markdown
| | Other tools | **This tool** |
|---|---|---|
| **Feature A** | ❌ | ✅ |
| **Feature B** | partial | **full** |
| **Feature C** | manual | **automatic** |
```

---

## Minimal Style (ripgrep / zustand / gh-cli inspired)

### Layout pattern
```
1. [Optional centered logo image]
2. Badge row (flat style, all same color)
3. H1 title (may be plain text, not centered)
4. One short paragraph description — what it is and why it's good
5. Install command (prominent)
6. First usage example — actual code, not pseudocode
7. ## Features (bullet list with emoji or plain bullets)
8. ## Installation (full detail by platform if needed)
9. ## Usage (more examples, flag tables)
10. ## API / Reference (if library)
11. ## Configuration
12. ## Contributing
13. ## License (one line)
```

### Badge row (zustand black style)
```markdown
[![Build](https://img.shields.io/github/actions/workflow/status/OWNER/REPO/test.yml?branch=main&style=flat&colorA=000000&colorB=000000)](https://github.com/OWNER/REPO/actions)
[![Version](https://img.shields.io/npm/v/PACKAGE?style=flat&colorA=000000&colorB=000000)](https://www.npmjs.com/package/PACKAGE)
[![Downloads](https://img.shields.io/npm/dt/PACKAGE?style=flat&colorA=000000&colorB=000000)](https://www.npmjs.com/package/PACKAGE)
```

### Description block
```markdown
Short, direct description. State what it does. State what makes it different. Skip adjectives that don't mean anything.

You can try a live [demo](LINK) and read the [docs](LINK).

```bash
npm install PACKAGE
```
```

---

## GitHub Dark (Next.js / Vercel style)

### Layout pattern
```
1. <div align="center"> block
   - <picture> tag for dark/light logo swap
   - H1 title
   - Made by / Platform badge (black, for-the-badge)
   - Version badge (black labelColor)
   - License badge
   - Community badge
   </div>
2. ## Getting Started (prose paragraph, no bullets)
3. ## Documentation (link out)
4. ## Community (Discord, Discussions)
5. ## Contributing
6. ## Security
```

### Dark/light logo swap
```html
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="URL_DARK">
  <source media="(prefers-color-scheme: light)" srcset="URL_LIGHT">
  <img alt="Logo" src="URL_FALLBACK" height="128">
</picture>
```

---

## SEO Rules (apply to all styles)

From the old readme-generate-pro skill — these rules maximize GitHub + Google discoverability.

### H1 Title
- Never a bare product name. Use keyword-first pattern.
- Pattern: `{Primary keyword} for {Platform} — {Product name}`
- Example: `README Generator for Claude Code — readme-forge`
- Keep under 70 characters.

### Opening paragraph (meta description)
- Used by GitHub and Google as the page description snippet.
- Must contain: what the tool does (verb-first), primary platform/ecosystem, key differentiator.
- Include 2+ signal terms: `auto-generate`, `auto-update`, `no API key`, `zero-dependency`, primary language, package manager command.
- Target 120–160 characters.
- Never open with: "A tool for…", "This project…", "An awesome…"

### Keyword coverage
Before writing, identify 3–5 search terms a developer would use. Verify each appears at least once.

High-intent terms by type:
- CLI tool: `command-line`, `cli`, `terminal`, executable name
- Library: `npm install PACKAGE`, primary function name
- Plugin: `claude code plugin`, skill name, install command
- API: `REST API`, `GraphQL`, framework name

### README length
- Optimal: 500–2000 words.
- Under 300 = thin content.
- Over 4000 without TOC = poor UX.
- If over 2000 words, add `## Table of Contents` with anchor links.

### Internal links
- Always link to: Issues page, CONTRIBUTING.md (if exists), LICENSE file.
- Use absolute GitHub URLs for Issues and Releases — they work on npm/PyPI too.

### Code blocks hygiene
- Always use language tags: ` ```bash `, ` ```ts `, ` ```json `
- Don't prefix commands with `$`
- Bash comments (`# comment`) inside code blocks can be misread by crawlers — rewrite as inline comments or prose
