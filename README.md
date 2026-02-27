# Obsidian Clipper Template Creator

> **AI Agent skill for creating custom templates for the [Obsidian Web Clipper](https://help.obsidian.md/web-clipper)**

This skill enables AI agents (Claude Code, Cursor, Gemini CLI, etc.) to help you create importable JSON templates for the Obsidian Web Clipper. It guides the agent through analyzing web pages, mapping to your Obsidian schema, and generating valid template configurations.

## Features

- 🎯 Analyzes web pages to extract Schema.org metadata, meta tags, and CSS selectors
- 📋 Maps web content to your existing Obsidian Base schemas
- 🔧 Generates valid JSON templates following Obsidian Web Clipper schema
- ✅ Validates variables and provides reference documentation
- 📐 Produces templates using Clipper 1.0 template logic (conditionals, loops, fallbacks) so optional sections and defaults work correctly; logic aligns with the Clipper’s built-in template validation
- 📦 Includes example templates (recipes, general clipping)

## Compatibility

This skill targets **Obsidian Web Clipper 1.0.0** and supports the template logic (conditionals, loops, variable assignment) and template validation introduced in 1.0.0. 
It follows the universal **SKILL.md** format and works with any AI coding assistant that supports agentic skills.

| Tool | Type | Compatibility | Installation Path |
| ------ | ------ | --------------- | ------------------ |
| **Claude Code** | CLI | ✅ Full | `.claude/skills/` or `.agent/skills/` |
| **Cursor** | IDE | ✅ Full | `.cursor/skills/` or project root |
| **Gemini CLI** | CLI | ✅ Full | `.gemini/skills/` or `.agent/skills/` |
| **Codex CLI** | CLI | ✅ Full | `.codex/skills/` or `.agent/skills/` |
| **Antigravity IDE** | IDE | ✅ Full | `.agent/skills/` |
| **OpenCode** | CLI | ✅ Full | `.opencode/skills/` or `.claude/skills/` |

## Installation

1. Download or clone this repository
2. Copy the `skills/obsidian-clipper-template-creator/` folder to your agent's skills directory

Most tools auto-discover skills in `.agent/skills/`.

## Configuration

### Important: Template Paths Setup

This skill contains hardcoded references to `Bases/` as the default path for your Obsidian Base schemas. **You must edit the skill files to configure your vault path before using the skill.**

#### Files to Edit

1. **`SKILL.md`** - Main skill file with workflow instructions
2. **`references/bases-workflow.md`** - Contains path references in the workflow documentation

#### Setup Steps

1. **Edit both SKILL.md and references/bases-workflow.md**
2. **Replace all instances of `Bases/`** with your actual Obsidian bases directory path

The skill expects your Base schemas to be in `*.base` files within your configured directory.

## Usage

Once installed, trigger the skill by asking your AI agent to create an Obsidian Clipper template:

```text
"Create an Obsidian Web Clipper template for YouTube videos"
"Help me make a clipper template for recipe sites"
"I want to clip articles to Obsidian"
```

The agent will:

1. Identify your intent and check for existing Base schemas
2. Ask for a sample URL to analyze (if not provided)
3. Extract metadata and structure from the page
4. Generate a valid JSON template you can import into Obsidian

## What's Included

```text
skills/obsidian-clipper-template-creator/
├── SKILL.md                      # Main skill definition
├── assets/
│   ├── clipping-template.json    # Example: General clipping
│   └── recipe-template.json      # Example: Recipe sites
└── references/
    ├── analysis-workflow.md      # Page analysis techniques
    ├── bases-workflow.md         # Mapping to Obsidian Bases
    ├── filters.md                # Available formatting filters
    ├── json-schema.md            # Template JSON structure
    ├── logic.md                  # Template logic
    └── variables.md              # Available data variables
```

## Resources

### Obsidian Web Clipper

- [Web Clipper Documentation](https://help.obsidian.md/web-clipper)
- [Variables](https://help.obsidian.md/web-clipper/variables)
- [Filters](https://help.obsidian.md/web-clipper/filters)
- [Logic](https://help.obsidian.md/web-clipper/logic)
- [Templates](https://help.obsidian.md/web-clipper/templates)

### Agent Skills Documentation

- [Agent Skills Official Site](https://agentskills.io/home) - Complete guide to the Agent Skills standard
- [Cursor Agent Skills](https://cursor.com/docs/context/skills) - Cursor-specific implementation guide

### Community Skill Collections

- [Antigravity Awesome Skills](https://github.com/sickn33/antigravity-awesome-skills) - Curated repository of high-quality agent skills; this skill is included there as well
- [Skills Directory](https://skills.sh) - Open agent skills directory with one-command installs

## License

Apache License 2.0 - See [LICENSE.txt](LICENSE.txt) for details.

---

**Keywords**: Obsidian, Web Clipper, AI Agent Skill, Claude Code, Cursor, Gemini CLI, Template Creator, Obsidian Templates, SKILL.md
