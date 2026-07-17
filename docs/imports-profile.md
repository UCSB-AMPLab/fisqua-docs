---
layout: docs
title: Profile
parent: Imports
nav_order: 2
lang: en
permalink: /docs/imports/profile/
description: A mapping profile binds your spreadsheet's columns to Fisqua's description fields.
---

# Profile

<p class="lede">Tell Fisqua what your columns mean — once, and reusably.</p>

A **mapping profile** binds your spreadsheet's columns to the workspace's
description fields. Columns are **matched by their header name, never by their
position**, so a re-ordered export still maps correctly. Each column can also be
adjusted on the way in, to fit the shapes real exports arrive in — a column can
be copied as it is, given a fallback value when a cell is blank, set to a fixed
value, joined with other columns, split apart when one cell holds several values,
matched against your controlled vocabulary, read as a date, or carried down from
the row above.

You choose a profile during the [Check](../check/) step, and the check and dry
run both classify every row through it.

<figure>
  <img src="{{ '/docs-assets/img/imports-profile-en.png' | relative_url }}" alt="The mapping profile editor: each source column paired with a description field and a transform.">
  <figcaption>Each source column is paired with a description field, and a transform where the value needs reshaping.</figcaption>
</figure>

## Where a profile comes from

You can build one **from scratch**, or begin from a **starter** for a format you
already hold:

- AtoM's ISAD(G) CSV
- Colombia's AGN FUID inventory
- the Endangered Archives Programme (British Library) listing
- the Modern Endangered Archives Program (UCLA) item-level template

Starters are offered only for the descriptive standards they fit. Picking one
creates an ordinary, editable per-workspace profile and opens it in the editor
for review before first use. Later refinements to a starter never disturb
profiles already created from it.

For a catalogue started from nothing, download the **Fisqua template** — a CSV
generated from the workspace's own descriptive standard, one column per field —
and its matching pre-built profile, so a filled-in template needs no mapping at
all.

## Naming and versions

Profiles are **per-workspace**, named uniquely, and **versioned** — but the
version moves only when the mapping itself changes. This is what lets a dry run
pin the exact profile it was run against: edit the mapping after a dry run, and
that upload returns to check so the report can never describe a mapping that no
longer exists.
