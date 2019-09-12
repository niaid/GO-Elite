# GO-Elite
GO-Elite is designed to identify a minimal non-redundant set of biological Ontology terms or pathways to describe a particular set of genes or metabolites. Default resources include multiple ontologies (Gene, Disease, Phenotype), pathways (WikiPathways, KEGG, Pathway Commons), putative regulatory targets (transcription, microRNA, domains) and cellular biomarkers. 

This script takes a list or multiple list of protiens/genes and peforms the GO-elite anlaysis. It then produces a pdf output using R.

**Dependencies**

Python 2.7,
R 3.5.3


**Instrtuctions**

**Input file** The input file needs to be in csv format. The first row becomes the title of your protein list. This title can have letters, numbers, spaces of special characters. Note that the spaces and special charaters will be converted to "." in the output. Each column needs to have at least one offical gene smybol. We discussed making the requirment be at least three.

**Background** The background is a list of offical gene smybols in witch all other list/s are compared to determine enrichment of biological functions, struture motifs, or localization. This background list, if not specified is the column with the largest number of terms. The background must be larger than the list it is being compared too. I must also contain every gene that is found in any other column.



**Steps of the pipeline**

0) Set variables. These include file name, file path, output folder, Species, Bars per ontology, and more. 
1) Step two breaks down the csv input file into seperate txt files. It seprates the columns into sperate txt files. It also detect the column witht the longest list and seprates that into a txt file called background. The background.txt is place into the background folder. 
2) Now that the input has been parced and all the parameters have been set. It is now time to run GO-elite. A command is created in then pasted into command promt. This command calls upon python and GO-elite. It also tell GO-elite what paramteres to use. The resuts from the analysis can be found in the folder GO-Elite_results. An exsample of the command to set to command prompt: C:/Python27/python C:/Users/bishofij/Proteomics_Pipeline/GO-Elite_v.1.2.5-Py/GO_Elite.py --species Hs --mod Ensembl --permutations \"FisherExactTest\" --method \"z-score\" --zscore 1.96 --pval 0.05 --num 5 --input C:/Users/bishofij/Proteomics_Pipeline/go-elite_r_projects/test_GO/ --denom C:/Users/bishofij/Proteomics_Pipeline/go-elite_r_projects/test_GO/background/ --customSet C:/Users/bishofij/Proteomics_Pipeline/GO-Elite_v.1.2.5-Py/Databases/EnsMart62Plus/C2/ --dataToAnalyze all --output C:/Users/bishofij/Proteomics_Pipeline/go-elite_r_projects/test_GO/
3) The third step is pefromed compeletely in R. The results produced in step two are now graphed and placed into a pdf. 
