# GETTING_STARTED.md

## Purpose

This guide enables a new contributor to:
- set up the project locally
- validate the application
- follow the development workflow
- create and submit a pull request

Target setup time: under 1 hour.

---

## Prerequisites

Ensure the following are installed:

- Python 3.11+ (tested with 3.13)
- Git
- GitHub account
- VS Code or similar editor

---

## 1. Clone the Repository

```bash
git clone https://github.com/gbadedata/engineering-workflow-automation.git
cd engineering-workflow-automation
```

---

## 2. Set Up Virtual Environment

```bash
python -m venv .venv
.venv\Scripts\activate
```

---

## 3. Install Dependencies

```bash
pip install -r requirements.txt
```

---

## 4. Run the Application

```bash
python app.py
```

Expected:
- Server starts on localhost

---

## 5. Run Tests

```bash
pytest -v
```

Expected:
- All tests pass

---

## 6. Lint the Code

```bash
flake8 app.py test_app.py
```

Expected:
- No linting errors

---

## 7. Create a Feature Branch

```bash
git checkout -b feature/TRELLO-XXX-description
```

---

## 8. Make Changes and Commit

```bash
git add .
git commit -m "[TRELLO-XXX] Description of change"
```

---

## 9. Push to GitHub

```bash
git push origin feature/TRELLO-XXX-description
```

---

## 10. Open Pull Request

- Go to GitHub
- Create Pull Request
- Ensure CI checks run

---

## 11. CI Validation

Pull request will:
- run linting
- run tests

Merge only after:
- all checks pass

---

## Troubleshooting

### CI Fails
- Check lint errors
- Fix formatting issues
- re-commit and push

### Tests Fail
- Run `pytest` locally
- debug failing test

### Environment Issues
- ensure virtual environment is activated
- reinstall dependencies
