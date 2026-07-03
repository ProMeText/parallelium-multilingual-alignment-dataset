# Medieval Prose Corpus

**Quality over scale: this corpus captures rich semantic variation in challenging multilingual settings.**

This folder documents the medieval prose component of the **Parallelium multilingual alignment dataset**.

The medieval prose corpus contains aligned narrative texts in several medieval languages. Unlike scriptural corpora, where verse structures provide relatively stable alignment units, medieval prose often involves freer translation practices, narrative restructuring, expansions, omissions, and substantial linguistic variation.

The corpus is designed to support experiments in multilingual alignment, historical NLP, and cross-lingual representation learning on pre-standardized textual material.


## Contents

| File | Description |
|------|-------------|
| [`corpus_sources.csv`](corpus_sources.csv) | Source information for the medieval prose texts, including language, work, edition, availability, and licensing notes where relevant. |
| [`data_collection.md`](data_collection.md) | Notes on text collection, source preparation, and preprocessing decisions. |
| [`alignment_guidelines.md`](alignment_guidelines.md) | Alignment methodology and editorial principles used for semantic narrative-unit alignment. |
| [`data_structure.md`](data_structure.md) | Description of the JSON structure used for medieval prose alignment files. |
| [`dataset_statistics.md`](dataset_statistics.md) | Corpus statistics, including counts by work, language, version, and alignment unit where available. |


## Overview

The medieval prose corpus is aligned at the level of **semantic narrative units** rather than strictly at the sentence level.

A narrative unit corresponds to a coherent event, action, or semantic segment. It may coincide with a sentence, but it can also be shorter or longer depending on the structure of the source texts and their translations.

This approach is intended to capture meaningful semantic correspondences across texts that are not always structurally parallel.

## Why Medieval Prose?

Medieval prose introduces challenges that are less visible in more regular parallel corpora.

These include:

- non-literal translation practices
- additions, omissions, and paraphrases
- reordered narrative sequences
- uneven correspondence between sentences and semantic units
- strong linguistic and dialectal variation
- non-standardized spelling and historical orthographic variation

Because of these features, medieval prose provides a useful test case for evaluating how multilingual models handle semantic equivalence under conditions of historical and textual variation.

## Use Cases

The corpus may be used to:

- evaluate multilingual sentence embedding models on historical textual material
- fine-tune or adapt multilingual models to pre-standardized language
- test alignment methods under strong linguistic and textual variation
- study semantic correspondence across medieval translations and textual traditions
- compare alignment behavior between scriptural and narrative corpora



## Usage Example

The following example recursively reads JSON files and prints their aligned units:

```python
import json
from pathlib import Path

data_dir = Path("data")

for json_file in data_dir.rglob("*.json"):
    with open(json_file, encoding="utf-8") as f:
        data = json.load(f)

    work = data.get("work", json_file.stem)
    alignments = data.get("alignement_id", {})

    print(f"\nWork: {work}")
    print(f"File: {json_file}")

    for alignment_id, groups in alignments.items():
        print(f"\nAlignment unit: {alignment_id}")

        for group in groups:
            for lang, text in group.items():
                print(f"{lang}: {text}")
            print()
```

Adjust the data_dir path depending on where the repository is being accessed from.

## Limitations

Several limitations should be kept in mind when using the medieval prose corpus.

The dataset is limited in scale because segmentation and alignment require manual validation. It is therefore not intended to compete with large automatically generated parallel corpora.

Alignment at the level of narrative units also involves interpretative decisions, especially when texts diverge structurally or when translations expand, omit, or reorder material.

The corpus is shaped by the availability of suitable medieval witnesses and translations, which may lead to imbalances in language coverage, genre, and textual tradition.