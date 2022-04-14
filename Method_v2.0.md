# PGP1 genome assembly version 2.0

## Contig assembly for generating phased reads
### PacBio HiFi
* Hifiasm assembly with HiFi and Hi-C reads (Hi-C mode)
* Output contains contig assemblies from both haplotypes.

### ONT PromethION
* Pre-assembly with whole sequencing data using Flye assembler
* Variant calling with PromethION reads against pre-assembly using PEPPER-Margin-DeepVariant pipeline (https://github.com/kishwarshafin/pepper)
* Generating phased bam and fastq using Margin program
* Main contig assembly with phased reads (H1+H0 and H2+H0)
* Correcting base errors using Medaka program (1st phase)
* Correcting base errors with HiFi reads using DeepVariant and Merfin program (https://github.com/UCSC-nanopore-cgl/margin)

## Merging contig assemblies for generating exteneded contigs
* Merging contig assemblies using Quickmerger (ref: HiFi, target: ONT)

## Assessing base accuracy on extended contigs
* Merqury with short reads
