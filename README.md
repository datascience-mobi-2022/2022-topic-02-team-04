# 2022-topic-02-team-04

title

abstract

introduction

methods

results

discussion

references


## /preprocessing/01_variance_filtering_tcga_exp.Rmd
- Load original data (60,000x10,000 Matrix)
- Checking for NAs and removing rows containing NAs
- Compute mean, variencem, sd of every row/ for every gene
- *PLOT:* Distribution of means of all genes
- *PLOT:* Variances for each row of tcga_exp and quantiles in 10 % steps
- Removal of all genes with a variance < 35 % quantile of variance
- *EXPORT:* _tcga_exp_cleaned_

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
- Load _tcga_exp_cleaned.rds_
- Extract ensembl IDs
- Identification of biotypes using _biomaRt_
- Investigation of unmatched genes
- *PLOT:* Mean-variance plot for genes without known biotype
- Count of all occuring biotypes
### Gene sets
- Load _total_pathways_ensID.rds_
- Removal of duplicated genes
- Identification of biotypes using _biomaRt_ and _EnsDb.Hsapiens.v79_
- ??? _tcga_exp_cleaned_reduced_ ???
