
<!-- README.md is generated from README.Rmd. Please edit that file -->

# SpaCE (Spatial Cellular Estimator)

<!-- badges: start -->

<!-- badges: end -->

SpaCE is an R package for analyzing tumor spatial transcriptomics (ST)
data to deconvolute cell lineages and understand signaling interactions
in cancer progression. SpaCE first estimates cancer cell abundance and
clonal substructures through modeling the segmental copy number
variations across ST spots. A constrained regression model can calibrate
local tissue densities and determine stromal and immune cell lineage
hierarchies. SpaCE can further reveal how intercellular signaling
interactions at the tumor-immune interface to promote cancer
progression.

<img src="docs/image/fig1.png" width="88%" />

## Installation

To install `SpaCE`, we recommend using `devtools`:

``` r
# install.packages("devtools")
devtools::install_github("beibeiru/SpaCE")
```

## Tutorials

Click [here](./docs/tutorial.md) for the tutorials of `SpaCE`.
