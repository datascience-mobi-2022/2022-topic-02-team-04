# 2022-topic-02-team-04

## Structure (report)

title

abstract

introduction

methods

results

discussion

references

***

## data organisation (.rds files)

### gene sets / pathways
- hallmarks_genesets_ensID.rds: All given data sets with ensembl IDs
- hallmarks_genesets_gene_symbols.rds: All given data sets with gene symbols

- add_data_sets_ens_ID.rds: Chosen additional data sets with ensembl IDs
- add_data_sets_gene_symbols.rds: Chosen additional data sets with gene symbols

- total_pathways_gene_symbols.rds: Combination of given and additional genesets with gene symbols (Former: "pathways")
- total_pathways_ensID.rds: Combination of given and additional genesets with ensembl IDs

### Pan-cancer analysis (TCGA matrix)
- tcga_tumor_log2TPM.RDS: Original TCGA matrix (60498 rows)
- tcga_tumor_annotations.rds: Clinical annotations to original TCGA matrix
- tcga_exp_variance_filtered.rds: Variance filtered (var > q35) TCGA matrix (39324 rows) (Former: "tcga_exp_cleaned")
- tcga_exp_x_total_pathways.rds: variance filtered matrix containing all TCGA genes that are present in total pathways
- tcga_pancancer.rds: variance and biotype filtered genes, ready for further investigation

### Foccused analysis (PRAD)
- tcga_tumor_normal_datascience_proj_2022.rds: Original PRAD matrix
- PRAD_TvsN.rds: variance and biotype filtered (var > q60) PRAD list, ready for further investigation

***

## /preprocessing/01_variance_filtering_tcga_exp.Rmd
- Load original data (60,000x10,000 Matrix)
- Checking for NAs and removing rows containing NAs
- Compute mean, variencem, sd of every row/ for every gene
- *PLOT:* Distribution of means of all genes
- *PLOT:* Variances for each row of tcga_exp and quantiles in 10 % steps
- Removal of all genes with a variance < 35 % quantile of variance
- *EXPORT:* _tcga_exp_variance_filtered_

## /preprocessing/02_variance_filtering_tcga_exp.Rmd
- Import of additionally chosen gene sets using _msigdbr_
- fuse into one data.frame
- extract ensembl gene IDs
- *EXPORT:* _add_data_sets_ens_ID_

## /preprocessing/02_hallmarks_genesets_ensembl_IDs.Rmd
- Import hallmark_genesets
- Conversion from gene symbols to ensemble IDs using _EnsDb.Hsapiens.v79_
- *EXPORT:* _hallmarks_genesets_ensID.rds_

## /preprocessing/03_combination_given_and_additional_gene_sets.Rmd
- Fusion of _add_data_sets_ens_ID.rds_ and _hallmarks_genesets_ensID.rds_
- *EXPORT:* _total_pathways_ensID.rds_

## /preprocessing/04_comparison_of_gene_sets.Rmd
- Load _total_pathways_ensID.rds_
- Definition of Jaccard Metric
- Compute Jaccard Distance for every combination of gene sets
- *PLOT:* Jaccard Indices to compare similarity between different pathways

## /preprocessing/05_biotype_analysis.Rmd
### TCGA Matrix
- Load _tcga_exp_variance_filtered.rds_
- Extract ensembl IDs
- Identification of biotypes using _biomaRt_
- Investigation of unmatched genes
- *PLOT:* Mean-variance plot for genes without known biotype
- Count of all occuring biotypes
- Reduction to protein-coding genes (including IG's and TCR's), important short non-coding RNAs and long intergenic non-coding RNAs
- *EXPORT:* _tcga_pancancer.rds_
- tcga_pancancer_excluded
### Gene sets
- Load _total_pathways_ensID.rds_
- Removal of duplicated genes
- Identification of biotypes using _biomaRt_ and _EnsDb.Hsapiens.v79_
- *Export:* _tcga_exp_x_total_pathways_

***

## /prad_normal_vs_tumor/01_PRAD_variance_filtering
- Combination of normal and tumor samples into one data.frame
- Computation of variance -> extremly right skewed
- Removing every gene with a variance below the 60 % quantile (var < ~1)
- Create original-like nested list
- *EXPORT:* _PRAD_variance_filtered.rds_

## /prad_normal_vs_tumor/02_PRAD_biotype analysis
- Load _PRAD_variance_filtered.rds_
- Perform biotype analysis similarly to pan-cancer preprocessing
- only keep protein-coding and lincRNAs
- *EXPORT:* _PRAD_TvsN.rds_
