# Metabolomics Identification Report Standards

Metabolomics feature identification report industry standards from BioNovoGene corporation.

## Purpose


## Report Table Format

### section1: basic info and ms1 parent ion

| field   | type    | description                                                                                      |
|---------|---------|--------------------------------------------------------------------------------------------------|
| ID      | name    | The unique id of current ion, which can be generated from ``xcms`` R package                     |
| mz      | double  | m/z ratio of the ion in ms1 result                                                               |
| rt      | double  | rt in seconds of the ion in liquid chromatography result                                         |
| rtmin   | double  | rt its lower bounds of the ion peaks                                                             |
| rtmax   | double  | rt its upper bounds of the ion peaks                                                             |
| ms2n    | integer | Number of ms/ms spectrum that matched by current ms1 ion                                         |
| maxinto | double  | The max intensity of current ion between samples                                                 |
| index   | name    | The row index                                                                                    |
| feature | name    | The feature of the best ms/ms spectrum in raw file, in format like: ``rawfile_name#scan_number`` |

### section2: annotation information

In this section, includes three parts of annotation information to describ the resulted metabolite.

#### part1. the basic meta information

| field      | type   | description                                                   |
|------------|--------|---------------------------------------------------------------|
| BioDeepID  | term   | A unique database reference id of current assigned metabolite |
| name       | name   | The common name of the assigned metabolite                    |
| exact_mass | double | The exact mass of the assigned metabolite                     |
| formula    | term   | The chemical formula of the assigned metabolite               |

#### part2. the external database cross reference id

| field   | type | description                                |
|---------|------|--------------------------------------------|
| KEGG    | term | The KEGG id                                |
| hmdb    | term | The HMDB main id                           |
| pubchem | term | The pubchem compound id (not substrate id) |
| chebi   | term | The chebi main id                          |
| CAS     | term | The CAS registry number                    |
| metlin  | term | The metlin metabolite id                   |

#### part3. the chemical structure information of target

| field               | type | description                                                                                        |
|---------------------|------|----------------------------------------------------------------------------------------------------|
| InChIKey            | name | The hash key of the InChI calculate result                                                         |
| InChI               | name | The InChI identifier of the molecule structure of current metabolite                               |
| SMILES              | name | The SMILES string of the molecule structure of current metabolite                                  |
| kingdom             | term | The chemical structure classify result in *kingdom* level from ``ClassyFire`` database             |
| super_class         | term | The chemical structure classify result in *super class* level from ``ClassyFire`` database         |
| class               | term | The chemical structure classify result in *class* level from ``ClassyFire`` database               |
| sub_class           | term | The chemical structure classify result in *sub class* level from ``ClassyFire`` database           |
| molecular_framework | term | The chemical structure classify result in *molecular framework* level from ``ClassyFire`` database |

### section3: annotation score

This section of data consist with two parts of information. First part of the information is the alignment information for the metabolite identification, includes: the reference standard source trace in the reference library, and multiple dimensions of the scores of current identification.

| field          | type   | description                                                                                                |
|----------------|--------|------------------------------------------------------------------------------------------------------------|
| libname        | name   | The best alignment its unique id in mass spectrum reference library                                        |
| library        | name   | The library name                                                                                           |
| lib.mz         | double | The m/z ratio value of the ion in reference library                                                        |
| precursor_type | term   | The ``precursor type`` calculation result base on the sample mz and the exact mass value                   |
| ppm            | double | The ppm value between sample mz and target reference libibrary mz                                          |
| forward        | double | The ``query vs reference`` SSM socre                                                                       |
| reverse        | double | The ``reference vs query`` SSM score                                                                       |
| shared_forward | double | The number of shared fragment in direction ``query vs reference``                                          |
| shared_reverse | double | The number of shared fragment in direction ``reference vs query``                                          |
| pct1           | double | The shared fragment ratio in direction ``query vs reference``                                              |
| pct2           | double | The shared fragment ratio in direction ``reference vs query``                                              |
| mirror         | double | The mirror score between query and reference                                                               |
| rt.adjust      | double | The robust rt adjustment score between sample and reference                                                |
| supports       | double | The spectrum alignment supports count of current metabolite cross over multiple standard spectrum database |
| supports.score | double | The ratio of supports against the max likelihood supports score                                            |

And then, is the final identification confidence result for current alignment.

| field          | type   | description                                                                                                         |
|----------------|--------|---------------------------------------------------------------------------------------------------------------------|
| pvalue         | double | The max likelihood hyper-geometric pvalue test result                                                               |
| FDR            | double | FDR controls of the pvalue                                                                                          |
| algorithm      | enum   | The algorithm name for produce current identification score: ``SSM``/``shared_hits``/``metaDNA``                    |
| identify.level | enum   | The confidence level of current identification result: ``confirm``, ``MSMSconfirmed``, ``MSMScheck`` and ``ms2hit`` |


