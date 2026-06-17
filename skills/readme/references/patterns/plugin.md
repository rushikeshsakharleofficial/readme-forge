# Pattern: Claude Code Plugin

Based on: Darkforge, linux-admin. Use for projects with `.claude-plugin/plugin.json`.

---

## Section Order

1. Centered hero block
2. "What is this?" paragraph
3. Install instructions
4. Usage / skill table
5. Context-aware activation table (if many skills)
6. Why this / comparison table (optional)
7. Architecture (collapsible)
8. License footer

---

## Template (rich style)

```markdown
<div align="center">

# PLUGIN-NAME

### One-line tagline — what it does, not what it is.

<p>
  <img src="https://img.shields.io/badge/license-MIT-000000?style=for-the-badge&labelColor=000000&color=A78BFA" alt="MIT License" />
  <img src="https://img.shields.io/badge/Claude_Code-Plugin-000000?style=for-the-badge&labelColor=000000&color=A78BFA" alt="Claude Code Plugin" />
  <img src="https://img.shields.io/badge/skills-N-000000?style=for-the-badge&labelColor=000000&color=22D3EE" alt="N Skills" />
</p>

<sub>One punchy stat · Another stat · Another stat</sub>

</div>

## What is this?

A Claude Code plugin that [does X]. It provides [capability 1], [capability 2], and [capability 3]. [One sentence on what makes it different from doing this manually or with another tool.]

## Install

```bash
/plugin marketplace add OWNER/REPO
/plugin install PLUGIN-NAME@REPO-NAME
```

Or via CLI:
```bash
claude plugin marketplace add OWNER/REPO
claude plugin install PLUGIN-NAME@REPO-NAME
```

## Skills

| Skill | Use |
|---|---|
| `/PLUGIN:skill-one` | Short description |
| `/PLUGIN:skill-two` | Short description |
| `/PLUGIN:skill-three` | Short description |

## Usage

```text
/PLUGIN:main-skill do the thing with this argument
/PLUGIN:main-skill --flag value
```

## License

MIT — see [LICENSE](LICENSE).

---

<div align="center">

<sub>Built by <a href="https://github.com/OWNER"><b>AUTHOR</b></a>.</sub>

</div>
```

---

## Template (minimal style, linux-admin style)

```markdown
# PLUGIN-NAME

Short description of what the plugin does. One or two sentences max.

[![License](https://img.shields.io/github/license/OWNER/REPO?style=for-the-badge)](LICENSE)

## What is this?

A Claude Code plugin that [does X] by [mechanism]. Provides [list of major capabilities].

## Quick Start

**Install via CLI:**

```bash
claude plugin marketplace add OWNER/REPO
claude plugin install PLUGIN-NAME@REPO-NAME
```

**Or install via slash commands inside Claude Code:**

```text
/plugin marketplace add OWNER/REPO
/plugin install PLUGIN-NAME@REPO-NAME
```

Then invoke any skill inside Claude Code:

```text
/PLUGIN:main-skill argument here
/PLUGIN:other-skill argument here
```

Reload after edits:

```text
/reload-plugins
```

## Skills

### Core skills

| Skill | Use |
|---|---|
| `/PLUGIN:skill-one` | Short description |
| `/PLUGIN:skill-two` | Short description |

### Expert skills (if applicable)

| Skill | Use |
|---|---|
| `/PLUGIN:expert-skill` | Short description |

## Project Structure

```
PLUGIN-NAME/
├── .claude-plugin/
│   └── plugin.json
├── skills/
│   ├── skill-one/
│   │   └── SKILL.md
│   └── skill-two/
│       └── SKILL.md
└── README.md
```

## Contributing

Open a PR with a new skill directory under `skills/` and a matching entry in `plugin.json`. Follow the naming pattern of existing skills.

## License

MIT — see [LICENSE](LICENSE).
```

---

## What to extract from `.claude-plugin/plugin.json`

```json
{
  "name": "PLUGIN-NAME",       → use as title
  "description": "...",        → use in "What is this?" section
  "version": "X.Y.Z",         → use in version badge
  "skills": [...]              → build the skills table from this
}
```

## Skills table construction

For each skill in `plugin.json` skills array:
- Name → `/PLUGIN-NAME:skill-name`
- Description → second column of skills table

If skills have sub-skills or categories, group them with H3 headers.
