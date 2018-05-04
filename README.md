# BIOC3301 - GAIA

## Info
This repository contains all of the code used for the "GAIA: Conferring mental wellbeing from mother earth’s microbiome to us" dissertation in order to ascertain the validity of the idea that the park microbiome confers improvements to our cognition and mood. The code processed metagenomic data from the 16S V4 rRNA gene and was run in QIIME 1.9.1.

### The workflow follows this order:
* serial_joinpair_splitlib.pbs - joins the paired ends and demultiplexes the data
* parallel_pickclosed.pbs - picks the otus using closed referencing
* core_microb.pbs - generates a core microbiome from 50% upwards
* pCDA_80_100.pbs - performs a core diversity analysis on both the 80% and 100% core microbiomes
* hmap_80_100.pbs - generates heatmaps for the otus present in both 80% and 100% core microbiomes
* alpharare_shannon.pbs - performs an alpha-rarefaction analysis on the 100% microbiome to calculate each sample's Shannon index
* filter_hm_100.pbs - filters the 100% core microbiome to only include mental health improving bacteria (hm)
* hmap_hm.pbs - generates a heatmap for the hm otus

## Additional files included
* 2018mapNum.tsv - edited mapping file used in the scripts (includes new but unused variables)
* adiv_shan.xlsx - excel file showing the data from the shannon index and the formulae used to calculate the first t-test, comparing the diversity within the park vs outside the park
* ctab100hmspec.xlsx - excel file showing the hm data and the formulae used to calculate the final t-test, comparing the park's abundance to the other samples