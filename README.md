# PloGO2_R_Package

This project contains the package tar tar file, manual and vignette for the R package PloGO2, which helps with gene ontology and pathway analysis for multi-condition experiments.  The package will soon be submitted to Bioconductor.

## Dependencies
R version > 3.5

## Installation

# install dependencies 

install.packages(c('httr', 'openxlsx', 'xtable','heatmap3'))

if (!requireNamespace("BiocManager", quietly = TRUE))
    install.packages("BiocManager")

BiocManager::install("GOstats")

BiocManager::install("GO.db")

# install PloGO2_0.99.0.zip in R using install packages from local file

# testing script can be found in the package folder script/plog2_script.R



# Optional - only needed for using WGCNA workflow

BiocManager::install("impute")
BiocManager::install("preprocessCore")

install.packages('WGCNA')


# testing script can be run using
source(file.path(system.file("script", 	package="PloGO2"), "WGCNA_proteomics.R"))
