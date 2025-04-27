![Version](https://img.shields.io/github/v/release/DCMLab/dvorak_silhouettes?display_name=tag)
[![DOI](https://zenodo.org/badge/383817520.svg)](https://doi.org/10.5281/zenodo.7473576)
![GitHub repo size](https://img.shields.io/github/repo-size/DCMLab/dvorak_silhouettes)
![License](https://img.shields.io/badge/license-CC%20BY--NC--SA%204.0-9cf)


This is a README file for a data repository originating from the [DCML corpus initiative](https://github.com/DCMLab/dcml_corpora)
and serves as welcome page for both 

* the GitHub repo [https://github.com/DCMLab/dvorak_silhouettes](https://github.com/DCMLab/dvorak_silhouettes) and the corresponding
* documentation page [https://dcmlab.github.io/dvorak_silhouettes](https://dcmlab.github.io/dvorak_silhouettes)

For information on how to obtain and use the dataset, please refer to [this documentation page](https://dcmlab.github.io/dvorak_silhouettes/introduction).

When you use (parts of) this dataset in your work, please read and cite the accompanying data report:

_Hentschel, J., Rammos, Y., Neuwirth, M., Moss, F. C., & Rohrmeier, M. (2024). An annotated corpus of tonal piano music 
from the long 19th century. Empirical Musicology Review, 18(1), 84–95. https://doi.org/10.18061/emr.v18i1.8903_

This corpus forms part of the larger [Distant Listening Corpus](https://github.com/DCMLab/distant_listening_corpus)
which constitutes a data infrastructure the data report of which has implications for the present corpus, too:

_Hentschel, J., Rammos, Y., Neuwirth, M., & Rohrmeier, M. (2025). A corpus and a modular infrastructure for the 
empirical study of (an)notated music. Scientific Data, 12(1), 685. https://doi.org/10.1038/s41597-025-04976-z_

# Antonín Dvořák – Silhouettes


## Getting the data

* download repository as a [ZIP file](https://github.com/DCMLab/dvorak_silhouettes/archive/main.zip)
* download a [Frictionless Datapackage](https://specs.frictionlessdata.io/data-package/) that includes concatenations
  of the TSV files in the four folders (`measures`, `notes`, `chords`, and `harmonies`) and a JSON descriptor:
  * [dvorak_silhouettes.zip](https://github.com/DCMLab/dvorak_silhouettes/releases/latest/download/dvorak_silhouettes.zip)
  * [dvorak_silhouettes.datapackage.json](https://github.com/DCMLab/dvorak_silhouettes/releases/latest/download/dvorak_silhouettes.datapackage.json)
* clone the repo: `git clone https://github.com/DCMLab/dvorak_silhouettes.git` 


## Data Formats

Each piece in this corpus is represented by five files with identical name prefixes, each in its own folder. 
For example, the first piece has the following files:

* `MS3/op08n01.mscx`: Uncompressed MuseScore 3.6.2 file including the music and annotation labels.
* `notes/op08n01.notes.tsv`: A table of all note heads contained in the score and their relevant features (not each of them represents an onset, some are tied together)
* `measures/op08n01.measures.tsv`: A table with relevant information about the measures in the score.
* `chords/op08n01.chords.tsv`: A table containing layer-wise unique onset positions with the musical markup (such as dynamics, articulation, lyrics, figured bass, etc.).
* `harmonies/op08n01.harmonies.tsv`: A table of the included harmony labels (including cadences and phrases) with their positions in the score.

Each TSV file comes with its own JSON descriptor that describes the meanings and datatypes of the columns ("fields") it contains,
follows the [Frictionless specification](https://specs.frictionlessdata.io/tabular-data-resource/),
and can be used to validate and correctly load the described file. 

### Opening Scores

After navigating to your local copy, you can open the scores in the folder `MS3` with the free and open source score
editor [MuseScore](https://musescore.org). Please note that the scores have been edited, annotated and tested with
[MuseScore 3.6.2](https://github.com/musescore/MuseScore/releases/tag/v3.6.2). 
MuseScore 4 has since been released which renders them correctly but cannot store them back in the same format.

### Opening TSV files in a spreadsheet

Tab-separated value (TSV) files are like Comma-separated value (CSV) files and can be opened with most modern text
editors. However, for correctly displaying the columns, you might want to use a spreadsheet or an addon for your
favourite text editor. When you use a spreadsheet such as Excel, it might annoy you by interpreting fractions as
dates. This can be circumvented by using `Data --> From Text/CSV` or the free alternative
[LibreOffice Calc](https://www.libreoffice.org/download/download/). Other than that, TSV data can be loaded with
every modern programming language.

### Loading TSV files in Python

Since the TSV files contain null values, lists, fractions, and numbers that are to be treated as strings, you may want
to use this code to load any TSV files related to this repository (provided you're doing it in Python). After a quick
`pip install -U ms3` (requires Python 3.10) you'll be able to load any TSV like this:

```python
import ms3

labels = ms3.load_tsv("harmonies/op08n01.harmonies.tsv")
notes = ms3.load_tsv("notes/op08n01.notes.tsv"")
```


## Version history

See the [GitHub releases](https://github.com/DCMLab/dvorak_silhouettes/releases).

## Questions, Suggestions, Corrections, Bug Reports

Please [create an issue](https://github.com/DCMLab/dvorak_silhouettes/issues) and/or feel free to fork and submit pull requests.

## Cite as

> Hentschel, J., Rammos, Y., Neuwirth, M., Moss, F. C., & Rohrmeier, M. (2024). An annotated corpus of tonal piano music from the long 19th century. Empirical Musicology Review, 18(1), 84–95. https://doi.org/10.18061/emr.v18i1.8903

## License

Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License ([CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/)).

![cc-by-nc-sa-image](https://licensebuttons.net/l/by-nc-sa/4.0/88x31.png)

## File naming convention


The file names listed in the [Overview](#overview) below refer to the 12 pieces contained in
[opus number 8](https://en.wikipedia.org/wiki/List_of_compositions_by_Anton%C3%ADn_Dvo%C5%99%C3%A1k).


## Overview
|file_name|measures|labels|standard|                annotators                |          reviewers           |
|---------|-------:|-----:|--------|------------------------------------------|------------------------------|
|op08n01  |      52|    80|2.3.0   |Daniel Grote (2.1.1), Hanné Becker (2.3.0)|Johannes Hentschel (2.1.1), AN|
|op08n02  |      15|    67|2.3.0   |Daniel Grote (2.1.1), Hanné Becker (2.3.0)|Johannes Hentschel (2.1.1), AN|
|op08n03  |      72|   238|2.3.0   |Daniel Grote (2.1.1), Hanné Becker (2.3.0)|Johannes Hentschel (2.1.1)    |
|op08n04  |      59|   136|2.3.0   |Adrian Nagel (2.1.1), Hanné Becker (2.3.0)|Adrian Nagel (2.1.1)          |
|op08n05  |      80|   139|2.3.0   |Adrian Nagel (2.1.1), Hanné Becker (2.3.0)|Adrian Nagel (2.1.1)          |
|op08n06  |      60|   113|2.3.0   |Adrian Nagel (2.1.1), Hanné Becker (2.3.0)|Adrian Nagel (2.1.1)          |
|op08n07  |      38|   167|2.3.0   |Adrian Nagel (2.1.1), Hanné Becker (2.3.0)|Adrian Nagel (2.1.1)          |
|op08n08  |      57|   100|2.3.0   |Adrian Nagel (2.1.1), Hanné Becker (2.3.0)|Adrian Nagel (2.1.1.)         |
|op08n09  |      61|    97|2.3.0   |Adrian Nagel (2.1.1), Hanné Becker (2.3.0)|Adrian Nagel (2.1.1)          |
|op08n10  |      58|   104|2.3.0   |Adrian Nagel (2.1.1), Hanné Becker (2.3.0)|Adrian Nagel (2.1.1)          |
|op08n11  |      44|    88|2.3.0   |Adrian Nagel (2.1.1), Hanné Becker (2.3.0)|Adrian Nagel (2.1.1)          |
|op08n12  |      78|   210|2.3.0   |Adrian Nagel (2.1.1), Hanné Becker (2.3.0)|Adrian Nagel (2.1.1)          |


*Overview table automatically updated using [ms3](https://ms3.readthedocs.io/).*
