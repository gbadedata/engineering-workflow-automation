# CONTRIBUTING.md

## Purpose

This document defines how contributors should work in this repository to maintain:
- traceability
- code quality
- predictable review flow
- CI enforcement before merge

---

## Development Workflow

This repository uses a structured workflow built around:

- Trello for task tracking
- GitHub for source control
- feature branches for isolated changes
- pull requests for review
- GitHub Actions for automated quality checks

All work begins with a Trello card and ends with a merged pull request into `main`.

---

## Branching Rules

### Stable Branch
- `main` is the stable branch
- do not commit directly to `main`

### Feature Branch Format
All changes must be made on a feature branch.

Format:

```text
feature/TRELLO-XXX-description