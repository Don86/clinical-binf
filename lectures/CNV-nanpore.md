# Rapid CNV characterization of clinical cancer samples on the Oxford Nanopore MinION.

Original vid [here](https://londoncallingconf.co.uk/lc/2016-plenary#168639913)

Concept: Take short reads (1000 bp or smaller) and distribute them across the whole genome or a chromosome in "bins", which can contain 50 - 500 reads. The proportion of the reads that end up in the bins tells us whether that region has duplication/deletion type events (i.e. too many, too little).  This is predicated on the assumption that the reads should be evenly distributed across a normal genome.

Practice: 

* Smaller fragments perform less well in terms of pass/fail than larger fragments. 
* Larger fragments perform much better
* 2/3 of all reads generated in the first 24h
* Not too concerned about calling perect SNPs or error-free reads; we ultimately just want to make sure that they go into the bin that they're supposed to be in (uniqueness also matters!)
* 98-99% of the 2D pass reads mapped uniquely to the genome. 60% of the 1D fail reads still mapped uniquely. 

`Ginkgo` for sparse coverage sequencing: interactive analysis and assessment of single-cell CNVs

* Pass and fail reads perform equally well for CNV detection
* Minion performance equivalent to MiSeq
