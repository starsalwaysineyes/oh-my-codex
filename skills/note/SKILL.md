---
name: note
description: Persist important context into a local notepad for Codex sessions
---

# Note Skill

## Purpose

Save high-value context that should survive long sessions and context compaction.

## Storage

Default file: `.codex/notepad.md`

Sections:
- Priority Context (always short and essential)
- Working Memory (timestamped notes)
- Manual (long-term facts)

## Typical Operations

- Add working note
- Add/update priority note
- Add manual permanent note
- Show notes
- Prune stale working notes
- Clear working notes only

## Workflow

1. Ensure `.codex/` exists
2. Create `.codex/notepad.md` if missing
3. Parse requested note action
4. Write/update target section
5. Confirm what changed

## Guidance

- Keep Priority Context small and factual
- Use Working Memory for temporary breadcrumbs
- Use Manual for stable team/process information

## Output

Return concise confirmation with file path and affected section.
