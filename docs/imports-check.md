---
layout: docs
title: Check
parent: Imports
nav_order: 3
lang: en
permalink: /docs/imports/check/
description: The check surfaces every issue your file will cause before anything runs.
---

# Check

<p class="lede">Every issue your file will cause, surfaced before anything runs.</p>

Before anything runs, the check reads your staged file against the chosen
mapping profile and the live catalogue, and surfaces every issue the import
would cause — grouped **by problem class** rather than row by row, so a fault in
a thousand rows is one thing to decide, not a thousand.

<figure>
  <img src="{{ '/docs-assets/img/imports-check-en.png' | relative_url }}" alt="The check screen listing findings grouped by problem class, each with its options.">
  <figcaption>The check groups findings by class and states the options for each.</figcaption>
</figure>

## The three kinds of finding

Each class arrives with its options already stated, so you are never left
guessing what to do about it:

- A **blocking** finding names rows that can't be imported as they stand — a
  duplicate reference code, or a parent that can't be found in the file or the
  catalogue. Those rows will be rejected unless you fix the file and upload
  again. It does not hold up the dry run; the named rows simply reject.
- A **decision** finding asks you to choose, and is the only kind that holds up
  the dry run. The common case is a required field that some rows leave blank:
  you either accept the gap or go back and improve the file. The dry run stays
  locked until every decision is answered.
- An **informational** finding just explains something you should know; it
  blocks nothing.

## Accepting a gap is never silent

When you accept a gap, it does not disappear. The affected rows import with the
gap recorded as a **named warning** in every later report, and the acceptances
themselves are stored on the upload and copied into the run's permanent record
when the import is committed — so a later reader can always see what was waved
through, and why.

Some failures can never be accepted. A **broken identifier** — a blank or
duplicate reference code, an unresolvable parent — always rejects the row,
because letting one in would damage how the catalogue fits together, rather than
merely leave a field thin.

## Checks are cached

The check result is stored, so the imports landing page can show each
in-progress upload's state without recomputing it. If you edit the mapping
profile after a check has run, that upload returns to **Check pending** — the
old result no longer describes what the current profile would do, and the check
must run again before the dry run can unlock.
