---
layout: docs
title: Runs
parent: Imports
nav_order: 6
lang: en
permalink: /docs/imports/runs/
description: Every committed import is recorded as a run, with its message, author, counts, and downloadable files.
---

# Runs

<p class="lede">Every committed import leaves a permanent record, held within your workspace.</p>

Every committed import is recorded as a **run**. A run carries:

- its **message** and justification,
- its **author**,
- the **mapping profile and version** it used,
- **live progress** while it runs,
- **counts by kind** when it finishes (created, updated, skipped, rejected),
- an **error message** if it fails, and
- links to download the run's **source file, report, and rejects file**.

<figure>
  <img src="{{ '/assets/img/imports-runs-en.png' | relative_url }}" alt="The runs list: each committed import as a row, with its message, author, and outcome.">
  <figcaption>The runs list is the catalogue's import history — what entered, when, and on whose authority.</figcaption>
</figure>

Runs are **kept within the workspace** — one workspace never sees another's. The
runs list is the catalogue's import history: what entered, when, on whose
authority, and against which mapping.
