---
layout: docs
title: Upload
parent: Imports
nav_order: 1
lang: en
permalink: /docs/imports/upload/
description: Stage a CSV to begin an import — validated on the way in, nothing silently corrupted.
---

# Upload

<p class="lede">Stage a CSV to begin — validated on the way in, nothing silently corrupted.</p>

An import begins on the imports landing page, by uploading a CSV of your
records. The file is validated as it arrives, and every rejection is **by name**,
so a bad file is turned away with a reason rather than half-imported:

- The file must be saved as **UTF-8** text — the format most tools offer under
  that name. Anything else is turned away, and nothing is staged.
- A file with an **unclosed quote**, **repeated column names**, or **no data
  rows** is turned away before anything is stored.

A valid file is **staged** — the file itself, together with a note of its
details — and the step chain begins. Staging touches nothing in the catalogue;
it only holds the file for the checks ahead.

<figure>
  <img src="{{ '/assets/img/imports-upload-en.png' | relative_url }}" alt="The imports landing page: a CSV upload area, the step chain, and a list of imports in progress.">
  <figcaption>The imports landing page: stage a CSV, and pick up any import already under way.</figcaption>
</figure>

## Discarding and deleting

An upload can be **discarded** at any point before it is imported. Discarding
ends its journey but keeps the file and its record, so an abandoned upload still
leaves a trace. A discarded upload can then be **deleted** outright — the staged
file, everything generated from it, and its record are all removed.

An upload that has **been imported can never be deleted**: it is part of a run's
permanent record, and the record of what entered the catalogue is not something
the interface will let you erase.
