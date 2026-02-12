---
name: deepsearch
description: Thorough codebase search and dependency tracing in Codex
---

# Deep Search Skill

## Objective

Run comprehensive search across the codebase and return high-signal results with context.

## Strategy

1. Broad pass
- `rg --files` for file map
- `rg` with exact terms and variants

2. Relationship pass
- Follow imports/exports and callers/callees
- Trace ownership and boundaries

3. Validation pass
- Read key files around matches
- Confirm primary implementation path

4. Synthesis
- Primary locations
- Related files
- Usage patterns
- Key insights/gotchas

## Tool Guidance

- Prefer `rg` over slower search tools
- Batch independent search/read operations with `multi_tool_use.parallel`
- Keep search iterative: narrow queries as understanding improves

## Output

Cite file references with line numbers and separate "primary" vs "related" results.
