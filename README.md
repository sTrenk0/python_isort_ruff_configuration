# README.md

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

___

## Обзор проекта

Этот проект представляет собой Python-репозиторий, в котором настроены `ruff` и `isort` для обеспечения единообразного форматирования и линтинга кода. В него также включён скрипт `pre-commit.sh`, который автоматизирует эти проверки перед коммитами.

## Используемые инструменты

- **Ruff**: Быстрый инструмент для линтинга и форматирования Python-кода.
- **Isort**: Утилита для сортировки импортов в Python.

## Детали конфигурации

### Линтинг и форматирование с Ruff

`ruff` настроен на:

- Ограничение длины строки **88 символами**.
- Возможность настраивать список директорий, которые исключаются из проверки Ruff.
- Применение правил линтинга: **ошибки стиля** (`E`), **обнаружение ошибок** (`F`), **лучшие практики** (`B`), **безопасность** (`S`), **совместимость с Pylint** (`PL`).
- Игнорирование `E203` (конфликт форматирования с Black) и `E501` (Black уже обрабатывает длину строки).
- Использование **двойных кавычек** для строк и автоопределение конца строки.

### Конфигурация Isort

`isort` настроен на:

- Возможность исключать указанные директории из сортировки импортов.
- Использование **многострочного вывода** (`3`).
- Добавление **запятых** в конце многострочных импортов.
- Группировку импортов с использованием **grid wrap** (`3`).
- Соблюдение **максимальной длины строки 88 символов**.

## Pre-Commit Hook

Скрипт `pre-commit.sh` выполняет автоматические проверки перед коммитом, **обрабатывая только файлы, добавленные в stage-зону с помощью `git add`**:

1. **`ruff format .`** — форматирует весь код.
2. **`ruff check .`** — выполняет линтинговую проверку.
3. **`isort .`** — сортирует импорты.
4. **Если все проверки пройдены**, коммит выполняется. В противном случае выводятся ошибки, которые необходимо исправить.

### Как использовать pre-commit hook

Для активации pre-commit хука выполните:

```sh
chmod +x pre-commit.sh
./pre-commit.sh
