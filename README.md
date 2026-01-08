# FutureSuper Claude Code Plugin Marketplace

Official marketplace for FutureSuper Claude Code plugins.

## Installation

### For FutureSuper Team Members

**1. Add the marketplace (one-time setup):**

Launch Claude and run:
```bash
/plugin marketplace add https://raw.githubusercontent.com/futuresuper/claude-marketplace/main/.claude-plugin-marketplace.json
```

Or add to your `~/.claude/settings.json`:
```json
{
  "extraKnownMarketplaces": {
    "futuresuper": {
      "source": {
        "source": "url",
        "url": "https://raw.githubusercontent.com/futuresuper/claude-marketplace/main/.claude-plugin-marketplace.json"
      }
    }
  }
}
```

**2. Install plugins:**
```bash
/plugin install fg
```

**Note:** You must have access to the FutureSuper GitHub organization to install plugins from this marketplace.

## Available Plugins

### fg
Code review and simplification tools

**Commands:**
- `/fg:peer-review` - Comprehensive code review with quality, security, and performance analysis

**Agents:**
- `code-simplification` - Refactors complex code for clarity while preserving functionality

**Repository:** https://github.com/futuresuper/fg-claude-code-plugin

## Adding New Plugins

To add a new plugin to this marketplace:

1. Create your plugin repository
2. Edit `.claude-plugin-marketplace.json` and add your plugin entry:
```json
{
  "name": "your-plugin-name",
  "repository": "https://github.com/futuresuper/your-plugin-repo.git",
  "description": "Brief description"
}
```
3. Commit and push changes
4. Team members will automatically see the new plugin available

## Updating Plugins

To get the latest version of an installed plugin:
```bash
/plugin update fg
```

## Troubleshooting

**"Permission denied" error when installing:**
- Ensure you have access to the FutureSuper GitHub organization
- Verify you're authenticated with GitHub (`gh auth status`)

**Plugin not showing up:**
- Verify marketplace is added: `/plugin marketplace list`
- Try refreshing: `/plugin marketplace refresh`

**Command not found:**
- Check plugin is installed: `/plugin list`
- Verify plugin loaded: `/help` should show `/fg:*` commands
