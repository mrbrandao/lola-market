# Contributing to Lola Marketplace

**Write your AI skills once, use them everywhere.**

Thank you for your interest in contributing to the Lola
Marketplace! This document provides guidelines for adding your
modules to the marketplace. Whether you're sharing a useful
skill, a clever command, or a fun demo, we appreciate your help
in making AI assistants better for everyone.

## Prerequisites

Before you begin, ensure you have:

- **Git**: Version control system
- **Your Lola Module**: A working module following Lola structure
- **(Optional) AI coding assistant**: Tools like Claude Code,
  Cursor, or GitHub Copilot

## Getting Started

### 1. Fork and Clone

1. Fork the repository by clicking the "Fork" button on
   https://github.com/RedHatProductSecurity/lola-market
2. Clone your fork:

```bash
git clone https://github.com/YOUR-USERNAME/lola-market.git
cd lola-market
```

### 2. Create a Feature Branch

```bash
git checkout -b add-your-module-name
```

Use descriptive names like `add-git-workflow` or
`add-code-review`.

## Adding Your Module

### 1. Add Module to Marketplace YAML

Edit `general-market.yml` and add your module entry:

```yaml
  - name: "your-module-name"
    description: "Brief one-line description"
    version: "1.0.0"
    repository: "https://github.com/you/your-module"
    tags:
      - "tag1"
      - "tag2"
```

**Guidelines:**
- **name**: Use lowercase with hyphens (e.g., `git-workflow`)
- **description**: One sentence, under 80 characters
- **version**: Follow semantic versioning (MAJOR.MINOR.PATCH)
- **repository**: Must be publicly accessible
- **tags**: 2-5 relevant keywords

### 2. Update the Module Catalog

Edit `docs/modules-catalog.md` and add your module to the
appropriate category. Once merged, your module will be
searchable when users add this marketplace and can be installed
directly via `lola mod search` and `lola install`.

## Submitting a Pull Request

### 1. Commit Your Changes

We use [Conventional Commits](https://conventionalcommits.org/):

```bash
git add general-market.yml docs/modules-catalog.md
git commit -m "docs: add your-module to marketplace"
```

### 2. Push to Your Fork

```bash
git push origin add-your-module-name
```

### 3. Open the Pull Request

1. Go to https://github.com/RedHatProductSecurity/lola-market
2. Click "Compare & pull request"
3. Describe what your module does and why it's useful
4. Link to your module repository

### 4. Wait for Review

Maintainers will review your submission. We check:
- YAML is valid and properly formatted
- Repository is accessible
- Module follows Lola standards
- Description is clear and accurate
- No duplicate entries

### 5. Respond to Feedback

If changes are requested, update your code and push - the PR
updates automatically!

## Module Quality Guidelines

To be accepted into the marketplace, your module should:

1. **Follow Lola Structure**: Have proper `skills/`,
   `commands/`, or `agents/` directories
2. **Include Documentation**: Have a clear README explaining
   what it does
3. **Use Proper Frontmatter**: Include `name` and `description`
   in SKILL.md
4. **Be Functional**: Actually work when installed
5. **Be Maintained**: Have at least initial version and commits

## AI-Assisted Contributions

We welcome contributions made with AI coding assistants! As a
marketplace for AI skills, we embrace AI-assisted development
while maintaining quality through transparency.

### How to Disclose AI Usage

**Option 1: Git commit signature** (Recommended)

Configure git to add "Assisted-by" to your commits:

```bash
git config user.assistedby "Claude Code"
```

**Option 2: Commit message**

Simply mention AI assistance in your commit message:

```bash
git commit -m "docs: add module (AI-assisted)"
```

### Quality Standards

Whether AI-assisted or not, all contributions must:
- Be reviewed and understood by you
- Follow the guidelines in this document
- Have valid YAML syntax
- Include accurate descriptions

## Resources

- **[Lola Documentation](https://github.com/RedHatProductSecurity/lola)**:
  Main Lola repository
- **[How to Create Lola Modules](docs/howto-create-modules.md)**:
  Module creation guide
- **[Marketplace Catalog](docs/modules-catalog.md)**: See
  existing modules for examples

## Questions?

If you have questions about contributing, please open an issue
on GitHub. We're happy to help!
