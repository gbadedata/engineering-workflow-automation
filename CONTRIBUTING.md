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

```text
feature/TRELLO-XXX-description
```

Examples:
- feature/TRELLO-002-ci-pipeline
- feature/TRELLO-003-extra-test

---

## Commit Message Rules

All commits must follow:

```text
[TRELLO-XXX] Short description
```

Examples:
- [TRELLO-002] Add CI pipeline
- [TRELLO-003] Add test coverage

---

## Pull Request Requirements

Every pull request must:

- reference a Trello ID
- pass all CI checks
- contain clear description of changes
- be reviewed before merge

---

## CI Enforcement

GitHub Actions will:

- install dependencies
- run flake8 (linting)
- run pytest (tests)

### Failure Rules

- lint failure → PR blocked
- test failure → PR blocked

---

## Code Quality Rules

- no unused imports
- no trailing whitespace
- readable naming
- tests must cover new functionality

---

## Definition of Done

A task is complete only when:

- code is implemented
- tests pass
- CI passes
- PR is merged into `main`
- Trello card is moved to Done
