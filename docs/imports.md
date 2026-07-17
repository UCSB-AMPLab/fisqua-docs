---
layout: docs
title: Imports
nav_order: 1
has_children: true
lang: en
permalink: /docs/imports/
description: Bring catalogue records into a workspace from a spreadsheet, as a reviewed, reversible operation.
---

# Imports

<p class="lede">Bring catalogue records into a workspace from a spreadsheet — reviewed, and reversible.</p>

The imports module brings catalogue records into a workspace from a CSV, as an
explicit step chain: **Upload → Profile → Check → Dry run → Import**, with a
recorded history and a full **Revert**. Nothing touches the catalogue until the
import step, and every import can be undone.

This section walks each step:

- **[Upload](upload/)** — stage a CSV, validated on the way in.
- **[Profile](profile/)** — bind your columns to Fisqua's description fields.
- **[Check](check/)** — surface every issue before anything runs.
- **[Dry run](dry-run/)** — classify every row, writing nothing.
- **[Import](import/)** — commit the reviewed rows as a recorded run.
- **[Runs](runs/)** — the permanent record of every import.
- **[Revert](revert/)** — undo a completed import, without erasing it.
