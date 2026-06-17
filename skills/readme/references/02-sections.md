# Section Templates

Copy and adapt. Never use as-is — fill with real project content.

---

## Hero (rich style)

```markdown
<div align="center">

<!-- <img src="docs/images/logo.png" alt="ProjectName" width="120" /> -->

# ProjectName

### One punchy tagline that says what it does, not what it is.

<a href="TYPING_SVG_URL">
  <img src="TYPING_SVG_URL" alt="Typing tagline" />
</a>

<p>
  ![License Badge]
  ![Version Badge]
  ![Build Badge]
</p>

<sub><b>Key stat</b> · <b>Key stat</b> · <b>Key stat</b></sub>

</div>
```

## Hero (minimal style)

```markdown
# ProjectName

> One punchy tagline that says what it does, not what it is.

[![License](BADGE_URL)](LICENSE)
[![Version](BADGE_URL)](https://...)
[![Build](BADGE_URL)](https://...)
```

## Hero (library — zustand style)

```markdown
<p align="center">
  <img src="./docs/logo.png" />
</p>

[![Build Status](BADGE)](LINK)
[![Version](BADGE)](LINK)
[![Downloads](BADGE)](LINK)

Short description. What problem it solves. What makes it different in one sentence.

```bash
npm install PACKAGE
```
```

---

## Description / What is this

For plugins and tools:
```markdown
## What is this?

A [type] that [does X] by [mechanism]. It provides [capability 1], [capability 2], and [capability 3].
```

For libraries:
```markdown
A small, fast [type] for [use case]. [Key differentiator — what makes it better than alternatives].

[Demo link if available] · [Docs link]
```

---

## Quick Start / Getting Started

```markdown
## Quick Start

```bash
npm install PACKAGE
```

```ts
import { thing } from 'PACKAGE'

const result = thing({ option: 'value' })
```
```

For CLI tools:
```markdown
## Quick Start

**Install:**
```bash
npm install -g PACKAGE
# or
brew install PACKAGE
```

**Run:**
```bash
COMMAND --help
COMMAND <subcommand> [flags]
```
```

---

## Features (minimal — bullet list, tRPC style)

```markdown
## Features

- ✅ Short description of feature one — one sentence max
- 🔑 Short description of feature two
- ⚡️ Short description of feature three
- 🛠️ Short description of feature four
- 📦 Short description of feature five
```

Pick emoji that match the feature, don't repeat them. Skip emoji entirely for plain minimal style.

---

## Features (rich — table with three columns)

```markdown
<table>
  <tr>
    <td width="33%" valign="top" align="center">
      <b>Feature Name</b>
      <p align="left"><sub>One to two sentence description. What it does and why it matters.</sub></p>
    </td>
    <td width="33%" valign="top" align="center">
      <b>Feature Name</b>
      <p align="left"><sub>One to two sentence description.</sub></p>
    </td>
    <td width="33%" valign="top" align="center">
      <b>Feature Name</b>
      <p align="left"><sub>One to two sentence description.</sub></p>
    </td>
  </tr>
</table>
```

---

## Installation

### npm package:
```markdown
## Install

```bash
npm install PACKAGE
# pnpm
pnpm add PACKAGE
# yarn
yarn add PACKAGE
# bun
bun add PACKAGE
```
```

### Global CLI:
```markdown
## Install

```bash
npm install -g PACKAGE
```

Or download a binary from the [releases page](https://github.com/OWNER/REPO/releases/latest).
```

### Multi-platform CLI (gh style):
```markdown
## Install

**macOS:** `brew install PACKAGE`

**Linux:** `sudo apt install PACKAGE` or see [Linux install docs](docs/install_linux.md)

**Windows:** `winget install PACKAGE` or see [Windows install docs](docs/install_windows.md)

**Build from source:** `cargo install PACKAGE` / `go install .` / `npm install -g .`
```

### Claude Code plugin:
```markdown
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
```

---

## Usage

### Function/library usage:
```markdown
## Usage

```ts
import { functionName } from 'PACKAGE'

// Basic usage
const result = functionName({ input: 'value' })

// With options
const result2 = functionName({
  input: 'value',
  option: true,
  callback: (data) => console.log(data),
})
```
```

### CLI usage:
```markdown
## Usage

```bash
COMMAND [global-flags] <subcommand> [flags]

# Common examples
COMMAND subcommand --flag value
COMMAND subcommand --help
```

| Flag | Short | Default | Description |
|---|---|---|---|
| `--flag` | `-f` | `default` | One sentence |
| `--output` | `-o` | `stdout` | One sentence |
```

### Skills table (Claude Code plugin):
```markdown
## Skills

| Skill | Use |
|---|---|
| `/plugin:skill-name` | Short description |
| `/plugin:other-skill` | Short description |
```

---

## API Reference (library)

```markdown
## API

### `functionName(options)`

Short description.

**Parameters:**

| Parameter | Type | Default | Description |
|---|---|---|---|
| `option1` | `string` | `''` | What it does |
| `option2` | `boolean` | `false` | What it does |
| `option3` | `(data: T) => void` | `undefined` | What it does |

**Returns:** `Promise<Result>` — short description of what's returned.

```ts
const result = await functionName({ option1: 'value' })
// result: { id: string, data: T }
```
```

---

## Configuration

```markdown
## Configuration

| Option | Type | Default | Description |
|---|---|---|---|
| `KEY_ONE` | `string` | `''` | One sentence |
| `KEY_TWO` | `number` | `3000` | One sentence |
| `KEY_THREE` | `boolean` | `false` | One sentence |

Copy `.env.example` to `.env` and fill in values.
```

---

## Project Structure

```markdown
## Project Structure

```
project/
├── src/
│   ├── index.ts        ← entry point
│   └── lib/            ← core logic
├── tests/              ← test suite
├── docs/               ← documentation
└── examples/           ← usage examples
```
```

---

## Why / Comparison table

```markdown
## Why PROJECTNAME

| | Alternative | **PROJECTNAME** |
|---|---|---|
| **Feature A** | partial | **full** |
| **Feature B** | manual | **automatic** |
| **Feature C** | none | **built-in** |
```

---

## Contributing

```markdown
## Contributing

Open a PR with [short instruction matching project conventions]. See [CONTRIBUTING.md](CONTRIBUTING.md) for setup.
```

For plugins (linux-admin style):
```markdown
## Contributing

Open a PR with a new skill directory under `skills/`, a matching doc under `docs/`, and a test in `tests/`. Follow the naming pattern of existing skills.
```

---

## License footer

```markdown
---

<div align="center">

<sub>MIT licensed. [Short sign-off relevant to the project.]</sub>

<sub>Built by <a href="https://github.com/OWNER"><b>AUTHOR</b></a>.</sub>

</div>
```

Plain:
```markdown
## License

[MIT](LICENSE) — see LICENSE file.
```
