
#################
# Description
#################


All three example datasets presented in our paper are included:
*Main rice dataset - all data: this data set is for all proteins quantified in the TMT rice
	leave dataset (~2000 proteins). 
*Main rice dataset - DE proteins: this data set is for differentially expressed proteins 
	in the TMT rice leave dataset (~530 proteins). 

The above two datasets are from the following publication:
Wu, Y.; Mirzaei, M.; Pascovici, D.; Chick, J. M.; Atwell, B. J.; Haynes, P. A., 
Quantitative proteomic analysis of two different rice varieties reveals that drought tolerance is correlated with reduced abundance of photosynthetic machinery and increased abundance of ClpD1 protease. Journal of Proteomics 2016, 143, 73-82.	
	
*Secondary dataset - all data: this dataset is for the all data quantified for the 
	Swath age-specific human plamsa with the extended library (~930 proteins).
	
This dataset is from the following publication:
Bjelosevic, S.; Pascovici, D.; Ping, H.; Karlaftis, V.; Zaw, T.; Song, X.; Molloy, M. P.; Monagle, P.; Ignjatovic, V., 
Quantitative Age-specific Variability of Plasma Proteins in Healthy Neonates, Children and Adults. Molecular &amp; Cellular Proteomics 2017, 16, (5), 924-935.

For each example, an input folder and results folder are contained. 	
	
	
##############
# How to run
##############	
	
library(PloGO2)
	

# Main rice dataset - DE proteins

DataFolder <- "Main rice dataset - DE proteins/input"

# WGCNA 

source(file.path(system.file("script", package="PloGO2"), "WGCNA_proteomics.R"))

# PloGO2
res <- ExcelToPloPathway(file.path(DataFolder,"ResultsWGCNA_Input4PloGO2.xlsx"), 
	colName="Uniprot", compareWithReference="AllData", DB.name=file.path(DataFolder,"pathwayDB.csv"),
	data.file.name = file.path(DataFolder,"Abundance_data.csv") )



# Main rice dataset - all data

DataFolder <- "Main rice dataset - all data/input"

res <- ExcelToPloPathway(file.path(DataFolder, "ResultsWGCNA_alldata_Input4PloGO2.xlsx"),  
		colName="Uniprot", compareWithReference="AllData", DB.name=file.path(DataFolder,"pathwayDB.csv"),
				data.file.name = file.path(DataFolder, "Abundance_alldata.csv") )
				
# Secondary dataset - all data
	
DataFolder <- "Secondary dataset - all data/input"


res <- ExcelToPloPathway("ResultsWGCNAInput2PloGO2.xlsx", 
	colName="Uniprot", compareWithReference="AllData", DB.name="HumanPathwayDBComb.csv")


			
				
				

