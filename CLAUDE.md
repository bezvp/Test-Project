# CLAUDE.md

This file is read automatically by Claude Code at the start of every session. It provides project context, conventions, and instructions to follow throughout our work together.

---

## Project Overview

**Name:** Test Project
**Purpose:** Learning and experimentation — this project is used to explore tools, workflows, and coding concepts.
**Status:** Active learning environment

> When starting a new real project, replace this section with: what the project does, who it's for, and what problem it solves.

---

## Tech Stack

- **Language:** Python (default for all scripts and logic)
- **Python version:** 3.11+
- **Package manager:** pip
- **Dependency file:** `requirements.txt`
- **Virtual environment:** `.venv` (always use one — never install packages globally)

---

## Project Structure

```
Test Project/
├── CLAUDE.md           # This file
├── README.md           # Project description (shown on GitHub)
├── requirements.txt    # Python dependencies
├── .env                # Local environment variables (never commit this)
├── .gitignore          # Files git should ignore
├── src/                # Main source code
└── tests/              # Test files
```

> Add or update this section as the project grows.

---

## Environment Setup

First time on a new machine:

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

To activate the virtual environment in future sessions:

```bash
source .venv/bin/activate
```

---

## How to Run

```bash
# Activate virtual environment first
source .venv/bin/activate

# Run a script
python src/main.py

# Run tests
python -m pytest tests/
```

---

## Git Workflow

- **Default branch:** `main`
- **Commit often** — each commit should represent one logical change
- **Commit message format:** Short, present-tense description of what changed
  - Good: `Add user login function`
  - Bad: `stuff` / `fixed it` / `changes`
- **Never commit:** `.env`, `.venv/`, `__pycache__/`, `*.pyc`
- **Always ask before force-pushing** to main

---

## Coding Conventions

- Follow **PEP 8** style (standard Python formatting)
- Use **snake_case** for variables and functions: `user_name`, `get_data()`
- Use **PascalCase** for classes: `UserAccount`, `DataProcessor`
- Use **UPPER_CASE** for constants: `MAX_RETRIES = 3`
- Keep functions small and focused — one function, one job
- Prefer clarity over cleverness

---

## Do's and Don'ts

**Do:**
- Use a virtual environment for every project
- Keep `requirements.txt` updated when adding packages
- Write descriptive variable names
- Ask before creating new files or folders — explain the plan first

**Don't:**
- Install packages globally (always use `.venv`)
- Commit secrets, API keys, or passwords — use `.env` instead
- Add unnecessary comments that just repeat what the code says
- Refactor or clean up code unless explicitly asked

---

## Environment Variables

Sensitive values (API keys, passwords, tokens) go in a `.env` file that is **never committed to GitHub**.

Example `.env` file:
```
API_KEY=your_key_here
DATABASE_URL=your_db_url_here
```

Use the `python-dotenv` package to load them in code:
```python
from dotenv import load_dotenv
import os

load_dotenv()
api_key = os.getenv("API_KEY")
```

---

## Notes for Claude

- This user is learning — explain concepts clearly without assuming prior knowledge
- Default to Python for all code unless another language is requested
- Always explain what a command does before running it if it's destructive or unfamiliar
- Prefer simple, readable solutions over clever or complex ones
- When suggesting next steps, offer options rather than just proceeding
- When initializing any new project, always create a `.gitignore` before the first commit — never let `.env` or `.venv/` get committed accidentally
