---
title: "Essai"
gloss: "assay"
weight: 3
status: 0
repo: "fonderie-dev/fonderie-essai"
summary: "Reproducible evaluation of models on scientific tasks."
etymology: "An essai is the assay: the test that establishes what a casting actually contains."
---

## Intended scope

- Task definitions as versioned files: inputs, references, metric, and the
  exact prompt or scoring procedure.
- Runs against a model pinned to a commit hash, with fixed seeds and decoding
  settings, producing a [run record](../../methode/#the-run-record) and
  per-item outputs.
- Checks for overlap between evaluation items and a training manifest from
  [Affinage](../affinage/).
- Comparison across models, revisions and [Burin](../burin/) edits, reported
  with uncertainty intervals rather than single numbers.

## Not in scope

A public leaderboard; evaluation through hosted model APIs unless a task
definition requires it explicitly.

## First milestones

1. Task-file format and validator.
2. Deterministic evaluation of a tiny local model on a synthetic task, inside
   the test suite.
3. Result comparison with bootstrap intervals.
