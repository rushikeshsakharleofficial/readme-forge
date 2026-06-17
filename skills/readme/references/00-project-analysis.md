# Project Analysis Reference

How to scan a project before writing its README. Run all reads in parallel. Never invent — only write what you find.

---

## File Scan Checklist

### Package / Manifest files

| File | Extract |
|---|---|
| `package.json` | `name`, `description`, `version`, `main`, `bin`, `exports`, `scripts`, `dependencies`, `devDependencies`, `keywords`, `repository`, `license`, `homepage`, `author`, `private` |
| `pyproject.toml` | `[project]` name, version, description, authors, keywords, dependencies, entry_points |
| `setup.py` | Name, version, description, scripts, install_requires |
| `requirements.txt` | Key package names (infer framework) |
| `Cargo.toml` | name, version, description, keywords, repository, license, `[[bin]]` entries, `[lib]` section |
| `go.mod` | module name, go version |
| `composer.json` | name, description, require |
| `pubspec.yaml` | name, description (Flutter/Dart) |
| `mix.exs` | app name, version (Elixir) |
| `.csproj` | PackageId, Version (C#/.NET) |

### Structure scan (list depth 2)

Look for these directories to classify the project:

| Directory | Signals |
|---|---|
| `src/app/` or `app/` | Next.js App Router, SvelteKit, Nuxt |
| `src/pages/` | Next.js Pages Router |
| `src/lib/` or `lib/` | Library package |
| `bin/` or `cmd/` | CLI tool (binary entry points) |
| `api/` or `routes/` | API server |
| `packages/` or `apps/` | Monorepo |
| `examples/` | Good examples to extract usage from |
| `tests/` or `spec/` or `__tests__/` | Test suite exists |
| `docs/` | External docs |
| `.claude-plugin/` | Claude Code plugin |
| `.github/workflows/` | CI/CD — enables CI badge |
| `Dockerfile` | Container deployment |
| `docker-compose.yml` | Multi-service setup |

### Config / Environment

| File | Extract |
|---|---|
| `.env.example` or `.env.sample` | Config key names (never values) |
| `config.ts` / `config.js` / `config.yaml` | Option names and types |
| `schema.ts` / `schema.json` / `zod` schemas | Config shape |
| `tailwind.config.*` | Tailwind v3 vs v4, plugins |
| `next.config.*` | Next.js present |
| `vite.config.*` | Vite present |

### License detection (check in this order)

1. `LICENSE` file (root)
2. `LICENCE` file (British spelling)
3. `COPYING` file (GPL)
4. `NOTICE` file
5. `package.json` `license` field (SPDX identifier)
6. `pyproject.toml` `[project] license`
7. `Cargo.toml` `[package] license`
8. Source file SPDX headers (`// SPDX-License-Identifier: MIT`)

**If license found:** mention clearly and link to file.
**If metadata says license but no file exists:** note metadata, flag for maintainer.
**If nothing found:** omit the license section entirely, add Maintainer TODO.
**Never guess or assign a license that isn't there.**

### Copyright year detection

```bash
git log --reverse --format="%ad" --date=format:"%Y" | head -1
```
If multi-year: use range `FIRST_YEAR–CURRENT_YEAR`.

### Author detection

In priority order:
1. `package.json` → `author` field
2. `pyproject.toml` → `[project] authors`
3. `Cargo.toml` → `[package] authors`
4. `git log --reverse --format="%an" | head -1`
5. `git config user.name`

---

## Package Manager Detection

From lockfiles (check root):

| Lockfile | Package manager |
|---|---|
| `bun.lockb` | bun |
| `pnpm-lock.yaml` | pnpm |
| `yarn.lock` | yarn |
| `package-lock.json` | npm |
| `uv.lock` | uv (Python) |
| `poetry.lock` | poetry (Python) |
| `Gemfile.lock` | bundler (Ruby) |

If multiple lockfiles (monorepo): list all, lead with the root one.

---

## Framework Detection Matrix

### JavaScript / TypeScript

| Dependency or file | Framework |
|---|---|
| `next` in deps | Next.js |
| `react-scripts` in deps | Create React App |
| `@sveltejs/kit` in deps | SvelteKit |
| `nuxt` in deps | Nuxt |
| `@remix-run/` in deps | Remix |
| `astro` in deps | Astro |
| `vite` in devDeps | Vite (build tool) |
| `express` in deps | Express.js |
| `fastify` in deps | Fastify |
| `hono` in deps | Hono |
| `@trpc/server` in deps | tRPC |
| `drizzle-orm` or `prisma` in deps | ORM — database app |
| `framer-motion` in deps | Has animation |
| `three` in deps | Three.js / 3D |
| `@react-three/fiber` in deps | R3F |

### Python

| Package or file | Framework |
|---|---|
| `fastapi` | FastAPI |
| `django` | Django |
| `flask` | Flask |
| `starlette` | Starlette |
| `click` | CLI tool |
| `typer` | CLI tool |
| `torch` or `tensorflow` | ML project |
| `pandas` | Data project |

### Rust

| Signal | Type |
|---|---|
| `[[bin]]` in Cargo.toml | CLI tool |
| `[lib]` in Cargo.toml, no `[[bin]]` | Library crate |
| Both | Both (library with example binary) |
| `clap` dependency | CLI with arg parsing |
| `axum` or `actix-web` dependency | HTTP server |

### Go

| Signal | Type |
|---|---|
| `package main` in root | CLI tool |
| `package NAME` (not main) | Library |
| `github.com/gin-gonic/gin` import | Gin HTTP server |
| `github.com/labstack/echo` import | Echo HTTP server |
| `github.com/spf13/cobra` import | CLI tool |

---

## Content Extraction Rules

### Usage examples — where to find them

1. `examples/` directory — look for `*.ts`, `*.py`, `*.go`, `*.rs` files
2. `README.md` existing content — preserve working examples
3. Test files — `*.test.ts`, `*_test.go`, `test_*.py` — extract simple usage patterns
4. Entry point (`src/index.ts`, `main.go`, `main.py`) — look for exported functions

### CLI flags and subcommands

1. `--help` output: `BINARY --help` or from `src/cli.ts` ArgParse/Commander/Clap definitions
2. `bin/` scripts
3. `package.json` scripts (for npm run usage)
4. Cobra/Click/Clap command definitions in source

### API routes

1. `src/app/api/` (Next.js App Router)
2. `src/pages/api/` (Next.js Pages Router)
3. `routes/` or `api/` directories
4. `openapi.yaml` or `swagger.json`
5. Router definitions in Express/Fastify/Gin/Axum

### Maintainer TODOs

When a fact is important but unverifiable, add to `Maintainer TODOs` section:

```markdown
## Maintainer TODOs

- [ ] Add demo GIF or screenshot to `docs/` and embed in `## Demo` section
- [ ] Set GitHub repo Topics: `readme`, `cli`, `documentation`
- [ ] Add social preview image (1280×640px) in GitHub Settings → Social preview
- [ ] Confirm production deployment URL for the ## Demo section
```

Remove this section entirely if there are no TODOs.
