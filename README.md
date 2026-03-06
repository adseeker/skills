# Claude Code Skills

A collection of reusable skills for [Claude Code](https://claude.ai/claude-code).

Skills are invocable prompts that extend Claude Code's capabilities in a structured, repeatable way. Each skill lives in its own directory with a `SKILL.md` file that defines its behavior.

## Installation

Clone this repo into your Claude skills directory:

```bash
git clone https://github.com/adseeker/skills ~/.claude/skills
```

Or install a single skill manually:

```bash
cp -r learning ~/.claude/skills/
```

## Usage

Skills marked as `user-invocable: true` can be triggered in any Claude Code session with:

```
/learning
```

Claude Code will automatically discover skills placed in `~/.claude/skills/`.

## Available Skills

| Skill | Description |
|-------|-------------|
| [learning](./learning/) | At the end of a session, evaluate what was learned and propose updates to the project's CLAUDE.md file as new procedures/SOPs. |

## Skill format

Each skill is a directory containing a `SKILL.md` file with a YAML frontmatter block:

```markdown
---
name: skill-name
description: Short description shown to Claude as a trigger hint.
user-invocable: true
allowed-tools: Read, Write, Edit
---

# Skill Title

Instructions for Claude...
```

### Frontmatter fields

| Field | Required | Description |
|-------|----------|-------------|
| `name` | yes | Unique identifier for the skill |
| `description` | yes | Shown in Claude's system prompt as a usage hint |
| `user-invocable` | no | If `true`, the user can trigger it with `/skill-name` |
| `allowed-tools` | no | Comma-separated list of tools the skill may use |

## Contributing

1. Create a directory named after your skill
2. Add a `SKILL.md` following the format above
3. Update the skills table in this README
4. Open a pull request
