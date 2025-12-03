# Claude Skills

A collection of custom skills for Claude Code that enhance AI-assisted workflows.

## What are Skills?

Skills are reusable instruction sets that Claude Code automatically activates based on context. Unlike slash commands (which require manual invocation), skills are model-driven - Claude decides when to use them based on your input and the skill's description.

## Available Skills

| Skill | Description |
|-------|-------------|
| [prompt-polisher](skills/prompt-polisher/) | Transform messy voice transcriptions and unstructured notes into polished, Claude-optimized prompts |

## Installation

### Install All Skills

```bash
cp -r skills/* ~/.claude/skills/
```

### Install Individual Skill

```bash
cp -r skills/prompt-polisher ~/.claude/skills/
```

## Skill Structure

Each skill follows Claude Code's standard structure:

```
skill-name/
├── SKILL.md        # Main skill definition (required)
├── reference.md    # Supporting documentation (optional)
└── examples.md     # Usage examples (optional)
```

### SKILL.md Format

```yaml
---
name: skill-name
description: When to activate and what the skill does
---

# Skill Title

## Instructions
Step-by-step guidance for Claude
```

## Creating New Skills

1. Create a new directory under `skills/`
2. Add a `SKILL.md` with frontmatter and instructions
3. Optionally add `reference.md` and `examples.md`
4. Install to `~/.claude/skills/`

## Usage

Once installed, skills activate automatically. For example, with `prompt-polisher`:

- Dump a voice transcription into Claude
- Claude detects unstructured input and activates the skill
- The skill cleans up your input, asks clarifying questions, and generates a polished prompt
- You approve, then Claude executes

## License

MIT
