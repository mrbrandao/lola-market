# How to Create Your Own Marketplace

A guide for creating custom Lola module marketplaces for teams,
organizations, or communities.

## What is a Marketplace?

A marketplace is a curated catalog of Lola modules that users
can discover and install without manually finding repository
URLs. It's a YAML file hosted anywhere (GitHub, GitLab, your
own server) that Lola can fetch and cache locally.

## Why Create Your Own Marketplace?

- **Team/Organization**: Share internal AI skills across your
  team
- **Community**: Curate modules for a specific domain (DevOps,
  Data Science, etc.)
- **Personal**: Maintain your own collection of favorite modules

## Quick Start

### 1. Create the YAML File

Create `marketplace.yml`:

```yaml
name: "My Marketplace"
description: "Curated collection of AI skills"
version: "1.0.0"

modules:
  - name: "module-name"
    description: "Brief module description"
    version: "1.0.0"
    repository: "https://github.com/user/module"
    tags:
      - "tag1"
      - "tag2"
```

### 2. Host the File

**Option 1: GitHub** (Recommended)

```bash
git init
git add marketplace.yml
git commit -m "feat: initial marketplace"
git remote add origin https://github.com/you/marketplace
git push -u origin main
```

Your marketplace URL will be:
`https://raw.githubusercontent.com/you/marketplace/main/marketplace.yml`

**Option 2: GitLab, Bitbucket, or any HTTP server**

Host the YAML file anywhere it's publicly accessible via HTTPS.

### 3. Test the Marketplace

```bash
# Register your marketplace locally
lola market add my-market https://raw.githubusercontent.com/you/marketplace/main/marketplace.yml

# Test searching
lola mod search <keyword>

# Verify it appears
lola market ls
```

## Marketplace YAML Format

### Required Fields

```yaml
name: "Marketplace Display Name"
description: "What this marketplace provides"
version: "1.0.0"
```

- **name**: Display name shown in `lola market ls`
- **description**: Brief description of marketplace purpose
- **version**: Marketplace schema version (use "1.0.0")

### Module Entries

```yaml
modules:
  - name: "module-name"
    description: "Brief one-line description"
    version: "1.0.0"
    repository: "https://github.com/user/repo"
    tags:
      - "tag1"
      - "tag2"
```

**Required module fields:**
- **name**: Module identifier (must match repository directory
  name)
- **description**: Brief description shown in search results
- **version**: Module version (semantic versioning)
- **repository**: Git URL, zip/tar URL, or local path

**Optional module fields:**
- **tags**: Keywords for search (array of strings)

### Example Marketplace

```yaml
name: "DevOps Toolkit"
description: "Essential AI skills for DevOps engineers"
version: "1.0.0"

modules:
  - name: "kubectl-helper"
    description: "Kubernetes cluster management assistant"
    version: "1.2.0"
    repository: "https://github.com/team/kubectl-helper"
    tags:
      - "kubernetes"
      - "k8s"
      - "devops"

  - name: "terraform-guide"
    description: "Infrastructure as Code best practices"
    version: "2.0.1"
    repository: "https://github.com/team/terraform-guide"
    tags:
      - "terraform"
      - "iac"
      - "devops"

  - name: "docker-workflow"
    description: "Container development workflows"
    version: "1.5.0"
    repository: "https://github.com/team/docker-workflow"
    tags:
      - "docker"
      - "containers"
      - "devops"
```

## Best Practices

### 1. Clear Naming

- Use descriptive marketplace names
- Keep module names lowercase with hyphens
- Make descriptions concise but informative (under 80 chars)

### 2. Version Management

- Follow semantic versioning for both marketplace and modules
- Update module versions when the source changes
- Keep marketplace version at "1.0.0" unless schema changes

### 3. Organization

- Group related modules together
- Use consistent tagging across similar modules
- Keep the YAML file well-formatted and readable

### 4. Maintenance

- Regularly verify module repositories are accessible
- Update module versions when upstream changes
- Remove deprecated or unmaintained modules

### 5. Documentation

Add a README to your marketplace repository explaining:
- What modules are included
- Who the target audience is
- How to register and use the marketplace
- How to contribute new modules

## Publishing Your Marketplace

### 1. Create a Repository

```bash
git init
git add marketplace.yml README.md
git commit -m "feat: initial marketplace"
git remote add origin https://github.com/you/marketplace
git push -u origin main
```

### 2. Document Usage

Add installation instructions to your README:

```markdown
# My Marketplace

## Installation

```bash
lola market add my-market https://raw.githubusercontent.com/you/marketplace/main/marketplace.yml
```

## Usage

```bash
# Search for modules
lola mod search <keyword>

# Install a module
lola install <module-name>
```
```

### 3. Share with Users

Share your marketplace URL with your team, community, or
organization:

```bash
lola market add team-skills https://raw.githubusercontent.com/you/marketplace/main/marketplace.yml
```

## Managing Your Marketplace

### Adding Modules

1. Edit `marketplace.yml`
2. Add new module entry with all required fields
3. Commit and push changes
4. Users run `lola market update <name>` to refresh

### Updating Modules

1. Update the `version` field for changed modules
2. Commit and push
3. Users update marketplace cache to see changes

### Removing Modules

1. Remove the module entry from `marketplace.yml`
2. Commit and push
3. Note: This doesn't uninstall from users' systems

## Private Marketplaces

For internal team use, you can host marketplaces on:

- Private GitHub/GitLab repositories (requires auth)
- Internal HTTP servers
- Shared network drives (file:// URLs)

Users will need appropriate access to fetch the YAML file.

## Resources

- **[Lola Documentation](https://github.com/RedHatProductSecurity/lola)**:
  Official Lola docs
- **[General Marketplace](../modules-catalog.md)**: See the
  official marketplace for examples
- **[Marketplace YAML Format](https://github.com/RedHatProductSecurity/lola#marketplace-yaml-format)**:
  Detailed format reference

## Examples

- **[Lola General Marketplace](https://github.com/RedHatProductSecurity/lola-market)**:
  Official curated marketplace
- Create team-specific marketplaces for your organization
- Build domain-specific collections (Data Science, Web Dev,
  etc.)

## Questions?

For questions about creating marketplaces, open an issue on the
[Lola repository](https://github.com/RedHatProductSecurity/lola/issues).

---

*Happy marketplace building!* 📦
