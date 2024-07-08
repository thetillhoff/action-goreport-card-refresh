# Action: Golang build

This action triggers a refresh for your repository on https://goreportcard.com.


Example usage:
```yaml
name: Release new version

on:
  push:
    tags:
    - "v[0-9]+.[0-9]+.[0-9]+"

jobs:
  release-prerequisites:
    # [...] See https://github.com/thetillhoff/action-release-prerequisites

  golang-build:
    # [...] See https://github.com/thetillhoff/action-golang-build

  release-artifacts:
    needs:
      - release-prerequisites
      - golang-build
    runs-on: ubuntu-latest
    permissions:
      contents: write
    steps:
      - # [...] See https://github.com/thetillhoff/action-release-artifacts
      - uses: thetillhoff/action-goreportcard-refresh@v1.0.1
```
