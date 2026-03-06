---
name: learning
description: At the end of a session, evaluate what was learned and propose updates to the project's CLAUDE.md file as new procedures/SOPs.
user-invocable: true
allowed-tools: Read, Grep, Edit, Write, Glob
---

# Learning Review

Review the current session to identify new procedures, patterns, or SOPs worth adding to the project's `CLAUDE.md` file.

## Steps

### 1. Read the current CLAUDE.md
Find the `CLAUDE.md` file in the project root and read it in full. If it doesn't exist, treat it as empty.

### 2. Analyze the session
Mentally replay everything that happened in this session:
- Commands run and problems solved
- Architectural decisions made
- Errors encountered and how they were resolved
- Patterns or conventions that emerged during the work
- Non-obvious workarounds or discoveries
- Preferences explicitly expressed by the user

### 3. Identify the delta
Compare what emerged in the session against the current `CLAUDE.md` content:
- Are there new procedures to document that aren't already covered?
- Are there recurring errors or pitfalls worth adding as warnings?
- Are there implicit conventions that should be made explicit?
- Are there commands, tools, or workflows worth codifying?

### 4. Propose additions
If you identified a delta (new learnings), present to the user:
- A **clear summary** of what was learned in the session
- The **proposed additions** to `CLAUDE.md`, formatted and ready to insert
- A **brief explanation** of why each addition is useful for future sessions

If the delta is empty (nothing new beyond the existing CLAUDE.md), say so explicitly: "No new learnings to add from this session."

### 5. Update CLAUDE.md (with approval)
Wait for user confirmation before modifying the file. If the user approves (even partially), update `CLAUDE.md` integrating only the approved sections.

## Format for additions

Insert new learnings into an appropriate section of `CLAUDE.md`. If the section doesn't exist, create it. Use this style:

```markdown
## Procedures / SOPs

### [Procedure name]
[Concise description of when to apply it and how]

## Errors to avoid

- **[Error]**: [Explanation and fix]
```

## Important notes

- Do not add obvious things or anything already documented
- Favor conciseness: every rule must be actionable
- Do not invent procedures that didn't genuinely emerge from the session
- Always document explicit preferences expressed by the user during the session
