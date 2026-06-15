# AreWeNullYet

This action collects every csproj and checks the ratio of files which currently enable nullable

## Inputs

```yaml
uses: crashdummyy/arewenullyet-gh@master
with:
  # Root directory to look for .csproj files
  # Default: . (current working directory)
  root-path: './src'
  # Path of projects to check for nullability
  # Default: *.csproj
  pattern: '*NotLegacy*.csproj'
```

## Samples

````yaml
name: Are we null yet

on:
  pull_request:
    branches:
      - master

jobs:
  checks:
    runs-on: ubuntu-latest
    steps:
      - name: Clone Repository
        uses: actions/checkout@main

      - name: Assert nullability
        uses: crashdummyy/arewenullyet-gh@master
        with:
          root-path: './src'
          pattern: '*NotLegacy*.csproj'
````
