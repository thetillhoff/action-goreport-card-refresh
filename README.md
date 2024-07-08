# Action: Golang build

This action triggers a refresh for your repository on https://goreportcard.com.


Example usage:
```yaml
name: Release Golang Application

on:
  push:
    tags:
    - "v[0-9]+.[0-9]+.[0-9]+"

jobs:
  # [...] Tests etc.

  goreportcard-refresh:
  - uses: thetillhoff/action-goreportcard-refresh@v1.0.0
```
