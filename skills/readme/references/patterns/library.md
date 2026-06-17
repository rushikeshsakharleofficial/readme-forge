# Pattern: Library / Package

Based on: zustand, tRPC, vite. Use for npm/PyPI/crates.io packages where code is imported, not run directly.

---

## Section Order

1. [Optional: centered logo image]
2. Badge row (flat, all-black style preferred)
3. H1 project name + one-line description
4. Install command (prominent, near top)
5. Quick start (minimal working example)
6. Features list
7. Full usage examples
8. API reference (if small enough to inline; else link out)
9. TypeScript usage (if TS types are a feature)
10. Configuration
11. Comparison / Why this (if alternatives exist)
12. Contributing
13. License

---

## Template (minimal, zustand-inspired)

```markdown
<p align="center">
  <img src="./docs/logo.png" />
</p>

[![Build Status](https://img.shields.io/github/actions/workflow/status/OWNER/REPO/test.yml?branch=main&style=flat&colorA=000000&colorB=000000)](https://github.com/OWNER/REPO/actions)
[![Version](https://img.shields.io/npm/v/PACKAGE?style=flat&colorA=000000&colorB=000000)](https://www.npmjs.com/package/PACKAGE)
[![Downloads](https://img.shields.io/npm/dt/PACKAGE.svg?style=flat&colorA=000000&colorB=000000)](https://www.npmjs.com/package/PACKAGE)

# PACKAGE-NAME

Short, direct description. What problem it solves. What makes it different in one sentence. No adjectives that don't mean anything.

You can try a live [demo](DEMO_URL) and read the [docs](DOCS_URL).

```bash
npm install PACKAGE
```

## Quick start

```ts
import { mainExport } from 'PACKAGE'

// Minimal working example — copied from examples/ or tests/
const result = mainExport({
  option: 'value',
})
```

## Then use it in your components

```tsx
function MyComponent() {
  const value = useHook((state) => state.value)
  return <div>{value}</div>
}
```

## Features

- ✅ Feature one — what it does in one sentence
- ⚡️ Feature two — what it does in one sentence
- 🛠️ Feature three — what it does in one sentence
- 🔑 Feature four — what it does in one sentence
- 📦 Feature five — what it does in one sentence

## API

### `functionName(options)`

Short description.

| Parameter | Type | Default | Description |
|---|---|---|---|
| `option1` | `string` | `''` | What it controls |
| `option2` | `boolean` | `false` | What it controls |

**Returns:** `Promise<Result>` — description.

```ts
const result = await functionName({ option1: 'value' })
```

## TypeScript usage

If the library has strong TypeScript support, add a short note and example:

```ts
import { functionName, type OptionsType, type ResultType } from 'PACKAGE'
```

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).

## License

[MIT](LICENSE)
```

---

## Template (rich style, tRPC-inspired)

```markdown
<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="URL_DARK" />
    <img alt="PACKAGE" src="URL_LIGHT" />
  </picture>

  <h1>PACKAGE-NAME</h1>
  <h3>One-line description of what it does.</h3>

  [![Build](BADGE)](LINK)
  [![Version](BADGE)](LINK)
  [![License](BADGE)](LICENSE)
  [![Discord](BADGE)](DISCORD_LINK)
</div>

## Intro

Short intro paragraph. What problem it solves. Key design decision that makes it unique.

### Features

- ✅ Feature one
- 🧙 Feature two
- ⚡️ Feature three
- 🍃 Feature four (e.g., "zero deps")
- 🔋 Feature five (e.g., "batteries included")
- ⚡️ Feature six

## Quickstart

```bash
# npm
npm install PACKAGE

# yarn
yarn add PACKAGE

# pnpm
pnpm add PACKAGE

# bun
bun add PACKAGE
```

## Documentation

Visit [DOCS_URL](DOCS_URL) to view the full documentation.

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=OWNER/REPO&type=Date)](https://star-history.com/#OWNER/REPO)

## License

[MIT](LICENSE)
```

---

## Key rules for library READMEs

1. **Install command in the first screenful.** The #1 thing a developer needs.
2. **Working example before feature list.** Show, then tell.
3. **TypeScript types are a feature.** If the library is typed, say so explicitly.
4. **Bundle size matters.** If under 5kB gzipped, say it. Use bundlejs.com badge.
5. **Zero deps is a selling point.** If `dependencies: {}`, say "zero dependencies".
6. **Peer deps are requirements.** List them in the install section.
7. **Framework compatibility.** State which frameworks it works with (React, Vue, Svelte, vanilla).
