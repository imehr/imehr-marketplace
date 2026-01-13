# Skills Marketplace

Professional skills for Claude Code covering deployment, infrastructure, and development workflows.

## Installation

### Add Marketplace

```bash
/plugin marketplace add imehr/imehr-marketplace
```

### Install Skills Plugin

```bash
/plugin install imehr-skills@imehr-skills-marketplace
```

## Available Skills

### Professional Skills Plugin (imehr-skills)

**Repository:** [github.com/imehr/skills](https://github.com/imehr/skills)

Battle-tested skills for professional development workflows:

#### Learning Skills

- **learner-tools** - Self-improving metacognitive recipe tools
  - Decision Historian: Learn context-aware decisions
  - Style Learner: Learn personal writing voice
  - Meta-Recipe Tuner: Learn pipeline performance
  - Knowledge Compressor: Learn extraction rules
  - Production-ready: 44 tests, 100% passing

#### Deployment Skills

- **telegram-integration** - Telegram bot and Mini App integration using Telegraf
  - Bot development with commands, AI, interactive UI
  - Mini App integration with security validation
  - Environment-specific patterns (local/production)
  - Platform deployment (Railway, Vercel, serverless)
  - Diagnostic router for quick troubleshooting

- **railway** - Railway.com deployment and management
  - Next.js + PostgreSQL support
  - Verification safeguards
  - Complete CLI reference
  - Tested with 3 pressure scenarios

### Book Writer Plugin (book-writer)

**Repository:** [github.com/imehr/book-writer-plugin](https://github.com/imehr/book-writer-plugin)

Complete AI-powered book writing automation system:

#### Features

- **35+ Specialized Agents** - Content creation, QA, production, orchestration
- **Multi-Format Export** - EPUB, HTML, PDF via Pandoc
- **Quality Pipelines** - Automated review, technical validation, copyediting
- **GitHub Releases** - Automated release creation and distribution
- **Self-Updating Books** - Monitor sources and apply updates automatically
- **Research Integration** - Ingest and synthesize research materials
- **Multi-Agent Orchestration** - Coordinate complex workflows

#### Commands (all prefixed with `book-writer:`)

```bash
/book-writer:export-book [book] epub html pdf    # Export to formats
/book-writer:audit-book                          # Check book status
/book-writer:start-book-project                  # Initialize new book
/book-writer:review-and-promote [file]           # Quality review & promotion
/book-writer:publish-release [book]              # Create GitHub release
# ... and 22 more commands
```

#### Installation

```bash
/plugin install book-writer@imehr-marketplace
```

## Features

All skills in this marketplace are:
- ✅ **TDD-tested** with RED-GREEN-REFACTOR methodology
- ✅ **Pressure-tested** with multiple scenarios
- ✅ **Token-efficient** (<1000 words per main skill)
- ✅ **Verified** with safeguards against false positives
- ✅ **Documented** with comprehensive references

## Quality Standards

Each skill must pass:
- 3+ pressure scenarios (time, sunk cost, authority, exhaustion)
- False-positive prevention tests
- Verification safeguards (for platform-specific skills)
- Word count limits (<1000 words main, unlimited supporting)

## Plugin Details

### imehr-skills

**Categories:**
- learning
- deployment
- infrastructure
- development
- workflows

**Current Skills:**
- Learner Tools: Self-improving recipes (v1.0.0)
- Telegram bot and Mini App integration (v1.0.0)
- Railway deployment (v1.0.0)
- Skills/marketplace builder (v1.0.0)

**Coming Soon:**
- Vercel deployment
- AWS deployment
- PostgreSQL management
- Redis caching
- Docker workflows

### Video Explainer Plugin (video-explainer-skill)

**Repository:** [github.com/imehr/video-explainer-skill](https://github.com/imehr/video-explainer-skill)

Create multi-platform explainer videos with intelligent orchestration:

- **Multi-platform output** - YouTube, Shorts, TikTok, Instagram, LinkedIn
- **Brand × Platform × Style** - Fully customizable configuration matrix
- **Intelligent orchestrator** - Parallel background agent execution
- **Learning memory** - Improves over time based on feedback
- **Technique skills** - Hooks, narrative structures, platform optimization

**Requires:** [video_explainer](https://github.com/example/video_explainer) Python CLI

## About

This marketplace follows the same pattern as [obra/superpowers-marketplace](https://github.com/obra/superpowers-marketplace), providing a curated collection of professional-grade skills.

**Author:** Mehran Mozaffari
**License:** MIT
**Repository:** https://github.com/imehr/imehr-marketplace

## Support

- **Issues:** [GitHub Issues](https://github.com/imehr/imehr-marketplace/issues)
- **Skills Repository:** [imehr/skills](https://github.com/imehr/skills)
- **Contributions:** See [CONTRIBUTING.md](https://github.com/imehr/skills/blob/main/CONTRIBUTING.md) in the skills repository

## Version

**Current:** v1.8.0
**Last Updated:** January 2026
