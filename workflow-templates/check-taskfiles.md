# "Check Taskfiles" workflow

Validate the repository's [Taskfiles](https://taskfile.dev/#/usage) against the JSON schema.

## Installation

### Workflow

Install the [`check-taskfiles.yml`](check-taskfiles.yml) GitHub Actions workflow to `.github/workflows/`

### Dependencies

The tool dependencies of this workflow are managed by [npm](https://www.npmjs.com/).

Add the dependencies by running this command:

```text
npm install --save-dev ajv-cli@^5.0.0 ajv-formats@^3.0.1
```

Commit the resulting changes to the `package.json` and `package-lock.json` files.

### Configuration

#### Workflow

The workflow is configured to check all files named `Taskfile.yml` in the repository. If there are additional taskfiles, add them to the following fields in `check-taskfiles.yml`:

- `on.push.paths`
- `on.pull_request.paths`
- `jobs.validate.strategy.matrix.file[]`

Configure the version of Node.js used for development of the project in the `env.NODE_VERSION` field of `check-taskfiles.yml`.

#### `.gitignore`

Add the following to [`/.gitignore`](https://git-scm.com/docs/gitignore):

```
/node_modules/
```

### Readme badge

Markdown badge:

```markdown
[![Check Taskfiles status](https://github.com/TODO_REPO_OWNER/TODO_REPO_NAME/actions/workflows/check-taskfiles.yml/badge.svg)](https://github.com/TODO_REPO_OWNER/TODO_REPO_NAME/actions/workflows/check-taskfiles.yml)
```

Replace the `TODO_REPO_OWNER` and `TODO_REPO_NAME` placeholders in the URLs with the final repository owner and name ([example](https://raw.githubusercontent.com/arduino-libraries/ArduinoIoTCloud/master/README.md)).

---

Asciidoc badge:

```adoc
image:https://github.com/{repository-owner}/{repository-name}/actions/workflows/check-taskfiles.yml/badge.svg["Check Taskfiles status", link="https://github.com/{repository-owner}/{repository-name}/actions/workflows/check-taskfiles.yml"]
```

Define the `{repository-owner}` and `{repository-name}` attributes and use them throughout the readme ([example](https://raw.githubusercontent.com/arduino-libraries/WiFiNINA/master/README.adoc)).

## Commit message

```
Add CI workflow to validate Taskfiles

On every push or pull request that affects the repository's Taskfiles, and periodically, validate them
against the JSON schema.
```

## PR message

```markdown
On every push or pull request that affects the repository's [Taskfiles](https://taskfile.dev/#/usage), and periodically, validate them against the JSON schema.
```
