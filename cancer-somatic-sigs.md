# Somatic Signatures in Cancer

Notes from the informal BINF Wednesday Meeting (24 Jan 2018), by Nick (@methylnick)

Based on "Signature of mutational proccesses in human cancer", Alexandrov et al 2013.

 - Nick says non-negative matrix factorization (NMF) quite important
 - RNAseq just looks at transcript abundance, i.e. just counting
 - Fig 3 - presence of mutational signatures across human cancer types. 
 - Nick's exome-seq pipeline: tools: alignment (`BWA`), mark duplicates (`picard`), base recalibration (`picard`), `GATK` (`Haplotype caller`), `Samtools` (`mpileup`), `freebayes`. From GATK: `VCF` for somatic signatures, `BCFtools`, `hsmetrics` for summary stats. Filter variants: require >20x coverage
 - Kirill suggests SNPdb that calls known germline mutations. 
 - **CSIRO Training modules**: [Cancer genomics modules](https://bpa-csiro-workshops.github.io/)/somatic mutations/assessing somatic mutational signatures.
 - There's a `SomaticSignature` R library! (Roxane has her doubts on whether its results are actionable, though. Used in PeterMac on patient data for research, but maybe not in a clinical setting?)
