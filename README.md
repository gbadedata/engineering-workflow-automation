# Engineering Workflow Automation with GitOps & CI

## Project Overview

This project implements a structured GitOps-style development workflow for a lightweight Flask service.

The objective is not application complexity, but engineering discipline:
- controlled change management
- enforced code quality
- traceable workflow from task to deployment

The system integrates:
- Trello (task tracking)
- GitHub (source control and PR workflow)
- GitHub Actions (CI enforcement)

---

## Objectives

- Track work using Trello cards with unique IDs
- Enforce feature-branch-based development
- Prevent direct changes to `main`
- Use pull requests for all changes
- Enforce linting and testing through CI
- Provide clear onboarding and contribution documentation
- Maintain full traceability across all layers

---

## Repository Structure

```text
.github/workflows/ci.yml
app.py
test_app.py
requirements.txt
README.md
GETTING_STARTED.md
CONTRIBUTING.md
evidence/