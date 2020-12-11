# SprayNPray

There is no official publication for SprayNPray. If it was useful for your work, you can cite it as follows:

Garber, AI. 2020: SprayNPray: quick and easy taxonomic profiling of genome and metagenome contigs, GitHub repository: https://github.com/Arkadiy-Garber/SprayNPray.

Please also cite the various dependencies used by spray-and-pray: [DIAMOND](https://pubmed.ncbi.nlm.nih.gov/25402007/), [Prodigal](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2848648/), and [Metabat2](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6662567/).


Provide either raw contigs or ORFs (amino acid) in FASTA format.
A reference protein dataset also needs to be provided. Ideally, this should be NCBI's RefSeq or nr database from NCBI, 
which can be downloaded via: wget ftp://ftp.ncbi.nih.gov/blast/db/FASTA/nr.gz

This program will then DIAMOND BLAST each ORF against the reference database
(This takes about 30 minutes for a typical bacteria genome of ~4Mbp).

The program will then output a file in CSV format summarizing the dominant taxanomic groups matched to each contig.
This allows the user to visually inspect the data, seeing what the closest taxonomic group to each contig is.
Additionally, the user can specify a set of criteria (e.g. GC-content, read coverage, coding density, closest taxonomic hits) to re-write the provided contigs into a new FASTA file.

## Citing SprayNPray
If you found this software useful to your research please cite as follows:

Garber, AI. 2020: SprayNPray: quick and easy taxonomic profiling of genome and metagenome contigs, GitHub repository: https://github.com/Arkadiy-Garber/SprayNPray.

Please also cite the various dependencies used by spray-and-pray: [DIAMOND](https://pubmed.ncbi.nlm.nih.gov/25402007/), [Prodigal](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2848648/), and [Metabat2](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC6662567/).


## easy-installation:
  
    git clone https://github.com/Arkadiy-Garber/SprayNPray.git
    cd SprayNPray
    bash setup.sh
    source activate sprayandpray

Do not worry about the dependencies after conda installation. Just type:

`source deactivate` when finished using the program.


## Installation without conda (not recommended):

`git clone https://github.com/Arkadiy-Garber/SprayNPray.git

## Install Dependencies:

* [DIAMOND](https://github.com/bbuchfink/diamond)
* [Prodigal](https://github.com/hyattpd/Prodigal)
* [Metabat](https://bitbucket.org/berkeleylab/metabat)
* [Python3](https://www.python.org/download/releases/3.0/)


## quick-start

    spray-and-pray.py -g genomeContigs.fa -out genomeContigs -ref /path/to/nr/nr.faa

### setting minimum amino acid identity for clustering to 35%, with query coverage of at least 50%

    ParaHunter.sh -a genomeOrfs_aa.faa -n genomeOrfs_nuc.fna -m 0.35 -c 0.5
