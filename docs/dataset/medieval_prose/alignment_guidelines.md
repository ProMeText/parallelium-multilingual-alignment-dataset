# Alignment Guidelines

This document describes the alignment methodology and editorial principles used for the medieval prose component of the **Parallelium multilingual alignment dataset**.

The medieval prose corpus is aligned at the level of **semantic narrative units** rather than strictly at the sentence level. A narrative unit corresponds to a coherent event, action, or semantic segment. It may coincide with a sentence, but it can also be shorter or longer depending on the structure of the source texts and their translations.

## Alignment Workflow

The alignment workflow combines automatic or semi-automatic alignment with manual correction.

The general pipeline is:

1. collection and preparation of source texts
2. preprocessing and initial segmentation
3. initial alignment with **Aquilign**
4. manual correction of proposed alignments
5. segmentation into narrative units where necessary
6. final semantic validation

The initial alignment relies on multilingual sentence representations and alignment tools. The final dataset prioritizes manually validated semantic correspondences.

## Alignment Principles

The corpus follows these general principles:

- align units only when they express a clear semantic correspondence
- prioritize semantic equivalence over surface similarity
- allow broader or narrower segment correspondences when required
- treat expansions, omissions, and paraphrases as meaningful textual variation
- avoid forcing alignments where no reliable correspondence exists
- preserve the historical and orthographic form of the texts where possible

The goal is not to normalize medieval texts or impose strict sentence-level parallelism, but to represent meaningful correspondences across divergent textual traditions.

## Non-Alignable Material

Some material may remain unaligned when no reliable semantic correspondence exists, when a passage is unique to one version, or when the relationship between passages is too uncertain.

Leaving material unaligned is preferable to introducing weak or misleading correspondences.