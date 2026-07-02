# An aligned scriptures dataset

## Overview

> A multilingual corpus of aligned Biblical and Qur’anic texts — spanning medieval and modern languages — designed for computational and philological alignment tasks.  
> It serves as a benchmark dataset for multilingual alignment of historical religious texts.

This README documents the Biblical and Qur’anic alignment dataset, composed primarily of medieval texts gathered from diverse external sources. Selected modern editions are also included to increase linguistic diversity and improve the robustness and generalizability of sentence alignment models.

The dataset includes over **48,000 aligned verses** and more than **4 million verse-level pairs**, covering **29 versions** in **9 languages**. The corpus spans both **medieval** and **modern** textual traditions.

> 📌 Each aligned verse includes two or more versions. Pair counts reflect all _n choose 2_ version pairs per verse.

➡️ See [Biblical alignment challenges](biblical_alignment_challenges.md) for notes on structural complexity, exclusions, and philological variation.

> 📢 **Important Notice on Licensing**  
> This repository includes *only alignment metadata*. Some source texts, especially medieval Bible translations and the Qur’anic corpus, are **not redistributed** due to licensing restrictions.  
> Please consult the documentation for access or citation of original sources.


## Dataset Overview

| Feature            | Biblical Corpus                                                                                   | Qur’anic Corpus                                                                 |
|--------------------|---------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------|
| **Text Types**     | Biblical texts (medieval and selected modern editions)                                            | Qur’anic translations in historical European languages and Arabic                 |
| **Languages**      | Latin, French, English, Castilian, Catalan, Italian, Portuguese, Greek                            | Arabic, Latin, English, French, Italian                                           |
| **Alignment Unit** | Verse-level (approximating sentence or clause)                                                    | Verse-level (based on surah:ayah structure)                                       |
| **Format**         | JSON                                                                                              | JSON                                                                              |
| **Use Case**       | Training multilingual alignment models *(not for textual criticism)*                              | Training multilingual alignment models *(not for religious or exegetical use)*    |
| **Aligned Verses** | 42,562                                                                                            | 6,236                                                                             |
| **Aligned Pairs**  | 3,927,811                                                                                          | 114,226                                                                           |



## Data Sources

The Biblical and Qur’anic texts were selected for their **structural compatibility** — namely, their verse-based (or surah:ayah in the case of the Qur’an) organization — and their widespread **cross-linguistic transmission**, which enables meaningful alignment across centuries and traditions.


### Medieval Bibles

| Language | Text                        | Source                                                                                                                                                                           | Format        |
|----------|-----------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------|
| en       | John Wycliffe Bible         | [GitHub](https://github.com/saibotsivad/john-wycliffes-bible/tree/master/raw-text)                                                                                              | `.txt`        |
| en       | Coverdale Bible             | [GitHub](https://github.com/Isidore-Guild/coverdale)                                                                                                                             | `.xml`        |
| en       | Great Bible                 | [EDGeS Corpus](https://spraakbanken.gu.se/en/resources/openedges)                                                                                                                | `.tsv`        |
| it       | Gospel of St. Matthew       | [Caterina Menichetti Edition](https://www.sismel.it/pubblicazioni/2059-il-vangelo-secondo-matteo-in-volgare-italiano-studio-ed-edizione-critica-delle-due-versioni-non-glossate)            | `.pdf`        |
| fr       | La Bible historiale         | [Project site](https://www.biblehistoriale.fr/index.php/xml-tei/)                                                                                                                | `.xml`        |
| fr       | Esther, Judith, Ruth        |Texts kindly provided by Claudio Lagomarsini                                                                                                                                                | Word\*        |
| fr       | Gospel of Matthew           |Transcription kindly provided by Seth Middleton                                                                                                                                                | `.txt`\*      |
| gr       | Septuagint (LXX)            | [Corpus Corporum](https://mlat.uzh.ch/browser?path=/17098/17099/17113/17110/17104)                                                                                               | `.xml`        |
| es       | Three Medieval Bibles       | [Proyecto Biblia Medieval](https://bibliamedieval.es/recursos/textos)                                                                                                            | `.txt`        |
| ca       | Three Medieval Bibles       | Texts kindly provided by Pere Casanellas [(Corpus Biblicum Catalanicum)](https://cbcat.abcat.cat/)                                                                                                       | `.xml`, Word\*|
| la       | Vulgata Sixto-Clementina    | [GitLab](https://gitlab.com/crosswire-bible-society/vulgate/-/blob/master/vulgate.osis.xml?ref_type=heads)                                                                      | `.xml`        |

> \* *These texts are not publicly shareable due to copyright restrictions.*

## Credits

We gratefully acknowledge the following scholars and institutions for their contributions of source material or expertise:

- **Pere Casanellas (Corpus Biblicum Catalanicum)** – Catalan biblical texts based on the Egerton, Peiresc, and Colbert manuscripts  
- **Claudio Lagomarsini** – Provided French texts of *Esther*, *Judith*, and *Ruth* (Bible du XIIIe siècle)  
- **Mouhamadoul-Khaly Wélé** – Multilingual aligned dataset based on the Quran  
- **Seth Middleton** – French transcription of the Gospel of *Matthew* (Bible du XIIIe siècle)  


### Modern Editions

Nine Bibles in French, English, Portuguese, Greek, and Spanish from [this repository](https://github.com/thiagobodruk/bible), used to augment language diversity.

➡️ For preprocessing and integration steps, see [alignment_workflow.md](alignment_workflow.md).


### Qur’an

Multilingual alignment produced by the **[Coran 12-21](https://coran12-21.org/fr) project** — co-directed by **Mouhamadoul-Khaly Wélé and Tristan Vigliano** — covering 7 languages (Arabic, Latin, English, French, Italian, etc.), with texts kindly provided by Mouhamadoul-Khaly Wélé.
*Note: This resource is not publicly redistributable.*


## Data Format

The dataset is stored in structured JSON files:

- **Monolingual format**: dictionary of `{book → list of {ref, text}}`
- **Multilingual format**: list of aligned verses, each with `book`, `ref`, and a `data` map of translations

➡️ See [data_structure.md](data_structure.md) for full examples and schema.

## 🔍 Alignment Preview (Biblical Corpus)

The snippet below illustrates how to explore aligned verse pairs in the JSON file.  
Each verse contains a `book`, `ref`, and a `data` dictionary mapping version IDs to verse translations.

```python
import json

with open("aligned_data.json") as f:
    data = json.load(f)

# Display all aligned French–Portuguese verse pairs from Genesis
#  Change language IDs below based on your alignment interest
for verse in data:
    if verse["book"] == "genesis":
        fr = verse["data"].get("fr_lsegond")
        pt = verse["data"].get("pt_almeida")
        if fr and pt:
            print(f'{verse["ref"]}:\nFR: {fr}\nPT: {pt}\n')
```
Note: aligned_data.json is not distributed due to licensing.
Use this example to preview the data format and structure.

