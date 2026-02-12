---
name: learner
description: Extract reusable Codex-native skills from hard-won debugging insights
---

# Learner Skill

## Purpose

Convert difficult problem-solving sessions into reusable skills that improve future execution quality.

## Core Principle

A good learned skill captures decision heuristics, not copy-paste snippets.

- Bad: one-off patch recipe
- Good: reusable diagnosis/fix pattern with clear triggers and boundaries

## Use When

- A bug required non-obvious investigation
- You discovered project-specific pitfalls
- You found a repeatable pattern worth preserving

## Do Not Use When

- The insight is generic and easily searchable
- The fix is trivial and unlikely to recur
- There is no clear trigger pattern

## Extraction Workflow

1. Problem statement
- Exact symptom/error
- Concrete file paths and context

2. Solution
- Precise changes that resolved it
- Why this worked

3. Triggers
- Searchable phrases/signals for future detection

4. Scope
- User-level skill: `~/.codex/skills/learned/<skill-name>/`
- Project-level skill: `.codex/skills/<skill-name>/`

5. Quality gate
- Specific, actionable, non-generic, and reusable

## Output Template

- Insight
- Why it matters
- Recognition pattern
- Approach/heuristic
- Optional focused example

## Related Skills

- `note`: capture quick intermediate findings
- `plan`: formalize execution plan before implementation
