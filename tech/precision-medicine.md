# Precision Medicine, School of Clinical Sciences at Monash Health, Monash University
By Dr. Jason Steen, 24-Oct-2018

## Abstract

_In the Precision Medicine group, we utilise gene panel sequencing (Hi-Plex and/or HaloPlex) to identify genetic variants in key genes of interest, with the aim of providing risk estimates of clinically-relevant markers that can be included in evidenced-base clinical management and genetic counselling.

Our largest project, BRA-STRAP, involves more than ten thousand breast cancer patients with no previous clinical identification of BRCA1 or BRCA2 pathogenic mutations. Data on this scale exemplifies the opportunities and challenges for realizing precision medicine and precision public health for breast cancer. Here I will describe our efforts to create a robust data analysis pipeline, and describe some of the key problems and considerations when working with this type of data.  In particular, we show that one of the most popular variant calling software packages is unsuitable for calling variants in amplicon based sequencing data._

## Identify clinically relevant genetic markers:
 * inform clinical practice
 * allow better risk diagnosis
 * provide population frequencies
 * These seem to be operative at population-level

### Mostly panel sequencing
* HiPlex or HaloPlex
* smallish panels of genes of interest
* Economical for large numbers of patients
 - BRASTRAP: > 10k patients
 - Prostate: ~1600
 - Renal cancers: ~1500

### Issues
 - Analysis of 10k samples from raw sequencing data through to annotated VCFs is non-trivial.
 - Managing metadata: difficult without a LIMS

### The Perfect Project

1. Study design
2. Biorepository
3. DNA
4. Library
5. Sequence data
6. QC
7. Analysis
8. Final output - a table or data structure of some sort

### The actual project

 - Non-data people being non-data people.

### Current pipeline

 * Currently using a `Ruffus` wrapper from Bernie Pope and Khalid Mahmood. `Ruffus` is not currently maintained, though, and docs are terrible.
 * Didn't bother taking down more details.

### Pain points

* Joint genotyping on such a large project is a pain: entire db has to be rebuilt to add/remove even a single sample. Partially fixed in GATK4, but still needs complete db regeneration
* UNDR-ROVER takes too long
* Upon analysis of validation runs, GATK:
 - Was not calling as many variants as expected (despite evidence in IGV)
 - Was calling variants when there was no evidence in IGV
 - Was incorrectly calling some complex variants
* Unable to combine multiple stages into single job submission (fixed in `Snakemake`!)


* `VarDict` seems to be a bit better at variant calling than `GATK`. And 10x faster!
* GATK is the "gold standard" in variant calling in exome and whole genomes, but not amplicons.
* "Clinically reportable variants" are validated by sequencing on the MiSeq, using another HiPlex panel or by Sanger sequencing.
* From experience: variants detected with allele frequency > 0.2 at depth >= 50x are very likely to be real

### External data sources
* BRCAexchange, INSiGHT, Gemini (db solution for exploration of VCFs, using an extended SQL syntax)

### Future pipelines

* `Snakemake` - Best!
* `CWL` - GA4GH support. "Disgusting" syntax.
* `Nextflow` - some licensing issues. Kirril likes it, Andrew Perry doesn't.

### More buzzwords

* `DeepVariant`
