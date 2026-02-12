---
name: build-fix
description: Fix build and type errors with minimal, targeted changes
---

# Build Fix Skill

## Purpose

Get the project back to green quickly with the smallest viable diff.

## Use When

- Build is broken
- Type checker fails
- Lint/type/build errors block progress

## Constraints

- Minimal changes only
- No unrelated refactors
- No architecture redesign
- Fix root causes, do not bypass tests/checks

## Workflow

1. Detect the right verification commands from project scripts/config
2. Capture current failing output
3. Group errors by root cause and fix in batches
4. Re-run verification after each batch
5. Repeat until green or a hard blocker is identified

## Tool Guidance

- Use `functions.exec_command` for build/type/test/lint commands
- Use `rg` to locate symbols and related code quickly
- Batch read/search operations with `multi_tool_use.parallel`

## Output

- Commands run and final status
- Error categories fixed
- Files changed with brief reason
- Remaining blockers (if any)
