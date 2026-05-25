---
name: subscribe-module-feature-development
description: Workflow command scaffold for subscribe-module-feature-development in aggregator.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /subscribe-module-feature-development

Use this workflow when working on **subscribe-module-feature-development** in `aggregator`.

## Goal

Implements or updates features in the subscribe module, often involving crawling, processing, and utilities for subscription sources.

## Common Files

- `aggregate/subscribe/airport.py`
- `aggregate/subscribe/clash.py`
- `aggregate/subscribe/crawl.py`
- `aggregate/subscribe/process.py`
- `aggregate/subscribe/push.py`
- `aggregate/subscribe/renewal.py`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Edit or create one or more of: aggregate/subscribe/airport.py, clash.py, crawl.py, process.py, push.py, renewal.py, utils.py, mailtm.py, workflow.py, collect.py
- Optionally update subconverter configs (pref.example.ini/yml/toml) if relevant
- Commit changes with a message describing the feature or fix

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.