# AreWeNullYet

This action collects every csrpoj and checks the ratio of files which currently enable nullable

## Inputs

### root-path

#### Default: . ( current working directory)

Root directory to look for `.csproj` files

### pattern

#### Default: .csproj

Glob-Pattern of projects to check

## Outputs

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
        id: gitClone
        uses: actions/checkout@v4

      - name: Assert nullability
        uses: crashdummyy/arewenullyet-gh@master
        with:
          root-path: './src'
          pattern: '*NotLegacy*.csproj'
````
