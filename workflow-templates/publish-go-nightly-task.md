# "Publish Nightly Build" workflow (Go, Task)

Workflow file: [publish-go-nightly-task.yml](publish-go-nightly-task.yml)

Publish nightly builds of a [Go](https://golang.org/) project.

This is the version of the workflow for projects using the [Task](https://taskfile.dev/#/) task runner tool.

## Assets

See [the "Release" workflow (Go, Task) documentation](release-go-task.md#assets)

## Configuration

See [the "Release" workflow (Go, Task) documentation](release-go-task.md#configuration)

In addition, the following [repository secret](https://docs.github.com/en/actions/reference/encrypted-secrets#creating-encrypted-secrets-for-a-repository) must be defined:

- `DD_API_KEY` - [Datadog](https://www.datadoghq.com/) API key.

## Readme badge

Markdown badge:

```markdown
[![Publish Nightly Build status](https://github.com/REPO_OWNER/REPO_NAME/actions/workflows/publish-go-nightly-task.yml/badge.svg)](https://github.com/REPO_OWNER/REPO_NAME/actions/workflows/publish-go-nightly-task.yml)
```

Replace the `REPO_OWNER` and `REPO_NAME` placeholders in the URLs with the final repository owner and name ([example](https://raw.githubusercontent.com/arduino-libraries/ArduinoIoTCloud/master/README.md)).

---

Asciidoc badge:

```adoc
image:https://github.com/{repository-owner}/{repository-name}/actions/workflows/publish-go-nightly-task.yml/badge.svg["Publish Nightly Build status", link="https://github.com/{repository-owner}/{repository-name}/actions/workflows/publish-go-nightly-task.yml"]
```

Define the `{repository-owner}` and `{repository-name}` attributes and use them throughout the readme ([example](https://raw.githubusercontent.com/arduino-libraries/WiFiNINA/master/README.adoc)).

## Commit message

```
Add CI workflow to publish nightly builds

On a daily schedule:

- Build the project for all supported platforms.
- Sign and notarize the macOS build.
- Upload the builds to Arduino's downloads server.

This will enable everyone to participate to the project's development via beta testing.
```

## PR message

```markdown
On a daily schedule:

- Build the project for all supported platforms.
- Use [gon](https://github.com/mitchellh/gon) to sign and notarize the macOS build.
- Upload the builds to Arduino's downloads server.

This will enable everyone to participate to the project's development via beta testing.
```

## Related

- ["Release" workflow (Go, Task)](release-go-task.md)