---
id: development
lastUpdated: 2026-03-10
owner: 74046732+aireilly@users.noreply.github.com
title: Getting started with LLM Compressor docs
type: docs
description: Learn how to set up, build, serve, or generate the LLM Compressor documentation site locally with the docs Makefile.
tags:
  - documentation
  - build
  - mkdocs
  - local-development
  - makefile
---
# Getting started with LLM Compressor docs

```bash
cd docs
```

- Install the dependencies:

```bash
make install
```

- Clean the previous build (optional but recommended):

```bash
make clean
```

- Generate docs content (files, API references, and navigation):

```bash
make gen
```

- Serve the docs locally (runs `gen` automatically):

```bash
make serve
```

This will start a local server. You can now open your browser and view the documentation.

- Build the static site (runs `gen` automatically):

```bash
make build
```

- List all available targets:

```bash
make help
```