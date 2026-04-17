# Engineering Workflow Automation with GitHub Actions and Trello

## Overview

This project implements a structured engineering workflow around a lightweight Flask API. The focus is not on application complexity, but on enforcing a professional software delivery process using:

- GitHub (version control and pull requests)
- GitHub Actions (CI enforcement)
- Trello (task tracking and workflow visibility)

The goal is to demonstrate how code quality, traceability, and team collaboration can be enforced through process rather than relying on individual discipline.

---

## Objectives

This project was designed to:

- Enforce structured development using feature branches
- Track work using a Trello board across defined stages
- Introduce CI checks (linting and testing) before merge
- Improve onboarding through clear documentation
- Ensure traceability from task -> branch -> commit -> PR

---

## Application

The application is a simple Flask API with three endpoints:

- `GET /health` -> returns service status
- `POST /sum` -> sums two numbers
- `POST /reverse-string` -> reverses a string

The simplicity is intentional. The value of this project lies in the workflow, not the business logic.

---

## Repository Structure

```text
engineering-workflow-automation/
├── .github/
│   └── workflows/
│       └── ci.yml
├── app.py
├── test_app.py
├── requirements.txt
├── README.md
├── GETTING_STARTED.md
├── CONTRIBUTING.md
├── evidence/
│   └── screenshots/
│       ├── 01-github-actions-failed-build.png
│       ├── 02-github-actions-success-build.png
│       ├── 03-github-actions-success-build-2.png
│       ├── 04-pr-open-with-checks.png
│       ├── 05-pr-checks-passed.png
│       ├── 06-trello-board-initial.png
│       ├── 07-trello-002-moved-to-in-progress.png
│       └── 08-final-trello-board.png
```

This structure reflects the actual implementation and evidence organization.

---

## Engineering Workflow

### 1. Task Management (Trello)

Work is tracked using a Trello board with the following lists:

- Backlog
- In Progress
- Review/QA
- Done

Each task is assigned a unique ID:

- TRELLO-001 - Repository setup
- TRELLO-002 - CI pipeline
- TRELLO-003 - Additional test coverage
- TRELLO-004 - Onboarding guide
- TRELLO-005 - Contributing standards
- TRELLO-006 - Final documentation and evidence

Cards move strictly across lists to reflect real progress.

---

### 2. Branching Strategy (Git)

- `main` -> stable production branch
- `feature/TRELLO-###-description` -> isolated work

Examples:
- `feature/TRELLO-002-ci-pipeline`
- `feature/TRELLO-003-extra-test`

Rules enforced:
- No direct commits to `main`
- All changes go through Pull Requests
- Commit messages reference Trello IDs

---

### 3. Pull Request Workflow

Each feature follows:

1. Create feature branch
2. Implement changes
3. Push branch
4. Open Pull Request
5. CI checks run automatically
6. Merge only after checks pass

This ensures controlled and reviewable integration.

---

## CI/CD Pipeline

GitHub Actions workflow runs on:

- push
- pull request

### Steps executed

1. Install dependencies
2. Run linting (`flake8`)
3. Run tests (`pytest`)

### Behavior

- Lint failure -> pipeline stops
- Test failure -> pipeline fails
- Only clean code passes

---

## Testing

The test suite validates all endpoints.

### Additional Test (TRELLO-003)

The originally suggested extra test already existed in `main`. Instead of duplicating it, a new meaningful test was added:

```python
def test_reverse_numeric_string(client):
    res = client.post('/reverse-string', json={"text": "12345"})
    assert res.get_json()["result"] == "54321"
```

This improves coverage while maintaining integrity.

---

## Evidence

Screenshots are stored in:

```plaintext
evidence/screenshots/
```

### CI / Engineering
- `01-github-actions-failed-build.png`
- `02-github-actions-success-build.png`
- `03-github-actions-success-build-2.png`

### Pull Request Workflow
- `04-pr-open-with-checks.png`
- `05-pr-checks-passed.png`

### Project Management (Trello)
- `06-trello-board-initial.png`
- `07-trello-002-moved-to-in-progress.png`
- `08-final-trello-board.png`

### Interpretation

The evidence shows:
- intentional failure -> correction -> success
- PR gating with CI checks
- task progression across Trello stages

---

## What Worked

- Strong traceability across Trello, Git, and PRs
- CI pipeline correctly enforced quality gates
- Real failure -> fix -> validation cycle captured
- Documentation separated clearly by purpose
- Evidence curated into a clean narrative

---

## What Did Not Work Initially

- Incorrect default branch setup
- Accidental commit on `main`
- flake8 formatting failures
- Over-capturing of screenshots
- Incorrect file path during evidence staging

---

## How Issues Were Resolved

- Recreated proper `main` branch structure
- Recovered commit using cherry-pick
- Fixed linting errors using flake8 feedback
- Reduced screenshots to only meaningful states
- Corrected file paths (`evidence/screenshots/`)

---

## Lessons Learned

- Workflow discipline must be enforced, not assumed
- CI failures are feedback, not blockers
- Documentation must evolve with the project
- Evidence should be curated, not dumped
- Honest fixes are stronger than artificial perfection

---

## Getting Started

See:

```plaintext
GETTING_STARTED.md
```

---

## Contributing

See:

```plaintext
CONTRIBUTING.md
```

---

## Final Outcome

This project demonstrates a complete engineering workflow:

- Task tracking (Trello)
- Version control (GitHub)
- Quality enforcement (GitHub Actions)
- Structured collaboration (PR workflow)
- Reproducible onboarding
- Clear documentation and evidence

The result is not just a working API, but a controlled and auditable development process.
