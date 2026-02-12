---
name: ralph
description: Persistent completion loop for Codex until verified done
---

# Ralph Skill

## Purpose

Drive a task to verified completion through iterative execution, verification, and correction. Ralph is for "do not stop until done" requests.

## Use When

- The task must be completed with strong verification evidence
- Work likely needs multiple correction loops
- The user wants persistence over one-shot attempts

## Do Not Use When

- User wants brainstorming/planning only
- Task is tiny and clearly one-shot
- User wants manual stop-and-go control at each step

## Execution Policy

- Keep iterating until acceptance criteria are met or a hard blocker is proven
- Prefer small, verifiable increments
- Run required checks after each meaningful change
- Never claim done without fresh evidence

## Ralph Loop

1. Define completion criteria
- What must pass to be "done"

2. Execute next increment
- Implement highest-priority unresolved item

3. Verify
- Run relevant build/test/lint/diagnostics commands
- Confirm outputs, do not assume

4. Review and decide
- If checks fail: fix and continue
- If checks pass but scope incomplete: continue
- If all criteria met: prepare final handoff

5. Repeat
- Track iteration state in `.codex/ralph-state.json`

## Parallelism Guidance

- Parallelize independent discovery and read operations
- Use `multi_tool_use.parallel` for concurrent search/read steps
- Keep write operations coordinated to avoid conflicts

## Stop Conditions

- Completed: all acceptance criteria verified
- Blocked: missing credentials, unavailable external dependency, or unresolved product decision
- If the same fundamental issue repeats 3 times, report blocker clearly with evidence

## Output

- Current status vs completion criteria
- Verification evidence (commands + outcomes)
- Remaining work or blocker details
