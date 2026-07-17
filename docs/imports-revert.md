---
layout: docs
title: Revert
parent: Imports
nav_order: 7
lang: en
permalink: /docs/imports/revert/
description: A completed import can be undone as a new recorded run — nothing is forced, nothing is erased.
---

# Revert

<p class="lede">Undo a completed import — as a recorded act, never an erasure.</p>

A completed import can be **reverted**: not wiped, but undone as a **new,
recorded run** with its own required message. The revert works back through what
the import did —

- records the import **created** are deleted,
- records it **updated** are restored to the values they had before, and
- every change it makes along the way is **recorded under the revert run**.

Because the revert is itself recorded, it is itself reversible: reverting a
revert re-applies the original import.

<figure>
  <img src="{{ '/assets/img/imports-revert-en.png' | relative_url }}" alt="A revert run's results: counts for deleted, restored, and kept records, with a downloadable revert report.">
  <figcaption>A revert is a recorded run of its own, with honest counts for what it undid and what it kept.</figcaption>
</figure>

## Nothing is forced

A revert never bulldozes work done since the import. It **keeps and reports**:

- a record **edited since** the import is kept, not overwritten,
- a container the import created that has since **gained new records inside it**
  is kept, and
- a **reference code reused** since is blocked from re-creation.

The run's results state the **reverted and kept counts** honestly, by reason,
with a downloadable report. An import can be reverted **once** — there is no
force path, no partial revert, and no merge.
