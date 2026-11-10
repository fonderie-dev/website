---
title: "Méthode"
description: "How Fonderie works: open weights, run records, artefacts, safe loading and licensing."
lede: "The rules every atelier follows. They are written before the code, so the code can be held to them."
---

## Open weights, local first

Work starts from models whose weights and licence permit inspection,
modification and local use. Training and evaluation run on hardware under our
control. Hosted model APIs are not part of the chain unless a task definition
requires one explicitly.

## The run record

Every training, editing or evaluation run writes a record next to its outputs.
A result that cannot be traced to its record is not reported.

| Field | Content |
|---|---|
| Base model | Identifier and revision as a commit hash, never a branch name |
| Data | Manifest of every input file with its SHA-256 checksum |
| Configuration | The configuration file, under version control, and its commit |
| Seeds | Every random seed the run used |
| Software | Package versions, Python version, driver and CUDA version |
| Hardware | Accelerator model and count, memory |
| Time | Start and end, in UTC |
| Outputs | Every output file with its checksum |

## Weights are artefacts, not source

Checkpoints, datasets, caches and run directories stay out of git. Released
artefacts go to an archive with a persistent identifier and a model card that
names the base model, the data, the record and the known limitations.

## Safe loading

Weights are read from `safetensors`. Pickle-based formats (`.bin`, `.pt`,
`.pth`, `.ckpt`, `.pkl`) can execute code when loaded; they are opened only
from a trusted source. `trust_remote_code` stays off unless the remote code has
been reviewed and its revision pinned. Model and dataset downloads are pinned
to a commit hash.

## Licensing and memorisation

A fine-tuned model inherits obligations from its base model and from its
training data. Open-weight licences differ in what they permit; they are
checked before training and again before release.

Models can memorise and reproduce training examples. Weights, adapters and
generated samples from a model trained on restricted or personal data carry
that data's restrictions and are not published. Evaluation items used for a
reported result must not appear in the training data, and the check that
established this is part of the record.

## Status scale

Each atelier shows a status stamp. It describes the code in the repository,
not an ambition.

| Stamp | Meaning |
|---|---|
| ○○○ scaffold | The package installs and its smoke test passes; the scope is not implemented. |
| ●○○ draft | Parts of the scope work and are tested; interfaces may change. |
| ●●○ usable | The stated scope works and is tested; a release is being prepared. |
| ●●● released | A versioned release is archived with a persistent identifier. |
