# Dataset Documentation

This directory contains corpus-level documentation for the dataset components of the **Parallelium multilingual alignment dataset**.

The documentation is organized into two main corpus areas: the scriptural corpus and the medieval prose corpus. Each subfolder provides information on source materials, data structure, alignment choices, and corpus-specific limitations.

## Contents

| Folder | Description |
|--------|-------------|
| [`bibles/`](bibles/) | Documentation for the scriptural corpus, including Biblical and Qur’anic alignment data, source materials, alignment guidelines, data structure, and statistics. |
| [`medieval_prose/`](medieval_prose/) | Documentation for the medieval prose corpus, including source materials, preprocessing choices, semantic narrative-unit alignment, and corpus-specific notes. |

## Corpus Relationship

The two corpus components are complementary.

The scriptural corpus provides relatively stable alignment units, especially through Biblical verse references and Qur’anic surah:ayah structures. These reference systems make it possible to compare multilingual textual traditions within a shared structural framework.

The medieval prose corpus extends the dataset to a more variable setting. In this case, alignment cannot rely on fixed reference systems alone, since translations may involve restructuring, expansion, omission, or reordered narrative sequences. Alignment therefore requires semantic segmentation and manual validation.

Together, these components make it possible to compare multilingual alignment across:

- structurally stable scriptural corpora
- semantically aligned but structurally divergent narrative prose





