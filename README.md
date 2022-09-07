
<!-- README.md is generated from README.Rmd. Please edit that file -->

# SpaCE (Spatial Cellular Estimator)

SpaCE is a reference-free method for analyzing cancer spatial
transcriptomics (ST) datasets to estimate cell lineage and cell-cell
interactions in tumor microenvironment. Briefly, SpaCE first estimates
cancer cell abundance by integrating a gene pattern dictionary of common
malignancies. SpaCE then uses a constrained regression model to
calibrate local tissue densities and determine stromal and immune cell
lineage fraction. Further, SpaCE can reveal putative cell-cell
interactions in the tumor microenvironment. What’s more, although SpaCE
does not require any input cell reference profile to process tumor ST
data, SpaCE can still accept a matched scRNA-seq data as customized
references to carry out cell type deconvolution.

<img src="man/figures/workflow.png" width="100%" />

## Installation

To install `SpaCE`, we recommend using `devtools`:

``` r
# install.packages("devtools")
devtools::install_github("data2intelligence/SpaCE")
```

Or user can install from the local source code:

``` r
# download in the shell.
git clone https://github.com/data2intelligence/SpaCE.git

# install SpaCE in R environment.
install.packages(“location_to_SpaCE_gitclone", repos = NULL, type="source”)
```

## Dependencies

-   R version \>= 4.2.0.
-   R packages: Matrix, jsonlite, ggplot2, reshape2, patchwork, png,
    jpeg, shiny, MUDAN, factoextra, NbClust, cluster, parallel, psych,
    BiRewire, limma.

## Example

``` r
library(SpaCE)

visiumPath <- file.path(system.file(package = "SpaCE"), "extdata/Visium_BC")
SpaCE_obj <- create.SpaCE.object.10X(visiumPath = visiumPath)
SpaCE_obj <- SpaCE.deconvolution(SpaCE_obj, cancerType="BRCA", coreNo=8)

SpaCE_obj@results$deconvolution[1:13,1:3]

##             AAACAAGTATCTCCCA-1 AAACACCAATAACTGC-1 AAACAGAGCGACTCCT-1
## Malignant         2.860636e-01                  1       6.845966e-02
## CAF               3.118545e-01                  0       3.397067e-01
## Endothelial       5.510895e-02                  0       1.427060e-01
## Plasma            2.213392e-02                  0       1.507382e-02
## B cell            3.885793e-03                  0       9.271616e-02
## T CD4             1.344389e-01                  0       1.554305e-02
## T CD8             7.578696e-03                  0       2.514558e-07
## NK                7.104005e-04                  0       1.670019e-06
## cDC               1.421632e-07                  0       8.278023e-02
## pDC               1.606443e-06                  0       2.283754e-02
## Macrophage        1.703304e-01                  0       5.021248e-02
## Mast              7.905067e-08                  0       1.621498e-05
## Neutrophil        1.380073e-05                  0       9.528996e-07
```

## Tutorial

-   [Cell type deconvolution and interaction analysis without
    reference](https://data2intelligence.github.io/SpaCE/articles/visium_BC.html)  
-   [Deconvolution with a matched scRNA-seq data
    set](https://data2intelligence.github.io/SpaCE/articles/oldST_PDAC.html)
