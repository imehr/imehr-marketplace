# Marketplace Setup and Troubleshooting

This document explains the marketplace setup, issues found, and how to use it.

## Issues Found and Fixed

### 1. Repository Visibility
**Problem:** The marketplace repository and several plugin repositories were private, making them inaccessible to Claude Code.

**Solution:** Made all repositories public:
- ✅ imehr-marketplace (marketplace)
- ✅ vet
- ✅ cc-ui-feedback
- ✅ skills (imehr-skills)
- ✅ blog-cc-framework
- ✅ book-writer-plugin
- ✅ video-explainer-skill
- ✅ create-audio-skill (created and published)
- ✅ capture-content-skill

### 2. Missing Repository
**Problem:** The `create-audio-skill` repository referenced in marketplace.json didn't exist on GitHub.

**Solution:** Created the repository and pushed all skill content including:
- SKILL.md
- scripts/ directory with TTS providers
- assets/ and references/ directories
- README.md with installation instructions

## How to Use the Marketplace

### Add the Marketplace

```bash
/plugin marketplace add imehr/imehr-marketplace
```

### Install Plugins

Install individual plugins from the marketplace:

```bash
# Install VET (Virtual Engineering Team)
/plugin install vet@imehr-marketplace

# Install skills collection
/plugin install imehr-skills@imehr-marketplace

# Install capture-content
/plugin install capture-content@imehr-marketplace

# Install create-audio
/plugin install create-audio@imehr-marketplace

# Install video-explainer
/plugin install video-explainer-skill@imehr-marketplace

# Install book-writer
/plugin install book-writer@imehr-marketplace

# Install blog-cc-framework
/plugin install blog-cc-framework@imehr-marketplace

# Install cc-ui-feedback
/plugin install cc-ui-feedback@imehr-marketplace
```

### List Available Plugins

```bash
/plugin marketplace list imehr-marketplace
```

### Update Plugins

```bash
/plugin update <plugin-name>
```

## Available Plugins

### 1. VET (Virtual Engineering Team)
- **Version:** 2.1.0
- **Description:** Senior Architect, Security Engineer, and DevOps personas
- **Keywords:** architecture, frontend, backend, security, devops, TDD

### 2. CC UI Feedback
- **Version:** 1.0.0
- **Description:** Cross-project UI feedback collection system
- **Keywords:** feedback, ui, react, bug-tracking, automation

### 3. IMehr Skills
- **Version:** 1.5.0
- **Description:** Learner Tools, Telegram integration, Railway deployment, Frontend UI
- **Keywords:** learning, telegram, railway, frontend, design-system, TDD

### 4. Blog CC Framework
- **Version:** 1.1.1
- **Description:** Static site management with AI content generation
- **Keywords:** blog, static-site, nextjs, content-management, github-pages

### 5. Book Writer
- **Version:** 3.0.0
- **Description:** AI-powered book writing automation with 35+ agents
- **Keywords:** book-writing, content-creation, epub, pdf, multi-agent

### 6. Video Explainer
- **Version:** 0.1.0
- **Description:** Multi-platform video creation (YouTube, TikTok, Instagram, LinkedIn)
- **Keywords:** video, explainer, multi-platform, storytelling, animation

### 7. Create Audio
- **Version:** 0.3.0
- **Description:** Generate audio using 13 TTS providers (Pocket TTS, MLX-Audio, ElevenLabs, Coqui)
- **Keywords:** audio, tts, voice, multilingual, voice-cloning

### 8. Capture Content
- **Version:** 1.0.0
- **Description:** Journalist-style interview to extract publishable content
- **Keywords:** content-creation, interview, social-media, writing, storytelling

## Marketplace Structure

```
imehr-marketplace/
├── .claude-plugin/
│   └── marketplace.json       # Plugin registry
├── README.md                  # Main documentation
├── MARKETPLACE-SETUP.md       # This file
├── LICENSE                    # MIT License
└── .gitignore
```

## Troubleshooting

### Marketplace Not Found
If you see "Marketplace 'imehr-marketplace' not found":
1. Verify the repository is public: `gh repo view imehr/imehr-marketplace --json isPrivate`
2. Check network connectivity
3. Try removing and re-adding:
   ```bash
   /plugin marketplace remove imehr-marketplace
   /plugin marketplace add imehr/imehr-marketplace
   ```

### Plugin Installation Fails
If a plugin fails to install:
1. Verify the plugin repository is public
2. Check the URL in marketplace.json matches the actual repository
3. Ensure the plugin has a `.claude-plugin/plugin.json` file

### Authentication Issues
For private repositories (not applicable now, but for future reference):
1. Configure git credentials: `gh auth login`
2. Use SSH URLs instead of HTTPS
3. Set up deploy keys for specific repositories

## Version History

- **v1.9.0** (2026-01-15)
  - Added capture-content skill
  - Fixed repository visibility issues
  - Created missing create-audio-skill repository

- **v1.8.0** (2026-01-13)
  - Added video-explainer-skill plugin

- **v1.7.0** (2026-01-13)
  - Added cc-ui-feedback plugin
  - Updated VET to v2.1.0

## Support

- **Issues:** https://github.com/imehr/imehr-marketplace/issues
- **Email:** mehran.mozaffari@gmail.com

## License

MIT License - See LICENSE file for details
