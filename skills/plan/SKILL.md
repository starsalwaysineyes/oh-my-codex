---
name: plan
description: Strategic planning with direct, interview, review, and consensus modes for Codex
---

# Plan Skill

## Purpose

Create actionable implementation plans with clear acceptance criteria before coding.

## Modes

- Interview mode: vague/broad request, gather requirements progressively
- Direct mode: request already detailed, plan immediately
- Review mode: evaluate an existing plan
- Consensus mode: iterate plan-review-revise until stable

## Use When

- Scope is broad or unclear
- There are meaningful tradeoffs
- A team needs explicit acceptance criteria before execution

## Do Not Use When

- Task is a small, obvious one-shot fix
- User explicitly asks to skip planning and start implementation

## Execution Policy

- Ask one focused question at a time (plain chat, no batching)
- Gather codebase facts first before asking user about those facts
- Keep plans testable and verifiable
- Save plans under `.codex/plans/`

## Workflow

1. Classify request (interview vs direct)
2. Gather facts from repository (`rg`, targeted reads)
3. Clarify constraints with minimal user questions
4. Produce plan with:
- Requirements summary
- Acceptance criteria
- Implementation steps with file references
- Risks and mitigations
- Verification strategy
5. Save plan file and summarize key decisions

## Review Mode

Given an existing plan, return:
- Verdict: APPROVE / REVISE / REJECT
- Critical gaps
- Concrete revision actions

## Consensus Mode

Iterate:
- draft -> critique -> revise
- Stop at convergence or max 5 rounds

## Output

Use concise structured sections and include explicit, testable criteria.
