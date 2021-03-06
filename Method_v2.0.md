# PGP1 genome assembly version 2.0

<img src = "https://user-images.githubusercontent.com/25347568/163683905-34631e8e-125c-4b90-884e-54806c0d8104.png" width="40%" height="40%">

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

## Correcting base errors on extended contigs
* 1st : Correction by HiFi reads
* 2nd : Correction by short reads
* Variant caller : DeepVariant v1.3.0

## Assessing base accuracy on extended contigs
* Merqury with short reads

## Scaffolding extended contigs
* 1st scaffolding : Reference-guided scaffolding aginast CHM13v2 using RagTag
* 2nd scaffolding (+ correcting local-misassemblies) : Juicer + 3D-DNA pipeline
