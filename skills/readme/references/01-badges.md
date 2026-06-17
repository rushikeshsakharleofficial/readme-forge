# Badge Reference

All shields.io badges. Use only badges for things that exist in the project.

---

## Style Variants

### for-the-badge (rich/dark style)
```markdown
![License](https://img.shields.io/badge/license-MIT-000000?style=for-the-badge&labelColor=000000&color=A78BFA)
![Version](https://img.shields.io/npm/v/PACKAGE?style=for-the-badge&labelColor=000000&color=22D3EE)
![Build](https://img.shields.io/github/actions/workflow/status/OWNER/REPO/ci.yml?style=for-the-badge&labelColor=000000)
```

### flat (minimal style)
```markdown
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![npm version](https://img.shields.io/npm/v/PACKAGE)](https://www.npmjs.com/package/PACKAGE)
[![Build Status](https://img.shields.io/github/actions/workflow/status/OWNER/REPO/ci.yml?branch=main)](https://github.com/OWNER/REPO/actions)
```

### flat-square (zustand/vite style — all black)
```markdown
[![Build Status](https://img.shields.io/github/actions/workflow/status/OWNER/REPO/test.yml?branch=main&style=flat&colorA=000000&colorB=000000)](https://github.com/OWNER/REPO/actions)
[![Version](https://img.shields.io/npm/v/PACKAGE?style=flat&colorA=000000&colorB=000000)](https://www.npmjs.com/package/PACKAGE)
[![Downloads](https://img.shields.io/npm/dt/PACKAGE.svg?style=flat&colorA=000000&colorB=000000)](https://www.npmjs.com/package/PACKAGE)
```

---

## Badge Catalog

### Version / Publishing

| What | Badge | When to use |
|---|---|---|
| npm version | `https://img.shields.io/npm/v/PACKAGE` | package.json with no `"private": true` |
| PyPI version | `https://img.shields.io/pypi/v/PACKAGE` | pyproject.toml with public PyPI |
| Crates.io | `https://img.shields.io/crates/v/CRATE` | Cargo.toml |
| GitHub release | `https://img.shields.io/github/v/release/OWNER/REPO` | any repo with releases |

### Downloads

| What | Badge | When to use |
|---|---|---|
| npm downloads/month | `https://img.shields.io/npm/dm/PACKAGE` | public npm package |
| npm total downloads | `https://img.shields.io/npm/dt/PACKAGE` | public npm package |
| PyPI downloads | `https://img.shields.io/pypi/dm/PACKAGE` | public PyPI package |

### CI / Quality

| What | Badge | When to use |
|---|---|---|
| GitHub Actions | `https://img.shields.io/github/actions/workflow/status/OWNER/REPO/ci.yml` | `.github/workflows/ci.yml` exists |
| Codecov | `https://codecov.io/gh/OWNER/REPO/branch/main/graph/badge.svg` | codecov integration |
| Bundle size | `https://img.shields.io/badge/dynamic/json?url=https://deno.bundlejs.com/?q=PACKAGE&query=$.size.uncompressedSize&label=bundle%20size` | JS library |

### License

| License | Badge |
|---|---|
| MIT | `https://img.shields.io/badge/License-MIT-yellow.svg` |
| Apache 2.0 | `https://img.shields.io/badge/License-Apache_2.0-blue.svg` |
| GPL v3 | `https://img.shields.io/badge/License-GPLv3-blue.svg` |
| BSD 3 | `https://img.shields.io/badge/License-BSD_3--Clause-blue.svg` |
| From file | `https://img.shields.io/github/license/OWNER/REPO` |

### Community

| What | Badge | When to use |
|---|---|---|
| GitHub stars | `https://img.shields.io/github/stars/OWNER/REPO?style=for-the-badge` | always |
| GitHub forks | `https://img.shields.io/github/forks/OWNER/REPO` | forks exist |
| Discord | `https://img.shields.io/discord/SERVER_ID?label=discord&logo=discord` | Discord server exists |
| Twitter/X | `https://img.shields.io/twitter/follow/HANDLE?style=social` | Twitter presence |

### Language / Stack

| What | Badge |
|---|---|
| TypeScript | `https://img.shields.io/badge/TypeScript-007ACC?style=flat-square&logo=typescript&logoColor=white` |
| Rust | `https://img.shields.io/badge/Rust-000000?style=flat-square&logo=rust&logoColor=white` |
| Python | `https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white` |
| Go | `https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white` |
| Next.js | `https://img.shields.io/badge/Next.js-000000?style=flat-square&logo=nextdotjs&logoColor=white` |
| React | `https://img.shields.io/badge/React-20232A?style=flat-square&logo=react&logoColor=61DAFB` |

### Plugin-specific (for Claude Code plugins)

```markdown
![Claude Code Plugin](https://img.shields.io/badge/Claude_Code-Plugin-000000?style=for-the-badge&labelColor=000000&color=A78BFA)
```

---

## Typing SVG Hero Tagline (rich style only)

```markdown
<a href="https://readme-typing-svg.demolab.com/?font=JetBrains+Mono&weight=600&size=22&duration=2400&pause=600&color=A78BFA&center=true&vCenter=true&width=720&height=44&lines=Line+one.;Line+two.;Line+three.">
  <img src="https://readme-typing-svg.demolab.com/?font=JetBrains+Mono&weight=600&size=22&duration=2400&pause=600&color=A78BFA&center=true&vCenter=true&width=720&height=44&lines=Line+one.;Line+two.;Line+three." alt="Typing tagline" />
</a>
```

Replace `lines=` with URL-encoded short phrases (use `+` for spaces, `%2C` for commas). Max 4 lines.

## Capsule Render Dividers (rich style only)

Top wave:
```markdown
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:000000,50:A78BFA,100:22D3EE&height=4&section=header" width="100%" />
```

Bottom wave:
```markdown
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:22D3EE,50:A78BFA,100:000000&height=4&section=footer" width="100%" />
```

## Star History Chart

```markdown
<a href="https://star-history.com/#OWNER/REPO">
  <img src="https://api.star-history.com/svg?repos=OWNER/REPO&type=Date" alt="Star History Chart" width="600" />
</a>
```

Use for any public repo with 50+ stars (or any stars at all if the user wants it).

## Contributors Grid

```markdown
<a href="https://github.com/OWNER/REPO/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=OWNER/REPO" />
</a>
```
