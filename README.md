
<!-- README.md is generated from README.Rmd. Please edit that file -->

# SpaCE (Spatial Cellular Estimator)

<!-- badges: start -->

<!-- badges: end -->

SpaCE is an R package for decomposing cell lineages and understanding
cell-cell interactions in tumors from spatial transcriptomics data.
SpaCE first estimates cancer cell abundance and clone structure through
modeling the segmental copy number variations. SpaCE then uses a
constrained regression model to calibrate local tissue densities and
determine stromal and immune cell lineage hierarchies. Further, SpaCE
can reveal how intercellular signaling interactions promote cancer
progression.

<img src="docs/image/fig1.png" width="100%" />

## Installation

To install `SpaCE`, we recommend using `devtools`:

``` r
# install.packages("devtools")
devtools::install_github("data2intelligence/SpaCE")
```

## Dependencies

R version \>= 3.6.0. R packages: Matrix, jsonlite, png, ggplot2,
reshape2, cowplot, GSVA, infercnv, Rjags, ComplexHeatmap, psych, ppcor,
ggraph, tidygraph, parallel.

## Tutorial

Please click [here](./docs/tutorial.md) to visit the `SpaCE` tutorial.
