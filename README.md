# GO-Elite
GO-Elite is designed to identify a minimal non-redundant set of biological Ontology terms or pathways to describe a particular set of genes or metabolites. Default resources include multiple ontologies (Gene, Disease, Phenotype), pathways (WikiPathways, KEGG, Pathway Commons), putative regulatory targets (transcription, microRNA, domains) and cellular biomarkers. 

This script takes a list or multiple list of protiens/genes and peforms the GO-elite anlaysis. It then produces a pdf output using R.



**Instrtuctions**

**Input file** The input file needs to be in csv format (or maybe txt?). The first row is the title of your protein list. This title can have letters, numbers, spaces of special characters. Note that the spaces and special charaters will be converted to "." in the output. Each column needs to have at least one offical gene smybol. We disucessed making the requirment be at least three.

**Background** The background is a list of offical gene smybols in witch all other list/s are compared to determine enrichment of biological functions, struture motifs, or localization. This background list, if not specified is the column with the largest number of terms. The background must be larger than the list it is being compared too. I must also contain every gene that is found in any other column.

