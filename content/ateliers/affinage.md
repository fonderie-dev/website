---
title: "Affinage"
gloss: "refining"
weight: 1
status: 0
repo: "fonderie-dev/fonderie-affinage"
summary: "Training and fine-tuning open models on domain data, packaged as customised local models."
etymology: "Affinage is the refining of molten metal: removing impurities until it reaches a specified composition."
---

## Intended scope

- Configuration-driven training and fine-tuning runs of open-weight models,
  full and parameter-efficient (for example LoRA), from a base model pinned to
  a commit hash.
- Data preparation with a manifest and checksums, and a recorded split that
  [Essai](../essai/) can check for train–test overlap.
- A [run record](../../methode/#the-run-record) written next to every output.
- Export of the result as a customised local model: merged `safetensors`
  weights, an adapter, or a quantised file for a local runtime, each with a
  model card.

## Not in scope

Hosted training services; weight inspection and surgery ([Burin](../burin/));
benchmark evaluation ([Essai](../essai/)).

## First milestones

1. Run-record schema and writer, shared in form with Essai.
2. A fine-tuning run on a tiny model and synthetic data that completes on CPU
   inside the test suite.
3. Export with a generated model card.
