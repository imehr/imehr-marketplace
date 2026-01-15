# Troubleshooting imehr-marketplace

## Current Status

Your marketplace IS installed and configured correctly:
- ✅ Repository is public: https://github.com/imehr/imehr-marketplace
- ✅ Listed in `~/.claude/plugins/known_marketplaces.json`
- ✅ Cloned to `~/.claude/plugins/marketplaces/imehr-marketplace`
- ✅ JSON structure is valid
- ✅ All 9 plugins are listed
- ✅ All plugin repositories are public

## The "/plugin" Command Confusion

When you run `/plugin` by itself, it shows available `/plugin` subcommands, not marketplaces. The error message might be misleading.

## Commands to Try

### 1. List Your Installed Marketplaces
```bash
/plugin marketplace list
```

### 2. Update Your Marketplace
```bash
/plugin marketplace update imehr-marketplace
```

### 3. List Plugins in Your Marketplace
Try one of these:
```bash
/plugin marketplace show imehr-marketplace
# or
/plugin list imehr-marketplace
```

### 4. Install a Plugin from Your Marketplace
```bash
/plugin install capture-content@imehr-marketplace
```

### 5. Remove and Re-add the Marketplace (if needed)
```bash
/plugin marketplace remove imehr-marketplace
/plugin marketplace add imehr/imehr-marketplace
```

## Manual Verification

Run these commands to verify the marketplace is installed:

```bash
# Check if marketplace is in known_marketplaces.json
cat ~/.claude/plugins/known_marketplaces.json | jq '.["imehr-marketplace"]'

# Check if marketplace directory exists
ls -la ~/.claude/plugins/marketplaces/imehr-marketplace/

# Check marketplace.json is valid
cat ~/.claude/plugins/marketplaces/imehr-marketplace/.claude-plugin/marketplace.json | jq '.'

# Pull latest changes
cd ~/.claude/plugins/marketplaces/imehr-marketplace && git pull
```

## What Actually Happened

Based on investigation, your marketplace is properly installed but:

1. The `/plugin` command alone doesn't list marketplaces - it shows help
2. You need to use specific subcommands to interact with marketplaces
3. The marketplace was successfully added on 2026-01-15T22:15:47.063Z

## Testing Installation

Try installing the capture-content skill:

```bash
/plugin install capture-content@imehr-marketplace
```

If this works, your marketplace is functioning correctly!

## Alternative: Direct Installation

If marketplace commands don't work, you can install skills directly:

```bash
# Install capture-content skill directly
cd ~/.claude/skills
git clone https://github.com/imehr/capture-content-skill.git capture-content
```

Then use:
```bash
/capture-content
```

## Common Issues and Solutions

### Issue: "Marketplace not found" error
**Solution:** The marketplace IS installed. Try:
1. `/plugin marketplace list` to see all marketplaces
2. `/plugin install <plugin-name>@imehr-marketplace` to install a specific plugin
3. Restart Claude Code

### Issue: Can't see plugins from marketplace
**Solution:** Use the full format:
```bash
/plugin install <plugin-name>@imehr-marketplace
```

### Issue: Marketplace shows old version
**Solution:**
```bash
/plugin marketplace update imehr-marketplace
# or manually
cd ~/.claude/plugins/marketplaces/imehr-marketplace && git pull
```

## Available Plugins

You can install any of these:

1. `vet@imehr-marketplace` - Virtual Engineering Team (v2.1.0)
2. `cc-ui-feedback@imehr-marketplace` - UI Feedback System (v1.0.0)
3. `imehr-skills@imehr-marketplace` - Skills Collection (v1.5.0)
4. `blog-cc-framework@imehr-marketplace` - Blog Framework (v1.1.1)
5. `book-writer@imehr-marketplace` - Book Writing (v3.0.0)
6. `video-explainer-skill@imehr-marketplace` - Video Creation (v0.1.0)
7. `create-audio@imehr-marketplace` - Audio Generation (v0.3.0)
8. `capture-content@imehr-marketplace` - Content Extraction (v1.0.0)
9. `dev-log@imehr-marketplace` - Development Logging (v1.0.0)

## Next Steps

1. Try running `/plugin install capture-content@imehr-marketplace`
2. If it works, your marketplace is functional
3. If not, try the manual verification steps above
4. Check Claude Code version - ensure you're on the latest version

## Support

If issues persist:
- Check Claude Code logs
- Restart Claude Code
- Verify internet connection
- Ensure all repositories are still public

Last verified: 2026-01-16
