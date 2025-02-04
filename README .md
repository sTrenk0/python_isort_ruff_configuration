# README_en.md

## Project Overview

This project is a Python repository configured with `ruff` and `isort` to ensure code formatting and linting consistency. Additionally, it includes a `pre-commit.sh` script that automates these checks before committing changes.

## Tools Used

- **Ruff**: A fast Python file linter and formatter.
- **Isort**: A tool for sorting Python imports.

## Configuration Details

### Ruff Linting & Formatting

`ruff` is configured to:

- Enforce a **line length of 88**.
- Allow customization of which directories should be excluded from Ruff checks.
- Apply linting rules for style errors (`E`), detection errors (`F`), best practices (`B`), security (`S`), and Pylint compatibility (`PL`).
- Ignore `E203` (Black formatting conflict) and `E501` (line length handled by Black).
- Use **double quotes** for strings and auto-detect line endings.

### Isort Configuration

`isort` is set up to:

- Skip sorting imports in the same directories excluded in `ruff`.
- Use a **multi-line output style** (`3`).
- Include **trailing commas** in multi-line imports.
- Group imports using **grid wrap** (`3`).
- Maintain a **line length of 88**.

## Pre-Commit Hook

The `pre-commit.sh` script ensures code quality before committing by **running only on files that have been added to the **stage-area** using `git add`**:

1. **`ruff format .`** - Formats the entire codebase.
2. **`ruff check .`** - Runs linting checks.
3. **`isort .`** - Sorts imports.
4. **If all checks pass**, the commit proceeds. Otherwise, errors are displayed for correction.

To use the pre-commit hook, run:

```sh
chmod +x pre-commit.sh
./pre-commit.sh
```