# Pattern: CLI Tool

Based on: ripgrep, gh CLI, bun. Use for tools with a binary/executable as the main interface.

---

## Section Order

1. [Optional] Hero image or ASCII art
2. Badge row (CI, version, license)
3. H1 title + one-paragraph description
4. [Optional] Screenshot or demo GIF
5. Quick start (install + first command)
6. Installation (by platform/method)
7. Usage (command reference, common examples)
8. Configuration (flags, env vars, config file)
9. Building from source
10. Comparison with similar tools (if applicable)
11. Contributing
12. License

---

## Template (ripgrep-style — Rust CLI, plain)

```markdown
# BINARY-NAME — keyword description

Short paragraph. What the tool does. What makes it faster/better than alternatives. State supported platforms.

[![Build](https://img.shields.io/github/actions/workflow/status/OWNER/REPO/ci.yml?style=flat)](https://github.com/OWNER/REPO/actions)
[![Version](https://img.shields.io/crates/v/CRATE)](https://crates.io/crates/CRATE)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)

### Quick links
- [Installation](#installation)
- [Usage Guide](GUIDE.md)
- [FAQ](FAQ.md)

### Quick examples

```bash
# Search for pattern in current directory
BINARY "pattern"

# Recursive search with file type filter
BINARY --type ts "functionName"

# Case-insensitive, whole word
BINARY -i -w "ClassName"
```

## Installation

**macOS:**
```bash
brew install PACKAGE
```

**Linux (Debian/Ubuntu):**
```bash
sudo apt install PACKAGE
```

**Rust (all platforms):**
```bash
cargo install BINARY-NAME
```

**Download binary:** [Releases page](https://github.com/OWNER/REPO/releases/latest)

## Usage

```
BINARY [OPTIONS] PATTERN [PATH...]
```

### Common flags

| Flag | Short | Description |
|---|---|---|
| `--type <LANG>` | `-t` | Filter by file type (`ts`, `py`, `go`, etc.) |
| `--ignore-case` | `-i` | Case-insensitive search |
| `--word-regexp` | `-w` | Match whole words only |
| `--no-heading` | | Disable filename headers |
| `--hidden` | | Search hidden files and directories |
| `--max-depth <N>` | | Limit directory depth |
| `--count` | `-c` | Show match count per file |

### Examples

```bash
# Find all TODO comments
BINARY "TODO" --type ts

# Search with context lines
BINARY -C 3 "functionName" src/

# Glob pattern
BINARY "pattern" --glob "*.{ts,tsx}"

# Invert match
BINARY -v "pattern"
```

## Building from source

**Requirements:** [list build requirements]

```bash
git clone https://github.com/OWNER/REPO.git
cd REPO
cargo build --release
./target/release/BINARY --help
```

## Comparison

| Tool | Speed | Respects .gitignore | Unicode | Install |
|---|---|---|---|---|
| **BINARY** | 🟢 fastest | ✅ | ✅ | cargo / brew |
| alternative1 | 🟡 fast | ✅ | partial | brew |
| alternative2 | 🔴 slow | ❌ | ✅ | brew |

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md). Run tests with: `cargo test`.

## License

MIT — see [LICENSE](LICENSE).
```

---

## Template (gh-style — multi-platform, Go CLI)

```markdown
# TOOL-NAME

`BINARY` is DESCRIPTION. It brings [concept] to the terminal [so that / enabling] [benefit].

![Demo screenshot](docs/screenshot.png)

TOOL-NAME is supported on macOS, Windows, and Linux.

## Documentation

For [installation options see below](#installation), for usage see the [manual](DOCS_URL).

## Installation

### macOS

- [Homebrew](docs/install_macos.md#homebrew): `brew install BINARY`
- [Precompiled binaries](https://github.com/OWNER/REPO/releases/latest)

### Linux & Unix

- [Debian, Ubuntu](docs/install_linux.md#debian): `sudo apt install BINARY`
- [Fedora, RHEL](docs/install_linux.md#rpm): `sudo dnf install BINARY`
- [Precompiled binaries](https://github.com/OWNER/REPO/releases/latest)

### Windows

- WinGet: `winget install PACKAGE`
- [Precompiled binaries](https://github.com/OWNER/REPO/releases/latest)

### Build from source

```bash
git clone https://github.com/OWNER/REPO.git
cd REPO
go build -o BINARY ./cmd/BINARY
```

## Contributing

See [CONTRIBUTING.md](.github/CONTRIBUTING.md).

## License

[MIT](LICENSE)
```

---

## Key rules for CLI tool READMEs

1. **State the binary name in H1 or first paragraph.** Developers need to know what to type.
2. **Install command by platform.** Most CLI users are on macOS or Linux — split install by platform if they differ.
3. **Show `--help` output or a command table.** Developers want to see flags before installing.
4. **Demo screenshot or GIF dramatically increases stars.** If possible, capture it.
5. **Build from source is mandatory.** Power users always want this.
6. **Comparison table with alternatives.** Justify why someone would switch.
7. **Performance benchmarks if applicable.** ripgrep's benchmark tables are legendary.
