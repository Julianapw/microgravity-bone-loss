# Microgravity and Bone Loss

**Investigating Biological Mechanisms Associated with Bone Loss During Microgravity Exposure**

## About the Project

Microgravity exposure can be associated with changes in bone mineral density, bone structure, and the biological processes involved in bone formation and remodeling. Understanding these changes and identifying potential early biological markers remain important research challenges.

The initial research question is:

> **Can bone loss be predicted before it occurs using biological data collected at the beginning of microgravity exposure?**

To investigate this question, publicly available datasets were explored to identify biological measurements collected before or during exposure and their potential relationship with subsequent bone outcomes.

So far, an important limitation has been identified: the datasets analyzed provide complementary evidence, but a dataset linking early biological measurements to a later quantitative bone outcome in the same individuals has not yet been confirmed.

For this reason, the project also investigates a complementary question:

**Which biological mechanisms are associated with microgravity-induced bone changes, considering structural, molecular, metabolic, and microbial evidence from different datasets?**

This alternative approach allows the investigation to progress without assuming that changes observed in one study necessarily cause bone loss in another.

## Research Objectives

- Investigate structural changes in bone associated with microgravity and reduced mechanical loading.
- Identify changes in the expression of genes related to bone formation and differentiation.
- Explore potential relationships between metabolism, the gut microbiome, and bone homeostasis.
- Investigate potential biomarkers associated with bone changes.
- Compare evidence across studies while accounting for differences in species, tissues, experimental methods, and conditions.
- Assess the feasibility of developing a predictive model if sufficient compatible longitudinal data become available.

## Datasets Investigated

| Dataset | Data type | Contribution to the project |
|---|---|---|
| [GSE100930](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE100930) — GSE100933 / OSD-546 | Microarray gene expression | Investigating molecular changes related to bone formation and differentiation. |
| [OSD-608](https://osdr.nasa.gov/bio/repo/data/studies/OSD-608) | Bone mineral density in rats | Investigating changes in bone density under different levels of mechanical loading and experimental durations. |
| [OSD-804](https://osdr.nasa.gov/bio/repo/data/studies/OSD-804) | Bone structure measured by micro-CT | Characterizing differences in trabecular bone parameters after exposure to actual spaceflight microgravity. |
| [OSD-417](https://osdr.nasa.gov/bio/repo/data/studies/OSD-417) | Metabolomics, microbiome, and related biological data | Investigating potential relationships between metabolic changes, the microbiome, and bone homeostasis. |
| [GSE276323](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE276323) — OSD-943 | DNA methylation in astronauts | Exploring epigenetic changes before and after spaceflight and potential associations with bone-related biological processes. |
| [GSE206008](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE206008) — OSD-539 | Gene expression in cartilage-differentiated cells | Investigating complementary molecular evidence under parabolic flight conditions. |

**Important:** These datasets do not necessarily contain measurements from the same individuals, tissues, or collection time points. They are therefore treated as complementary lines of evidence rather than as a single integrated dataset.

## 1. Gene Expression Analysis — GSE100930

### Overview

GSE100930 is part of the GSE100933 study and contains microarray gene expression data from human bone marrow mesenchymal stem cells (hBMSCs), comparing spaceflight samples (*Flight*) with ground controls (*Ground*).

The analysis uses microarray expression data and the annotation for platform [GPL6244](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GPL6244).

### Methods

- Organized gene expression data and sample metadata.
- Consulted platform annotations to map probes to genes.
- Initially selected genes associated with bone formation and differentiation.
- Compared Flight and Ground samples separately under Osteogenic and Standard culture conditions.
- Calculated log2 fold change (log2FC).
- Applied Welch's *t*-test.
- Corrected for multiple comparisons using the false discovery rate (FDR) method.

The initial gene panel included:

- `RUNX2`
- `ALPL`
- `BGLAP`
- `COL1A1`
- `SP7`
- `BMP2`
- `SPP1`

### Exploratory Findings

Under the **Osteogenic** condition, the analysis showed:

- Increased expression of `RUNX2`, `BGLAP`, and `COL1A1` in Flight samples compared with Ground samples.
- Decreased expression of `ALPL`.

These differences remained statistically significant after FDR correction, according to the results obtained in the analysis.

Under the **Standard** condition, `RUNX2` and `SP7` showed increased expression in Flight samples.

The results suggest that the response of bone-related genes varies depending on the gene and culture condition.

### Limitations

This dataset measures gene expression in cultured cells and does not provide a subsequent bone outcome, such as bone mineral density or percentage of bone loss.

Therefore, the results can be used to investigate molecular changes associated with the experimental condition, but they do not demonstrate that these changes predict bone loss in an individual.

The small sample size also requires caution when interpreting results and generalizing findings.

## 2. Bone Mineral Density Analysis — OSD-608

### Overview

OSD-608 investigates the effects of reduced mechanical loading on bone mineral density in rats. The experiment includes different levels of partial weight-bearing support (PWB20, PWB40, PWB70, and PWB100) and experimental periods of one, two, and four weeks.

Measurements were collected using peripheral quantitative computed tomography (pQCT) on the right tibia, including trabecular and cortical bone mineral density.

### Methods

- Organized the transformed data file provided by the repository.
- Identified experimental groups and measurement time points.
- Compared bone density measurements across weight-bearing conditions.
- Analyzed each experimental period separately.
- Checked percentage changes against the recorded initial and subsequent density measurements.
- Consulted the submitted spreadsheet, glossary, and dataset description.

### Exploratory Findings

Statistically significant differences in trabecular bone mineral density were observed between groups at all three experimental time points.

Overall, groups subjected to greater reductions in mechanical loading tended to show larger decreases in bone density. However, this pattern was not consistent across every comparison.

During data verification, discrepancies were identified between some reported percentage changes and the values recalculated from the initial and subsequent density measurements. In at least one case, the recorded density at week four was identical to the initial measurement, although the reported percentage change was negative.

The available supplementary files did not resolve all these discrepancies.

### Limitations

OSD-608 uses a terrestrial reduced-loading model rather than direct exposure to microgravity during spaceflight.

The consistency of the reported percentage changes must also be clarified before the results can be finalized. The absence of raw data in the repository consulted further limits the investigation of the source of these discrepancies.

The dataset provides quantitative measurements of the bone outcome, but an association between early biological markers and subsequent bone loss has not yet been established in a way that would support training a predictive model based on biological data.

## 3. Bone Structure Analysis — OSD-804

### Overview

OSD-804 investigates the effects of approximately 37 days of microgravity exposure on mouse bone structure during a mission aboard the International Space Station.

The study provides measurements obtained through micro-computed tomography (micro-CT), allowing structural characteristics of bone tissue to be compared across experimental groups.

### Methods

- Organized the transformed data file and identified the BSL, FLT, GC, and VIV groups.
- Analyzed structural measurements, focusing on the distal femur.
- Investigated trabecular thickness, trabecular separation, and trabecular number.
- Compared experimental groups using statistical tests.
- Applied Holm correction to pairwise comparisons.
- Checked outliers and missing observations against the original submitted spreadsheet and data dictionary.

### Exploratory Findings

Statistically significant differences between groups were found for trabecular separation, trabecular number, and the variable identified in the file as `bone_volume_total_volume_millimeter_cubed`.

However, not all differences observed in the overall group comparisons remained significant after correction for multiple testing.

Mean trabecular separation was higher in the FLT group than in the GC group, and this difference remained statistically significant after Holm correction.

Outliers were also identified, primarily in the GC group. Comparing the transformed file with the original spreadsheet confirmed that the investigated values were already present in the data submitted to the repository. For mouse M34, some measurements were missing in both the transformed file and the original spreadsheet.

These observations were retained during exploratory analysis rather than automatically excluding animals with extreme values.

### Limitations

The findings must be interpreted in light of between-animal variability, missing values, and differences between experimental groups.

The definition and unit of `bone_volume_total_volume_millimeter_cubed` must also be confirmed before the variable is interpreted definitively, since the BV/TV abbreviation usually refers to the ratio of bone volume to total volume.

The analyzed measurements characterize bone structure but do not independently establish a predictive relationship with biomarkers collected before exposure.

## 4. Metabolic and Microbial Investigation — OSD-417

### Overview

OSD-417 investigates changes in the gut microbiome and metabolic profiles associated with bone loss during microgravity exposure.

The study includes sequencing, metagenomic, and metabolomic data, alongside bone-health assessments described in the broader experiment.

### Methods

- Organized the available file inventory.
- Examined study metadata and assay descriptions.
- Identified files related to metagenomics and metabolomics.
- Organized and explored supplementary metabolite tables.
- Compared metabolite measurements descriptively between the ISS and ground-control groups.
- Searched for files containing bone outcomes, including DXA, micro-CT, histomorphometry, and blood biomarkers.

### Exploratory Metabolomics Findings

The analyzed supplementary metabolomics table showed descriptive differences between the ISS and ISS_G groups for metabolites including:

- Lactic acid.
- Glutathione.
- Leucine.
- Isoleucine.
- Proline.

The comparisons reported in the supplementary table indicate differences between groups for these metabolites. However, the reported FDR values exceed 5%, so these findings should not be described as statistically significant under a 5% FDR threshold.

These results provide leads for investigating metabolic processes associated with spaceflight, but they do not establish that the identified metabolites cause or predict bone loss.

### Search for Bone Outcomes

The file inventory examined so far did not contain filenames directly identifying DXA, micro-CT, bone mineral density, or histomorphometry measurements.

An attempt to access a repository endpoint returned HTTP 403. This indicates that access to that resource was not permitted by the request used, but it does not establish that all related data are publicly unavailable.

### Limitations

The bone outcome files still need to be located, and their animal identifiers and collection time points must be checked to determine whether they can be linked to the metabolomics and microbiome samples.

Without this correspondence, the molecular data and bone outcomes cannot be assumed to be integrable at the individual level or suitable for training a prediction model.

## 5. Epigenetic Investigation — GSE276323

### Overview

GSE276323, associated with OSD-943, contains DNA methylation data from two astronauts at different time points related to spaceflight.

The time points identified in the dataset description include:

- **T0:** before flight.
- **T2:** after flight.
- **T3:** approximately three months later.

### Contribution to the Project

The availability of pre- and post-flight samples allows the investigation of epigenetic changes over time.

Genes highlighted during the initial investigation include `FBLIM1`, `IHH`, and `SCAMP2`, which have been identified in the literature or exploratory analyses as relevant to biological processes of interest.

These genes are candidates for further investigation, not validated predictive biomarkers.

### Limitations

The number of individuals is very small, and the dataset does not independently provide a direct bone-loss measurement that can be linked to the methylation changes.

Therefore, the study may contribute to the search for potential biological markers, but it is not sufficient on its own to develop or validate a predictive model for bone loss.

## 6. Complementary Investigation — GSE206008

GSE206008, associated with OSD-539, was identified as a complementary source of gene expression data from cartilage-differentiated cells under parabolic flight conditions.

This dataset may help broaden the investigation of molecular responses involving tissues and biological processes related to bone formation and maintenance.

Its contribution to the main research question still depends on a detailed assessment of the available data, experimental conditions, and variables.

Because parabolic flight involves exposure conditions different from prolonged missions aboard the ISS, its results should not be treated as directly equivalent to those obtained during long-duration microgravity exposure.

## Integrated Analysis Strategy

The datasets will be integrated at the level of **biological processes and mechanisms**, rather than by simply combining all tables into a single dataset.

The main areas of investigation are:

| Biological area | Topics of interest |
|---|---|
| Bone formation and remodeling | Osteoblast differentiation, osteoclast activity, and bone matrix. |
| Energy metabolism | Metabolic processes associated with cellular activity and adaptation. |
| Oxidative stress | Antioxidant defense processes and glutathione metabolism. |
| Amino acid metabolism | Changes involving leucine, isoleucine, and related pathways. |
| Molecular and epigenetic regulation | Gene expression and DNA methylation in genes potentially related to bone homeostasis. |
| Bone structure | Mineral density, trabecular organization, and other quantitative parameters. |

These areas guide the investigation but do not represent established causal mechanisms. Final interpretations will depend on the statistical results, scientific literature, and consistency across the different lines of evidence.

## Methodology and Tools

Exploratory analyses were primarily conducted in Python using notebooks in Google Colab.

Tools and approaches include:

- **Pandas:** data organization, cleaning, and exploration.
- **NumPy:** numerical operations.
- **SciPy:** statistical tests, including Welch's *t*-test.
- **Statsmodels:** multiple-testing correction, where applicable.
- **Matplotlib and Seaborn:** exploratory data visualization.
- **GEO and NASA Open Science Data Repository (OSDR):** public data and metadata access.
- **Gene expression analysis:** log2 fold change, group comparisons, and FDR correction.
- **Bone data analysis:** descriptive statistics, group comparisons, and measurement consistency checks.

Methods were selected according to each dataset's structure and limitations. Not every method was applied to every dataset.

## General Limitations

The main limitations identified so far are:

1. **No confirmed predictive dataset:** a dataset linking early biological measurements to a subsequent quantitative bone outcome in the same individuals has not yet been identified.
2. **Small sample sizes in some studies:** this limits statistical power and generalizability.
3. **Experimental heterogeneity:** datasets include different species, tissues, culture conditions, measurement methods, and exposure periods.
4. **Differences between microgravity and reduced mechanical loading:** terrestrial models help investigate related mechanisms but do not fully reproduce the spaceflight environment.
5. **Multiple comparisons:** results must account for appropriate statistical corrections.
6. **Data quality and consistency:** some measurements contain missing values, outliers, or discrepancies that require further investigation.
7. **Associational evidence:** group differences alone do not establish causality or predictive capability.

## Next Steps

- Complete verification of OSD-608 bone measurements and investigate discrepancies in reported percentage changes.
- Confirm the definitions and units of OSD-804 structural measurements.
- Expand GSE100930 gene expression analysis beyond the initial seven-gene panel.
- Perform biological pathway enrichment analyses to identify relevant processes among differentially expressed genes.
- Continue investigating OSD-417 metabolomics and microbiome data and search for the corresponding bone outcome files.
- Examine GSE276323 epigenetic data and the complementary evidence from GSE206008.
- Compare results with the scientific literature and distinguish processes supported by multiple studies from those observed in only one dataset.
- Continue searching for longitudinal datasets that link early biological markers to later bone measurements.
- Assess predictive modeling only if the available data support appropriate predictor and outcome definitions and a valid evaluation strategy.

## Current Status

The project has progressed through exploratory analyses of structural, molecular, and metabolic data related to bone health during microgravity exposure or reduced mechanical loading.

GSE100930 has supported the investigation of gene expression changes; OSD-608 and OSD-804 have contributed to the characterization of quantitative bone density and structural outcomes; OSD-417 has expanded the investigation of metabolic and microbial changes; and GSE276323 and GSE206008 have been identified as complementary sources of biological evidence.

However, the relationship between early biological measurements and subsequent bone loss has not yet been established sufficiently to train and validate a predictive model.

The next stage will focus on consolidating the analyses, investigating shared biological processes across studies, and continuing to search for compatible longitudinal data.

The goal is to build a more consistent understanding of the mechanisms associated with bone changes and assess, based on available evidence, to what extent these mechanisms may eventually contribute to identifying potential early biomarkers.

## References and Data Access

- [GSE100930 — NCBI GEO](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE100930)
- [GSE100933 — NCBI GEO](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE100933)
- [GPL6244 — NCBI GEO](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GPL6244)
- [OSD-608 — NASA OSDR](https://osdr.nasa.gov/bio/repo/data/studies/OSD-608)
- [OSD-804 — NASA OSDR](https://osdr.nasa.gov/bio/repo/data/studies/OSD-804)
- [OSD-417 — NASA OSDR](https://osdr.nasa.gov/bio/repo/data/studies/OSD-417)
- [GSE276323 — NCBI GEO](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE276323)
- [GSE206008 — NCBI GEO](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=GSE206008)

---

**Disclaimer:** This repository documents an ongoing research project. The results presented are exploratory and may be updated as further analyses, data verification, and literature reviews are completed.
