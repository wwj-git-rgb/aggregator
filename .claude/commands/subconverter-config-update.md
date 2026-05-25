---
name: subconverter-config-update
description: Workflow command scaffold for subconverter-config-update in aggregator.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /subconverter-config-update

Use this workflow when working on **subconverter-config-update** in `aggregator`.

## Goal

Updates configuration templates and examples for the subconverter component, often in tandem with subscribe module changes.

## Common Files

- `aggregate/subconverter/pref.example.ini`
- `aggregate/subconverter/pref.example.yml`
- `aggregate/subconverter/pref.toml`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit one or more of: aggregate/subconverter/pref.example.ini, pref.example.yml, pref.toml
- Optionally edit subscribe module files to match config changes
- Commit changes

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.