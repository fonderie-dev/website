---
title: "À propos"
description: "About Fonderie, its name and its conventions."
lede: "Fonderie is a workshop for AI model engineering in science, maintained by R. Heller."
---

## What it is for

Scientific work increasingly depends on models whose training data, weights
and evaluation are opaque. Fonderie takes the opposite route: start from open
weights, adapt them to a domain, look inside them, and measure them in a way
that someone else can repeat. The aim is customised local models whose
provenance is on record.

Fonderie sits beside two other projects by the same maintainer:
[CTTIR](https://cttir.github.io/website/), computational trauma and tissue
injury research, and [Établi](https://github.com/etabli-dev), tools for
research and local knowledge work.

## The name

A *fonderie* is a foundry. Each repository takes its name from the foundry
trade, written `fonderie-<mot>` without accents.

| Word | Meaning | Use |
|---|---|---|
| *affinage* | refining | [Affinage](../ateliers/affinage/): training and fine-tuning |
| *burin* | engraver's chisel | [Burin](../ateliers/burin/): weight inspection and editing |
| *essai* | assay | [Essai](../ateliers/essai/): evaluation |
| *coulée* | casting | reserved |
| *creuset* | crucible | reserved |
| *moule* | mould | reserved |
| *alliage* | alloy | reserved, for model merging |
| *lingot* | ingot | reserved, for a packaged model |
| *trempe* | quench | reserved |
| *poinçon* | hallmark | reserved |

## Conventions

The ateliers are Python packages (≥ 3.11) with a `src/` layout, tested with
pytest and linted with ruff through a shared workflow. Tests use tiny
synthetic models and run without a GPU or downloads. The full house style is
in the [contributing guide](https://github.com/fonderie-dev/.github/blob/main/CONTRIBUTING.md);
data protection and model-file handling are in the
[security notes](https://github.com/fonderie-dev/.github/blob/main/SECURITY.md).

## Contact and licence

Questions and proposals go to the issue tracker of the relevant repository on
[GitHub](https://github.com/fonderie-dev). Code is released under Apache-2.0
unless a repository states otherwise; model weights and datasets keep their
own licences.
