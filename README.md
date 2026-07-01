# Parallelium Multilingual Alignment Dataset

*Where historical variation meets multilingual alignment.*

This repository presents a curated collection of **multilingual texts** aligned through manual and semi-manual workflows, **including scriptural materials and medieval prose**. It is intended for cross-lingual representation learning and for the fine-tuning or domain adaptation of multilingual models such as [LaBSE](https://arxiv.org/pdf/2007.01852) to historical and pre-standardized textual data.

Unlike many modern corpora, this dataset exposes models to:

- non-standardized spelling
- strong linguistic variation
- non-literal translation practices
- historically variable textual traditions


This makes it particularly suitable for studying **robust multilingual representations** in historical and pre-standardized textual settings, in conditions that differ significantly from modern benchmarks.



## Why This Dataset?

Most existing parallel or alignment-oriented corpora focus on **modern, standardized languages**.

Historical and pre-standardized texts introduce specific challenges:

- orthographic instability
- linguistic heterogeneity
- non-literal translation practices
- narrative or textual restructuring
- variation across textual traditions

Existing resources are often:

- small
- domain-restricted
- weakly aligned
- or not designed for model adaptation and evaluation

This project provides a **curated multilingual alignment dataset** combining scriptural materials and medieval prose, designed to support cross-lingual representation learning, LaBSE fine-tuning, and robustness evaluation on historical textual data.



## From Scriptural Parallel Corpora to Narrative Prose

This repository brings together two complementary resources:

- **scriptural parallel corpora**
- a smaller dataset of **narrative prose**

The scriptural corpora provide multilingual data that is:

- structurally stable
- inherently parallel
- relatively standardized

These properties make them well suited for alignment-oriented experiments.

The prose dataset extends this setting to more structurally variable narrative texts, where:

- translations may be non-literal
- events can be reordered
- discourse structure may vary significantly
- semantic equivalence does not always correspond to direct structural alignment

Together, these resources support the study of multilingual textual alignment across both highly standardized parallel corpora and more divergent narrative prose.



## Language Coverage

This repository brings together multilingual textual resources across a broad range of linguistic traditions, while placing particular emphasis on **medieval Romance languages**.


### Medieval Romance traditions

French · Catalan · Portuguese · Castilian · Occitan · Italian · Aragonese · Venetian · Galician-Portuguese

### Germanic tradition

Middle English

### Latin traditions

Latin · Medieval Latin

### Additional scriptural traditions represented

Including Greek (Septuagint) and Arabic


## Data Documentation

The datasets are distributed as JSON files, but their internal structure differs depending on the corpus.

Detailed documentation for each corpus is available in the `docs/` directory, where users can find information about:

- file organization
- corpus sources and source-text availability
- metadata fields
- alignment structure
- dataset statistics
- segmentation or alignment units
- corpus-specific conventions and limitations

Because the repository combines different types of aligned material, corpus-level documentation should be consulted for details on structure, coverage, sources, and licensing constraints.


## Objective and Use Cases

This dataset is designed to support multilingual representation learning, historical NLP, and the fine-tuning or evaluation of cross-lingual alignment models.

It is particularly suited for experiments aiming to:

- improve semantic alignment across languages and textual traditions
- handle historical and pre-standardized language variation
- evaluate multilingual models beyond literal translation settings
- fine-tune or adapt multilingual sentence embedding models
- test robustness on scriptural and medieval prose materials
- study multilingual text alignment across structurally different corpora

## Intended Audience

This dataset may be useful for:

- NLP researchers working on low-resource, historical, or cross-lingual alignment
- digital humanists studying multilingual translation, textual reuse, or textual variants
- scholars exploring textual transmission across religious, linguistic, and historical traditions

## Scope and Limitations

This dataset is intended for computational experiments in multilingual representation learning, model adaptation, and alignment evaluation.

It is not a substitute for philological alignment, critical editing, or scholarly textual collation. During manual alignment, textual segments may be adjusted or non-alignable material may be omitted.


## Status

This repository is under development. Corpus coverage, metadata, and alignment files may be updated as new texts become available or as existing alignments are revised.


## Contributing

Contributions are welcome.

You can contribute by:

- opening an issue to report errors, inconsistencies, or missing metadata
- providing usable source texts or witnesses for additional languages and textual traditions
- submitting a pull request with corrections, new alignments, new texts, or documentation improvements


## Related Projects

This repository is part of a broader ecosystem of tools and corpora developed for the study of medieval multilingual textual traditions:

- [Aquilign](https://github.com/ProMeText/Aquilign)  
  A clause-level multilingual alignment engine based on contextual embeddings (LaBSE), designed specifically for premodern texts.

- [Multilingual Segmentation Data](https://github.com/ProMeText/multilingual-segmentation-data)  
  Source texts and segmented versions in multiple medieval Romance languages, as well as Latin and English, used for training and evaluating clause segmentation models.


## Citation

Please cite the repository when using the dataset, alignment metadata, or derived files in publications, models, or downstream experiments.

```bibtex
@misc{parallelium_multilingual_alignment_dataset_2026,
  title        = {Parallelium: A Multilingual Alignment Dataset for Scriptural and Medieval Narrative Texts},
  author       = {Ing, Lucence and Levenson, Matthias Gille and Macedo, Carolina},
  year         = {2026},
  howpublished = {GitHub repository}
}
```

## License

The alignment metadata produced for this dataset are distributed under the [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/) license, unless otherwise specified.

> ⚠️ Some **source texts**—including certain medieval Bible translations, the Qur’anic corpus, and some critical editions—are **not redistributed** in this repository due to third-party copyright restrictions.  

> Please refer to the documentation or the original editions for licensing information on specific versions.


## Funding

This work benefited from national funding managed by the **Agence Nationale de la Recherche** under the *Investissements d'avenir* programme with the reference **ANR-21-ESRE-0005 (Biblissima+)**.

> Ce travail a bénéficié d'une aide de l’État gérée par l’**Agence Nationale de la Recherche** au titre du programme d’**Investissements d’avenir** portant la référence **ANR-21-ESRE-0005 (Biblissima+)**.

<p align="center">
  <img src="https://github.com/user-attachments/assets/915c871f-fbaa-45ea-8334-2bf3dde8252d" alt="Biblissima+ Logo" width="600"/>
</p>

