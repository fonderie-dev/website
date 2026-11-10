---
title: "Burin"
gloss: "engraving"
weight: 2
status: 0
repo: "fonderie-dev/fonderie-burin"
site: "https://fonderie-dev.github.io/fonderie-burin/"
summary: "Inspecting and editing the weights of open models."
etymology: "A burin is the engraver's chisel, used to cut fine lines into finished metal."
---

## Intended scope

- Read `safetensors` checkpoints lazily and report per-tensor shape, dtype and
  summary statistics without loading the whole model into memory.
- Compare two checkpoints of the same architecture, for example a base model
  and its fine-tune from [Affinage](../affinage/), layer by layer.
- Targeted edits (rescaling, zeroing, replacing or merging tensors) written to
  a new checkpoint, with a record of every change and the checksums of input
  and output.
- Confirm that an edited checkpoint still loads with the expected shapes.

## Not in scope

Training ([Affinage](../affinage/)); judging whether an edit helps
([Essai](../essai/)). Pickle-based checkpoints are not read; see
[safe loading](../../methode/#safe-loading).

## First milestones

1. Tensor inventory and statistics for a `safetensors` file.
2. Checkpoint comparison report.
3. Recorded edits with a change log that allows the edit to be reversed.
