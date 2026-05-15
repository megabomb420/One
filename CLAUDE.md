# CLAUDE.md

## Project Overview

> **Status: New / Empty Repository**
> This repository has no source code yet. Update this file as the project takes shape.

This file documents the project for Claude Code and human contributors. Keep it current as conventions and structure evolve.

---

## Tech Stack

_Not yet defined. Update when the stack is chosen._

| Layer | Technology |
|-------|-----------|
| Language | TBD |
| Framework | TBD |
| Database | TBD |
| Testing | TBD |
| CI/CD | TBD |

---

## Folder Structure

_Update as directories are created._

```
One/
├── CLAUDE.md        # This file
└── .git/
```

---

## How to Run / Build

_Add commands here once the project is initialized._

```bash
# Install dependencies
# <command>

# Run development server
# <command>

# Run tests
# <command>

# Build for production
# <command>
```

---

## Coding Conventions

_Establish and document conventions early. Suggested defaults:_

- **Commits**: Conventional Commits format (`feat:`, `fix:`, `chore:`, etc.)
- **Branch naming**: `<type>/<short-description>` (e.g. `feat/user-auth`)
- **Code style**: Enforced via linter/formatter (add config when stack is chosen)
- **No dead code**: Remove unused code rather than commenting it out
- **No TODO comments in committed code**: Use GitHub Issues instead

---

## Development Workflow

1. Branch off `main` using the naming convention above
2. Make changes, keeping commits small and focused
3. Ensure tests pass and linter is clean before pushing
4. Open a PR; require at least one review before merging

---

## Testing

_No tests exist yet. When tests are added, document:_

- Test framework and runner
- How to run the full suite
- Coverage targets
- Which layers are tested (unit / integration / e2e)

---

## Environment Variables

_Document required env vars here. Never commit secrets._

```bash
# Copy .env.example and fill in values
cp .env.example .env
```

| Variable | Required | Description |
|----------|----------|-------------|
| _none yet_ | — | — |

---

## Notes for Claude Code

- This repo was initialized empty on 2026-05-15
- All tasks, TODOs, and known issues should be tracked as GitHub Issues, not inline comments
- When adding new top-level directories, update the Folder Structure section above
