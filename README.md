# Parallelium Multilingual Alignment Dataset

**Where historical variation meets multilingual alignment.**

Parallelium is a curated multilingual alignment dataset for historical and pre-standardized textual material. It brings together scriptural corpora and medieval prose in order to support experiments in cross-lingual representation learning, sentence alignment, and the adaptation of multilingual models such as [LaBSE](https://arxiv.org/abs/2007.01852) to historical textual data.

Unlike many modern parallel corpora, this dataset exposes models to non-standardized spelling, strong linguistic variation, non-literal translation practices, and historically variable textual traditions.

## Repository Structure

| Path             | Description                                                                                                      |
| ---------------- | ---------------------------------------------------------------------------------------------------------------- |
| [`data/`](data/) | Dataset files and alignment metadata.                                                                            |
| [`docs/`](docs/) | Corpus-level documentation, including source descriptions, data structure, alignment guidelines, and statistics. |
| [`img/`](img/)   | Images and visual material used in the repository documentation.                                                 |

## Dataset Components

The dataset brings together two complementary types of aligned material.

### Scriptural corpus

The scriptural corpus includes Biblical and Qur’anic alignment data. These texts provide structurally stable alignment units, such as Biblical verses and Qur’anic surah:ayah references, making them especially useful for multilingual alignment experiments.

The Biblical corpus includes medieval and selected modern versions in several languages. Qur’anic alignment is referenced in the dataset documentation and statistics, but the corresponding source texts are not redistributed due to licensing constraints.

### Medieval prose corpus

The medieval prose corpus extends the dataset beyond scriptural material to more structurally variable narrative texts. In this setting, translations may be non-literal, events may be reordered, and semantic equivalence does not always correspond to direct structural alignment.

Together, the two components allow users to test alignment models on both relatively stable parallel traditions and more divergent narrative prose.

## Language Coverage

The dataset focuses especially on medieval Romance languages, while also including Germanic, Latin, Greek, and Arabic traditions.

### Medieval Romance traditions

French · Catalan · Portuguese · Castilian · Occitan · Italian · Aragonese · Venetian · Galician-Portuguese

### Germanic tradition

Middle English

### Latin traditions

Latin · Medieval Latin

### Additional scriptural traditions

Greek · Arabic

## Documentation

Detailed documentation is available in [`docs/`](docs/).

The documentation includes information on:

* corpus sources and source-text availability
* file organization
* data structure and metadata fields
* alignment methods and alignment units
* dataset statistics
* corpus-specific conventions and limitations

Because the repository combines different types of aligned material, users should consult the relevant corpus-level documentation before using the data.

## Use Cases

Parallelium is designed for research in multilingual NLP, historical NLP, and digital humanities.

It may be useful for:

* fine-tuning or evaluating multilingual sentence embedding models
* studying semantic alignment across historical languages and textual traditions
* testing model robustness on non-standardized and premodern textual data
* comparing alignment behavior across scriptural and narrative corpora
* supporting research on multilingual translation, textual reuse, and textual transmission

## Scope and Limitations

This dataset is intended for computational experiments in multilingual representation learning, model adaptation, and alignment evaluation.

It is not a substitute for philological alignment, critical editing, or scholarly textual collation. During manual alignment, textual segments may be adjusted and non-alignable material may be omitted.

Some source texts, including certain medieval Bible translations, the Qur’anic corpus, and some critical editions, are not redistributed in this repository due to third-party copyright restrictions. Please refer to the documentation or to the original editions for licensing information on specific versions.

## Status

This repository is under development. Corpus coverage, metadata, and alignment files may be updated as new texts become available or as existing alignments are revised.

## Contributing

Contributions are welcome.

You can contribute by:

* opening an issue to report errors, inconsistencies, or missing metadata
* providing usable source texts or witnesses for additional languages and textual traditions
* submitting a pull request with corrections, new alignments, new texts, or documentation improvements

## Related Projects

This repository is part of a broader ecosystem of tools and corpora developed for the study of medieval multilingual textual traditions:

* [Aquilign](https://github.com/ProMeText/Aquilign): a multilingual alignment and collation engine for historical corpora.
* [Multilingual Segmentation Data](https://github.com/ProMeText/multilingual-segmentation-dataset): source texts and segmented versions in multiple medieval Romance languages, as well as Latin and English, used for training and evaluating clause segmentation models.

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

> ⚠️ Some source texts — including certain medieval Bible translations, the Qur’anic corpus, and some critical editions — are not redistributed in this repository due to third-party copyright restrictions.

> Please refer to the documentation or the original editions for licensing information on specific versions.

## Funding

This work benefited from national funding managed by the Agence Nationale de la Recherche under the Investissements d'avenir programme with the reference ANR-21-ESRE-0005 (Biblissima+).

> Ce travail a bénéficié d'une aide de l’État gérée par l’Agence Nationale de la Recherche au titre du programme d’Investissements d’avenir portant la référence ANR-21-ESRE-0005 (Biblissima+).
