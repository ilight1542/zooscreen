# Zooscreen code base
This codebase contains scripts, input, and output files for the publication **Probing the zooarchaeological record across time and space for ancient pathogens** by Runge et al. This codebase was maintained and generated by Ian Light-Maka.
## Outline of codebase
### Pathogen Screening
Data processing scripts and outputs files for downstream analysis for the metagenomic screening. Zooscreen_final_production_run.txt contains the list of considered taxonomic nodes for the screening pipeline. The HOPS/MALT database was generated with the reference genomes in the database_info directory, using a step size of 4.
### Pathogen mapping
Downstream mapping post-snakemake generation of the candidate mutation table for *E. rhusiopathiae* and *S. lutetiensis*. Also includes output files from eager run and annotation files for generating trees in itol.
### Sample Host Validation
nf-core/Taxprofiler was used to assess the metagenomic content of the libraries for host validation and assessment of DNA preservation. Kraken2 was used with a pre-built nt-database available from [Ben Langmead's prebuilt kraken2 server](https://benlangmead.github.io/aws-indexes/k2). The specific database is the 11/29/2023 build. All outputs of kraken2 are availablein the k2_nt directory, and are analyzed using the host_validation_parsing_top_hits_to_csv.py. This analysis file requires files generated from the pathogen screening section of this repository.
### Tree outputs
This folder contains RAxML-ng outputs for the maxmium likelihood trees generated from the SNP tables from pathogen mapping. The files include all bootstrap realizations (1000 replicates), the maximum likelihood tree, the bootstrap support tree, and the log files. In addition, the single-ancient-sample projections are also available, and the TBE tree.