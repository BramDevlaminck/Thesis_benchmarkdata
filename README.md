# Benchmarkdata
## About
This repository contains all the data used during benchmarking the implementations created for my thesis.

## Download
This repostory is initialized using git LFS.  
Installation instructions for git LFS can be found [here](https://docs.github.com/en/repositories/working-with-files/managing-large-files/installing-git-large-file-storage). 

Downloading all the files in this repository is as easy as executing the following command.

```sh
git lfs clone https://github.com/BramDevlaminck/Thesis_benchmarkdata.git
```


## Filestructure
The `protein_database.tsv` from `SIHUMI`, `swissprot_var1` and `swissprot_var2` are all the same. This is a preprocessed version of the Swiss-Prot database from [UniProt](https://www.uniprot.org/) 2023_04.

The `protein_database.tsv` from the `humanprot` folder is a smaller database made out of 3 smaller databases:  
- [Human Genome](https://www.uniprot.org/proteomes/UP000005640)  
- [Influenza B](https://www.uniprot.org/proteomes/UP000119054)  
- [Human Papillomavirus](https://uniprot.org/proteomes/UP000126093)  

The `taxons.tsv` file is a processed version of the [NCBI taxonomy](https://www.ncbi.nlm.nih.gov/taxonomy) used during aggregation of taxon IDs.

The text block below contains the output from the `tree` command together with some comments indicated with a `#`.  

```
├── README.md
├── SIHUMI  # This folder contains 6 search files originating from real experiments. Because of this they all have natural missed cleavages. The search files can be used in combination with the provided database.
│   ├── S03.txt
│   ├── S05.txt
│   ├── S07.txt
│   ├── S08.txt
│   ├── S11.txt
│   ├── S14.txt
│   └── protein_database.tsv -> ../swissprot_var1/protein_database.tsv
├── humanprot  # This folder contains a smaller database and a search file with arbitrary peptides
│   ├── protein_database.tsv
│   └── search_file.tsv
├── swissprot_var1  # the database is a preprocessed version of Swiss-Prot from UniProt. The search file only contains strictly tryptic peptides (no missed cleavage)
│   ├── protein_database.tsv
│   └── search_file_no_mch.tsv
├── swissprot_var2 # the database is a preprocessed version of Swiss-Prot from UniProt. The search file only contains peptides with missed cleavage
│   ├── protein_database.tsv -> ../swissprot_var1/protein_database.tsv. 
│   └── search_file_mch.tsv
└── taxons.tsv  # this is a preprocessed version of the NCBI taxonomy.
```
