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
In the above example, the script downloads the GWAS data for fatty acid levels (met-d-Total_FA) and ieu-b-30 (WBC) from the OpenGWAS database. It then conducts the analysis and generated the following table:

| Exposure       | Outcome        | B         | SE         | P           | NSNP |
|----------------|----------------|-----------|------------|-------------|------|
| met-d-Total_FA | ieu-b-30       | 0.0435109 | 0.00604778 | 6.26749e-13 | 93   |
| cg12568669     | ieu-b-30       | 0.0191075 | 0.0016652  | 1.76965e-30 | 55   |
| cg12568669     | met-d-Total_FA | 0.0307653 | 0.0034964  | 1.3789e-18  | 56   |

Which describes the nature of association between biomarkers and the trait. The sign of effect size (B) indicates the direction of association (i.e. a positive beta indicates higher level of the exposure is associated with higher level of the outcome), SE indicates standard error, P indicates p-value, NSNP indicates the number of SNPs in the instrument used to examine the association between the exposure and the probe.
