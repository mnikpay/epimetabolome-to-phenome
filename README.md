### Description
The aim of this unix package is to investigate the contribution of epigenome-metabolome biomarker pairs listed in our manuscript to a phenotype. Below, we describe each script and their use. Users can edit the scripts to meet their requirements.

The entire package can be obtained from [here](https://zenodo.org/record/6420589)

It can be accessed as:
```
unzip epimetabolimics.zip

chmod -R 700 ./epimetabolimics

cd ./epimetabolimics
```
A search can be initiated by passing IDs for the metabolite and the trait of interest from the OpenGWAS db to the main script, example:
```
bash wrapper.sh met-d-Total_FA ieu-b-30
```
In the above example, the script downloads the GWAS data for fatty acid levels (met-d-Total_FA) and ieu-b-30 (White blood cell counts) from the OpenGWAS database. It then conducts the analysis and generated the following table:

| Exposure       | Outcome        | B         | SE         | P           | NSNP |
|----------------|----------------|-----------|------------|-------------|------|
| met-d-Total_FA | ieu-b-30       | 0.04 | 0.006 | 6.3e-13 | 93   |
| cg12568669     | ieu-b-30       | 0.02 | 0.002  | 1.8e-30 | 55   |
| cg12568669     | met-d-Total_FA | 0.03 | 0.003  | 1.4e-18  | 56   |

Which describes the nature of association between biomarkers and the trait. The sign of effect size (B) indicates the direction of association (i.e. a positive beta indicates higher levels of the exposure is associated with higher levels of the outcome), SE indicates standard error, P indicates p-value, NSNP indicates the number of SNPs in the instrument used to examine the association between the exposure and the probe.
In this example, the program identified a significant positive association between higher levels of fatty acids and higher values of WBC (B=0.04, P=6.3e-13). Furthermore, it identified cg12568669 as a methylation site that contributes to WBC (B=0.02, P=1.8e-30) by increasing the level of fatty acids (B=0.03, P=1.4e-18). 
