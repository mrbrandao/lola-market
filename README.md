# Lola Marketplace

**Your one-stop shop for awesome AI skills! 🚀**

Welcome to the Lola Marketplace - a curated, community-driven
catalog of portable AI skills and commands that work across
multiple AI assistants. Think of it as the "awesome modules"
list for AI superpowers!

## What is This?

Ever wish your AI assistant could do more? Want to share your
clever prompts with the world? You're in the right place!

The Lola Marketplace is where the Lola community shares reusable
skills, commands, and agents that work across Claude Code, Cursor,
Gemini CLI, and OpenCode. Write once, use everywhere - no more
copy-pasting the same prompts into different tools!

Powered by [Lola][lola] - the AI Skills Package Manager that
makes your AI context portable.

## Prerequisites

First, install Lola if you haven't already:

```bash
# With uv (recommended)
uv tool install git+https://github.com/RedHatProductSecurity/lola

# Or clone and install locally
git clone https://github.com/RedHatProductSecurity/lola
cd lola
uv tool install .
```

See the [official Lola documentation][lola-install] for more
installation options.

## Quick Start

Register this marketplace with Lola, then search and install
modules:

```bash
# Register the marketplace
lola market add general https://raw.githubusercontent.com/mrbrandao/lola-market/main/general-market.yml

# List registered marketplaces
lola market ls

# Search for modules
lola mod search workflow

# Install a module
lola install lola-manager -a claude-code
```

## Current Modules

Here are the modules we currently have. We're working hard to
grow this collection with more awesome modules!

**📚 [View Full Module Catalog](docs/modules-catalog.md)**

- **lola-manager** - Build Lola modules with workflow guidance
- **chef-buddy** - Lazy context loading demonstration

Want your module listed here? It's easy! Read our
[Contributing](#contributing) section to learn how.

## Documentation

Want to learn more? We've got guides for everything:

- **[How to Create Lola Modules][create-modules]** - Best
  practices for creating Lola modules
- **[How to Create Your Own Marketplace][create-marketplace]** -
  Guide for creating a custom marketplace

## Contributing

Got a cool module to share? We'd love to have it! 🎉

Adding your module is easy:

1. **Add to marketplace**: Edit `general-market.yml` and add
   your module entry
2. **Update catalog**: Add your module to
   `docs/modules-catalog.md`
3. **Submit PR**: Send us a pull request with your changes

See [CONTRIBUTING.md](CONTRIBUTING.md) for detailed guidelines.
Whether you've built a productivity booster, a code quality
checker, or a fun demo, the community wants to see it!

## Resources

- **[Lola on GitHub][lola]** - Main Lola repository
- **[Lola Documentation][lola-docs]** - Full Lola docs and CLI
  reference

## Author

- **Igor Brandao** ([@mrbrandao](https://github.com/mrbrandao))

---

*Happy coding! May your AI assistant always know exactly what*
*you need.* ✨

[lola]: https://github.com/RedHatProductSecurity/lola
[lola-docs]: https://github.com/RedHatProductSecurity/lola#readme
[lola-install]: https://github.com/RedHatProductSecurity/lola#installation
[create-modules]: docs/howto-create-modules.md
[create-marketplace]: docs/howto-create-marketplace.md
