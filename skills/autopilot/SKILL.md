---
name: autopilot
description: End-to-end autonomous delivery from idea to working code in Codex
---

# Autopilot Skill

## Purpose

Take a product idea and drive it through the full lifecycle: requirements, technical plan, implementation, QA, and validation. This mode is for hands-off execution with milestone checkpoints.

## Use When

- The user wants full autonomous delivery from idea to working result
- The task is multi-phase and non-trivial
- The user prefers fewer check-ins and end-to-end ownership

## Do Not Use When

- The user only wants brainstorming or option exploration
- The task is a small, focused bug fix
- The user wants manual step-by-step control

## Execution Policy

- Complete each phase before moving to the next
- Parallelize independent work where possible
- Ask the user only when blocked by missing decisions/credentials
- Keep artifacts in `.codex/autopilot/` for traceability and resume

## Phases

1. Expansion
- Convert brief idea into clear requirements
- Output: `.codex/autopilot/spec.md`

2. Planning
- Create implementation plan with acceptance criteria and risks
- Output: `.codex/autopilot/plan.md`

3. Implementation
- Execute plan in small verifiable increments
- Keep TODO state updated

4. QA Loop
- Run build/test/lint cycle and fix failures
- Max 5 cycles
- Stop early and report if the same fundamental error repeats 3 times

5. Validation
- Run final checks against acceptance criteria
- Do a self-review for security, correctness, and maintainability

6. Handoff
- Summarize what was built, changed files, and verification evidence
- Update `.codex/autopilot/state.json` to terminal status

## Resume

If interrupted, resume from `.codex/autopilot/state.json` and continue at the last incomplete phase.

## Output

- What was delivered
- What was verified (commands + result)
- What remains blocked (if any)
