---
layout: docs
title: Import
parent: Imports
nav_order: 5
lang: en
permalink: /docs/imports/import/
description: Committing is a separate, deliberate act — gated, journalled, and reversible.
---

# Import

<p class="lede">Commit the import — a deliberate, reversible act that never happens by accident.</p>

Committing the import is a **separate, deliberate act**, not something that
happens on its own when the dry run finishes. Before it will run, two things
must be true: a dry-run report must exist, and the mapping profile must be
unchanged since that report. Edit the profile after a dry run, and Fisqua asks
for a fresh dry run first.

To commit, you write a **required run message** (and an optional justification),
pick the **repository** new records are filed under, and confirm you have
**reviewed the report**.

<figure>
  <img src="{{ '/assets/img/imports-import-en.png' | relative_url }}" alt="The import step: the run message, repository selector, and the review confirmation that arms the commit button.">
  <figcaption>The import step: a run message, the repository to file records under, and the review confirmation.</figcaption>
</figure>

## The button never refuses silently

While anything is still missing, the commit button is **disabled and names its
reason** in a line beneath it — no dry-run report yet, decisions pending, a
profile changed since the report, or no repository to file new records under. Where the
fix lives elsewhere, the reason **links there**: a workspace with no repository
gets a link that explains what a repository is, takes you to create one, and
hands you back to the commit form where you left it.

## What the import does

The import reads every row again, straight from your staged file — the dry-run
report guided your decision, but it is never what gets written. It works through
the rows steadily, and if it is interrupted it picks up where it left off
without importing anything twice.

Records are **created or updated, never deleted**, matched by reference code.
Updates are careful:

- a **blank cell keeps** the existing value,
- **older identifiers are kept** alongside the new ones, nothing dropped, and
- a row that already matches is **left untouched** and counted as unchanged.

An import **never re-files an existing record**: if the file gives a record a
different parent, the report says so, but the import leaves it where it is. Each
upload is imported **once**.

Every change is **recorded together with the value it replaced**, and that
record is what lets you undo the import.
