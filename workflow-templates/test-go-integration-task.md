# "Test Integration" workflow (Go, Task)

Workflow file: [test-go-integration-task.yml](test-go-integration-task.yml)

Run Python integration tests for a [Go](https://golang.org/) module.

This is the version of the workflow for projects using the [Task](https://taskfile.dev/#/) task runner tool.

## Installation

The Python dependencies are managed by [Poetry](https://python-poetry.org/).

Install Poetry by following these instructions:<br />
https://python-poetry.org/docs/#installation

If your project does not already use Poetry, you can initialize the [`pyproject.toml`](https://python-poetry.org/docs/pyproject/) file using these commands:

```
poetry init --python="^3.9" --dev-dependency="pytest@^6.2.4" --dev-dependency="invoke@^1.5.0"
poetry install
```

If already using Poetry, add the tool using this command:

```
poetry add --dev "pytest@^6.2.4" "invoke@^1.5.0"
```

Make sure to commit the resulting `pyproject.toml` and `poetry.lock` files.

## Assets

- [`Taskfile.yml`](assets/test-go-integration-task/Taskfile.yml) - Test runner task.
  - Install to: repository root (or add the `go:test-integration` task into the existing `Taskfile.yml`)
- [`Taskfile.yml`](assets/shared/go/Taskfile.yml) - Build task.
  - Merge the `go:build` task into the existing `Taskfile.yml`.
- [`__init__.py`](assets/test-python/__init__.py) - Template for Python integration tests.
  - Install to: `/tests/`
- [`test_all.py`](assets/test-integration/test_all.py) - Template for Python integration tests.
  - Install to: `/tests/`
- [`pytest.ini`](assets/test-python/pytest.ini) - [pytest](https://pytest.org) configuration file.
  - Install to: `/tests/`

## Readme badge

Markdown badge:

```markdown
[![Test Integration status](https://github.com/REPO_OWNER/REPO_NAME/actions/workflows/test-go-integration-task.yml/badge.svg)](https://github.com/REPO_OWNER/REPO_NAME/actions/workflows/test-go-integration-task.yml)
```

Replace the `REPO_OWNER` and `REPO_NAME` placeholders in the URLs with the final repository owner and name ([example](https://raw.githubusercontent.com/arduino-libraries/ArduinoIoTCloud/master/README.md)).

---

Asciidoc badge:

```adoc
image:https://github.com/{repository-owner}/{repository-name}/actions/workflows/test-go-integration-task.yml/badge.svg["Test Integration status", link="https://github.com/{repository-owner}/{repository-name}/actions/workflows/test-go-integration-task.yml"]
```

Define the `{repository-owner}` and `{repository-name}` attributes and use them throughout the readme ([example](https://raw.githubusercontent.com/arduino-libraries/WiFiNINA/master/README.adoc)).

## Commit message

```
Add CI workflow to run integration tests

On every push and pull request that affects relevant files, run the integration tests.
```

## PR message

```markdown
On every push and pull request that affects relevant files, run the integration tests.
```