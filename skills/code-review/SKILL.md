---
name: code-review
description: Comprehensive Codex-style code review with severity-ranked findings
---

# Code Review Skill

## Purpose

Perform a rigorous review focused on regressions, correctness, security, and maintainability.

## Use When

- The user asks for a code review
- Before merge/release on non-trivial changes
- After major refactor or feature delivery

## Review Scope

- Prefer reviewing `git diff` first
- If scope is provided by user, focus there
- Expand only when needed for context

## Review Priorities

1. Correctness and behavioral regressions
2. Security issues and unsafe assumptions
3. Reliability/performance risks
4. Maintainability and testing gaps

## Workflow

1. Identify changed files and hotspots
2. Read code and related call sites/tests
3. Validate key assumptions with commands when needed
4. Produce findings ranked by severity

## Output Format

- Findings first (highest severity first)
- Each finding includes:
- Severity (`P0` to `P3`)
- Clear impact
- Evidence with path+line
- Recommended fix direction
- Then list open questions/assumptions
- End with concise summary and residual risks

## If No Findings

State explicitly that no actionable findings were found and mention any testing blind spots.
