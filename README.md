# Metabolomics Identification Report Standards

Metabolomics feature identification report industry standards from BioNovoGene corporation.

## Purpose


## Report Table Format

### section1: basic info and ms1 parent ion

| field   | type | description |
|---------|------|-------------|
| ID      |      |             |
| mz      |      |             |
| rt      |      |             |
| rtmin   |      |             |
| rtmax   |      |             |
| ms2n    |      |             |
| maxinto |      |             |
| index   |      |             |
| feature |      |             |

### section2: annotation information

In this section, includes three parts of annotation information to describ the resulted metabolite.

| field      | type | description |
|------------|------|-------------|
| BioDeepID  |      |             |
| name       |      |             |
| exact_mass |      |             |
| formula    |      |             |

| field   | type | description |
|---------|------|-------------|
| KEGG    |      |             |
| hmdb    |      |             |
| pubchem |      |             |
| chebi   |      |             |
| CAS     |      |             |
| metlin  |      |             |

| field               | type | description |
|---------------------|------|-------------|
| InChIKey            |      |             |
| InChI               |      |             |
| SMILES              |      |             |
| kingdom             |      |             |
| super_class         |      |             |
| class               |      |             |
| sub_class           |      |             |
| molecular_framework |      |             |

### section3: annotation score

| field          | type | description |
|----------------|------|-------------|
| libname        |      |             |
| library        |      |             |
| lib.mz         |      |             |
| precursor_type |      |             |
| ppm            |      |             |
| forward        |      |             |
| reverse        |      |             |
| shared_forward |      |             |
| shared_reverse |      |             |
| pct1           |      |             |
| pct2           |      |             |
| mirror         |      |             |
| rt.adjust      |      |             |
| supports       |      |             |
| supports.score |      |             |

| field          | type | description |
|----------------|------|-------------|
| pvalue         |      |             |
| FDR            |      |             |
| algorithm      |      |             |
| identify.level |      |             |


