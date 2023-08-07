# rat_singlecell_liver_ArchR

Branch version1 is the code for the article "Gene-regulation modules in nonalcoholic fatty liver disease revealed by single-nucleus ATAC-seq."

Files are in R Markdown/Notebook (.Rmd) format.
They are named 1_, 2_, ... in the order of execution.
I recommend using RStudio for editing and running.

Questions? Please submit to GitHub Issues or e-mail fumihiko AT takeuchi DOT name

## Data download

### Animal ID and experimental condition

* See fields `sample_name`, `age` and `treatment` for each `biosample` in DDBJ
  (BioProject [PRJDB13870](https://ddbj.nig.ac.jp/resource/bioproject/PRJDB13870))

### Use case 1: Raw data. Not recommended because the data cleaning takes a few days.

* single-nucleus ATAC-seq
  * BAM files produced by Cell Ranger are available from DDBJ
    (DRA [DRA014511](https://ddbj.nig.ac.jp/resource/sra-submission/DRA014511) within BioProject PRJDB13870)
  * Start by running `1_unify_multiple_barcodes_for_single_droplet.Rmd`
* bulk ATAC-seq
  * FASTQ files are available from DDBJ
    (DRA [DRA014458](https://ddbj.nig.ac.jp/resource/sra-submission/DRA014458) within BioProject PRJDB13870)
  * I used the ATAC-seq data processing workflow by
    [Reske et al.](https://doi.org/10.1186/s13072-020-00342-y)

### Use case 2: Datasets after cleaning

* single-nucleus ATAC-seq
  * ArchR project files (*.zip; unzip before use)  are available from
    [figshare](https://doi.org/10.6084/m9.figshare.20236509)
  * Start by running `2_ArchR_setting.Rmd` and then `4_LSI_and_clustering_of_tile_matrix.Rmd`
* bulk ATAC-seq
  * BAM files (*.bam *.bai) are available from
    [figshare](https://doi.org/10.6084/m9.figshare.20236509)
  * The data is analyzed in `6_cell_type_composition.Rmd`

### Use case 3: Generate tables & figures in manuscript

* Run Use case 2.
* 5_LSI_and_clustering_of_peak_matrix.Rmd >
  Clustering with taylored parameter >
  Uniform Manifold Approximation and Projection (UMAP)
  * Fig.1B
* 6_cell_type_composition.Rmd >
  Refine and inspect cell type composition of bulk samples >
  Cross check, bulk vs snATAC-seq
  * Fig.1D
* 6_cell_type_composition.Rmd >
  Refine and inspect cell type composition of bulk samples >
  Test difference and plot cell type composition
  * Fig.1E
* 7_GeneScoreMatrix.Rmd >
  QC
  * Fig.1C
* 7_GeneScoreMatrix.Rmd >
  Compare between conditions
  * Table S2, Dataset S1
* 7_GeneScoreMatrix.Rmd >
  Cross-check with bulk differential gene expression experiments
  * Fig.S1
* 9_GSEA.Rmd >
  Summarize results across tgt/bgd combinations
  * Fig.2 (The R code outputs result for each gene set. The heatmap was drawn using Excel.)
* 10_GRN.Rmd >
  Multiple motifs-to-one gene analysis >
  Nonnegative matrix factorization of regulator-regulatee matrix
  * Fig.3A, Fig.4A, Fig.5A, Fig.6A
* 10_GRN.Rmd >
  Multiple motifs-to-one gene analysis >
  Hyperparameters for the discovery of factors (modules) of TF regulation
  * Fig.S3
* 10_GRN.Rmd >
  Multiple motifs-to-one gene analysis >
  Inspect enriched gene sets
  * Fig.3B, Fig.4B, Fig.5B, Fig.6B
* 10_GRN.Rmd >
  Activity score and co-regulation of a gene set >
  Compute gene set activity score
  * Fig.7 (top panel), Fig.S2 (top panel)
* 10_GRN.Rmd >
  Activity score and co-regulation of a gene set >
  Core genes as those central in co-regulation and protein-protein interaction
  * Fig.7 (middle & bottom panels), Fig.S2 (middle & bottom panels)

## Information

Please cite

[Takeuchi, F. et al., Gene-regulation modules in nonalcoholic fatty liver disease revealed by single-nucleus ATAC-seq, DOI: 10.26508/lsa.202301988](https://doi.org/10.26508/lsa.202301988)

[Takeuchi, F. et al., Single-nucleus ATAC-seq elucidates major modules of gene regulation in the development of non-alcoholic fatty liver disease, DOI: 10.1101/2022.07.12.499681](https://doi.org/10.1101/2022.07.12.499681) (old manuscripts)

