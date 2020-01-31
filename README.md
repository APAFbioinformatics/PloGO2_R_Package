# PloGO2_R_Package

This project contains the package tar tar file, manual and vignette for the R package PloGO2, which helps with gene ontology and pathway analysis for multi-condition experiments.  The package will soon be submitted to Bioconductor.

## Dependencies
R version > 3.5

## Installation

### First install dependencies 

install.packages(c('httr', 'openxlsx', 'xtable','heatmap3'))

if (!requireNamespace("BiocManager", quietly = TRUE))
    install.packages("BiocManager")

BiocManager::install("GOstats")

BiocManager::install("GO.db")

### Next install PloGO2

From within R install from zipfile, using the file PloGO2_0.99.0.zip 

### Testing 

The example script for testing can be found in the script package folder
source(file.path(system.file("script", 	package="PloGO2"), "plog2_script.R"))

### Optional - use with the WGCNA workflow

BiocManager::install("impute")

BiocManager::install("preprocessCore")

install.packages('WGCNA')


### Test the WGCNA workflow
source(file.path(system.file("script", 	package="PloGO2"), "WGCNA_proteomics.R"))
