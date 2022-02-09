# Laminas Reusuable Automatic Releases Workflow

This repository contains a reusable workflow describing the Laminas Project automatic releases process.


## Usage

To use the automatic releases workflow:

```yaml
# In a package repository, in the file .github/workflows/release-on-milestone-closed.yml:
name: "Automatic Releases"

on:
  milestone:
    types:
      - "closed"

jobs:
  release:
    uses: laminas/workflow-automatic-releases/.github/workflows/release-on-milestone-closed.yml@1.x
    secrets:
      GIT_AUTHOR_EMAIL: ${{ secrets.GIT_AUTHOR_EMAIL }}
      GIT_AUTHOR_NAME: ${{ secrets.GIT_AUTHOR_NAME }}
      ORGANIZATION_ADMIN_TOKEN: ${{ secrets.ORGANIZATION_ADMIN_TOKEN }}
      SIGNING_SECRET_KEY: ${{ secrets.SIGNING_SECRET_KEY }}
```

## Available references

GitHub recommends when using reusable workflows that you specify a reference to ensure stability.
This package defines a release branch per stable version, as well as tags.
Generally speaking, a release branch will only receive:

- Bugfixes
- New opt-in features (including optional inputs, and new outputs)

Since they will not receive backwards incompatible changes, you can pin to them.

We also provide tags.
Tags are immutable, and can be trusted without issue; however, your project will not benefit from updates without first changing the reference in your workflow.

### Current branches

- 1.x

### Tags

Please see the [releases page](/laminas/workflow-continuous-integration/releases) for a complete list.
