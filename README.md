# CRISPRcleanR

![alt text](https://github.com/francescojm/CRISPRcleanR/blob/master/web/CCRlogo.jpg)

**An R package for unsupervised identification and correction of gene independent cell responses to CRISPR-cas9 targeting**

CRISPRcleanR is an R package for the processing of pooled genome-wide CRISPR-Cas9 derived essentiality profiles [1]. These essentiality profiles provide a measure of the loss or gain of cellular fitness resulting from knocking-out a gene from targeted disruption via a single guide RNA (sgRNA). The alteration in fitness is expressed as the log fold change (logFCs) of the sgRNA read counts at time 0, e.g. the pooled plasmid DNA library, and the final read counts determined at the end of the experiment. A circular binary segmentation algorithm [2, 3] is applied by the core function of CRISPRcleanR to the genome-wide pattern of sgRNAs' logFCs. In this way, this function identifies genomic regions containing clusters of sgRNAs with sufficiently equal logFCs, which are on average significantly different from the background. These regions must also contain a minimum number of targeted different genes. Assuming that it is very unlikely to observe the same loss/gain-of-fitness effect when targeting a large number of contiguous genes, if certain user-defined conditions are met then the logFCs of such regions are deemed as biased by some local feature of the involved genomic segment (which could be, for example, copy number amplified [4]), and they are corrected via mean centering. CRISPRcleanR also includes functions to measure and visualise extent and effect of the performed correction, its ability to detect copy number amplified and not expressed genes (which can be used as positive controls), and classification performances for a priori known sets of essential/non-essential genes of the corrected logFCs. Finally, it implements an inverse transformation function through which corrected treatment counts can be derived. This makes the output of CRISPRcleanR compatible with tools recently proposed to call depletion significance based on mean-variance modeling [5] or baysian statistics both [6].

Quick start guide:
https://github.com/francescojm/CRISPRcleanR/blob/master/Quick_start.pdf

**NEWS**

Now fully supporting the following additional libraries, with dedicated native annotation data objects and example datasets:
    - Brunello [7]

**References**

[1] Iorio F, Behan FM, Goncalves E, Beaver C, Ansari R, Pooley R, et al. *Unsupervised correction of gene-independent cell responses to CRISPR-Cas9 targeting*. BMC Genomics. 2018 Aug 13;19(1):604

[3] Olshen AB, Venkatraman ES, Lucito R et al. (2004). *Circular binary segmentation for the analysis of array-based DNA copy number data*. Biostatistics 5: 557-572.

[3] Venkatraman ES, Olshen AB (2007). *A faster circular binary segmentation algorithm for the analysis of array CGH data*. Bioinformatics 23: 657-63.

[4] Aguirre AJ, Meyers RM, Weir BA et al. *Genomic copy number dictates a gene-independent cell response to CRISPR-Cas9 targeting*. Cancer Discov June 3 2016 DOI: 10.1158/2159-8290.CD-16-0154

[5] Li W, Xu H, Xiao T, Cong L, Love MI, Zhang F, Irizarry RA, Liu JS, Brown M, Liu XS. *MAGeCK enables robust identification of essential genes from genome-scale CRISPR/Cas9 knockout screens*. Genome Biol. 2014;15(12):554.

[6] Hart T and Moffat J. *BAGEL: a computational framework for identifying essential genes from pooled library screens*. BMC Bioinformatics, 2016 vol. 17 p. 164.

[7] Doench JG, Fusi N, Sullender M, Hegde M, Vaimberg EW, Donovan KF, et al. *Optimized sgRNA design to maximize activity and minimize off-target effects of CRISPR-Cas9*. Nat Biotechnol. 2016;34:184–91.
