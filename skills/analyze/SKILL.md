---
name: analyze
description: Deep analysis and investigation for Codex workflows
---

# Analyze Skill

## Purpose

Run deep, evidence-based investigation before implementation. This skill is for root-cause analysis, architecture understanding, dependency mapping, and impact assessment.

## Use When

- The user asks to analyze, investigate, debug, or explain why something happens
- The issue spans multiple files or systems
- You need high-confidence findings before making changes

## Do Not Use When

- The user asks for immediate code changes with clear scope
- The question can be answered by reading one file quickly
- The task is planning-heavy rather than investigation-heavy

## Workflow

1. Define the analysis question and success criteria
2. Run broad discovery first:
- Use `rg --files` to map candidate files
- Use `rg` for symbol and keyword search
- Batch independent reads/searches with `multi_tool_use.parallel`
3. Build focused evidence:
- Read only relevant files and lines
- Trace call chains and data flow
- Confirm assumptions with commands/tests when needed
4. Produce structured findings:
- Root cause or architecture conclusion
- Evidence with file references
- Confidence level and open questions
- Recommended next actions

## Tool Guidance

- Prefer `rg` for fast search
- Use `functions.exec_command` for reproducible checks
- Use `update_plan` for long, multi-step investigations
- Browse web only when the user asks for external/latest information

## Output

Return concise, decision-ready analysis:
- Findings first
- Evidence references (`/absolute/path:line`)
- Risks and follow-up actions
