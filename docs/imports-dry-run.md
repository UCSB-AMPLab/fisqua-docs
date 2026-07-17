---
layout: docs
title: Dry run
parent: Imports
nav_order: 4
lang: en
permalink: /docs/imports/dry-run/
description: The dry run classifies every row without writing anything, and hands you two reports to judge.
---

# Dry run

<p class="lede">See exactly what the import would do — without writing a thing.</p>

The dry run classifies **every row** as a **create, update, skip, or reject**,
without writing anything to the catalogue. It produces two files you can
download:

- a **report** with counts by named reason, and
- a **rejects file** carrying each rejected row's original columns exactly as
  they were, plus its row number and the reason it was turned away.

There is **no automatic pass or fail**. The dry run's job is to let you read and
judge the outcome before committing to it.

<figure>
  <img src="{{ '/assets/img/imports-dry-run-en.png' | relative_url }}" alt="The dry-run report: counts for creates, updates, skips, rejects, and warnings, with a table of rejected rows.">
  <figcaption>The dry-run report — counts by outcome, and every rejected row with its reason.</figcaption>
</figure>

## Why some problems block and others don't

The report treats two kinds of problem differently, on purpose:

- A **broken identifier blocks the row** — a blank reference code, a duplicate
  within the file, a parent that can't be found or was itself rejected, a record
  that ends up its own ancestor, or a value that is too long or invalid. It is
  counted as a reject.
- An **unrecognised description value falls back to a safe default** — and is
  counted as a warning, never blocking.

The reasoning: a broken identifier would damage how the catalogue fits together,
so the row must not enter; a thin or unexpected description is merely incomplete,
and an incomplete record is still a truthful one.

## Update-existing

The **update-existing** choice decides the fate of rows whose reference code
already exists in the catalogue: **off** (the default) skips them; **on** updates
them in place. Re-run the dry run to change the mode and see the new counts.
