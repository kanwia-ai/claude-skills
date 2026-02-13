# Claude Skills

A collection of custom skills for Claude Code that extend its capabilities with reusable, context-aware instruction sets.

## What Are Skills

Skills are structured instruction files that Claude Code activates automatically based on context. Unlike slash commands, skills are model-driven -- Claude decides when to apply them based on your input and the skill description. Each skill lives in ~/.claude/skills/ after installation.

## Available Skills

### prompt-polisher

Transforms messy voice transcriptions, stream-of-consciousness notes, and rough document content into polished, Claude-optimized prompts.

**What it does:**

- Strips filler words, self-corrections, and false starts from voice input
- Extracts intent, constraints, and success criteria from unstructured text
- Detects gaps (ambiguous scope, missing format, unclear model target) and asks all clarifying questions at once
- Applies Anthropic best practices for Claude 4.x, with model-specific tuning for Opus 4.5 and Sonnet 4.5
- Structures output using XML tags (context, task, requirements, success_criteria)
- Previews the polished prompt for approval before execution

**Trigger phrases:** "polish this", "clean this up", "turn this into a prompt", or any clearly rough/unstructured input.

**Included files:**

- SKILL.md -- skill definition and full workflow (7 stages: voice cleanup, intent extraction, gap detection, best practices, structuring, preview, execute)
- reference.md -- Anthropic prompt engineering guidelines for Claude 4.x, Opus 4.5, and Sonnet 4.5
- examples.md -- six before/after transformation examples covering voice transcriptions, rough notes, debugging streams, and multi-document synthesis

## Installation

Install all skills:

    cp -r skills/* ~/.claude/skills/

Install a single skill:

    cp -r skills/prompt-polisher ~/.claude/skills/

## Skill File Structure

    skill-name/
      SKILL.md        Main skill definition (required)
      reference.md    Supporting documentation (optional)
      examples.md     Usage examples (optional)

SKILL.md uses YAML frontmatter with name and description fields, followed by Markdown instructions.

## Creating a New Skill

1. Create a directory under skills/ with the skill name.
2. Add a SKILL.md file with frontmatter (name, description) and step-by-step instructions.
3. Optionally add reference.md for background material and examples.md for demonstrations.
4. Copy the directory to ~/.claude/skills/.

## License

MIT
