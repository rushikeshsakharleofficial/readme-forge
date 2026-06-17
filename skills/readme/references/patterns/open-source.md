# Pattern: Open Source Project (General)

Fallback pattern for projects that don't clearly fit other types — scripts, configs, templates, utilities, data, infrastructure.

---

## Section Order

1. Title + short description + badges
2. What is this? (one paragraph)
3. Features or capabilities
4. Getting started / install / setup
5. Usage
6. Configuration (if any)
7. Contributing
8. License

---

## Template

```markdown
# PROJECT-NAME

Short description. What it is, what it does, who it's for. One to three sentences.

[![License](https://img.shields.io/github/license/OWNER/REPO)](LICENSE)
[![Stars](https://img.shields.io/github/stars/OWNER/REPO?style=social)](https://github.com/OWNER/REPO/stargazers)

## What is this?

One paragraph. Explain the project purpose, the problem it solves, and any important context. No marketing language.

## Features

- Feature one — what it does
- Feature two — what it does
- Feature three — what it does

## Getting Started

**Requirements:** [list prerequisites]

```bash
git clone https://github.com/OWNER/REPO.git
cd REPO
# setup command
```

## Usage

```bash
# Example usage
COMMAND argument --flag
```

Or if it's a template / config / data repo:
```
Describe how to use or copy the contents of this repo.
```

## Contributing

[Short contributing note. PR guidelines, issue templates, coding standards.]

## License

[MIT](LICENSE)
```

---

## Variations

### Script collection / toolbox
```markdown
## Scripts

| Script | Description |
|---|---|
| `scripts/setup.sh` | Initial setup |
| `scripts/deploy.sh` | Deploy to production |
| `scripts/cleanup.sh` | Clean up resources |

Run any script with:
```bash
bash scripts/SCRIPT.sh [arguments]
```
```

### Configuration / dotfiles
```markdown
## Installation

```bash
git clone https://github.com/OWNER/REPO.git ~/.dotfiles
cd ~/.dotfiles
./install.sh
```

## What's included

| File / Directory | Description |
|---|---|
| `.zshrc` | Zsh configuration |
| `.gitconfig` | Git configuration |
| `.config/nvim/` | Neovim config |
```

### Template / starter kit
```markdown
## Using this template

Click **Use this template** on GitHub, or:

```bash
gh repo create my-project --template OWNER/REPO --clone
```

Then:
1. Update `package.json` with your project details
2. Replace placeholder content
3. Delete this README section
```

### IaC / Infrastructure
```markdown
## Requirements

- Terraform >= 1.5
- AWS CLI configured
- [Other tools]

## Usage

```bash
terraform init
terraform plan -var-file="terraform.tfvars"
terraform apply
```

## Variables

| Variable | Required | Description |
|---|---|---|
| `region` | ✅ | AWS region |
| `environment` | ✅ | `dev`, `staging`, `prod` |
| `instance_type` | ❌ | EC2 instance type (default: `t3.micro`) |

## Outputs

| Output | Description |
|---|---|
| `endpoint` | Application endpoint URL |
| `instance_id` | EC2 instance ID |
```
