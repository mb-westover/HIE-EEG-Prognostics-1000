# Cardiac Arrest EEG Prognostic Analysis

This repository contains data, code, and analysis results for a study on EEG-based prognostication following cardiac arrest. The research examines the prognostic value of various EEG patterns observed at different time periods after cardiac arrest in predicting patient outcomes.

## Study Overview

The study analyzes EEG patterns from cardiac arrest patients to evaluate their prognostic significance for predicting poor neurological outcomes. EEG patterns are assessed across multiple time periods (24 hours, 48 hours, 72 hours, and >72 hours post-arrest) to determine their predictive performance using metrics such as sensitivity (TPR), specificity (1-FPR), positive predictive value (PPV), and negative predictive value (NPV).

## Repository Structure

### 📄 Documentation & Publications
- `2_CA prognosis-Supplement.docx` - Supplementary material
- `3-CA prognosis-SupplementalFigures.pptx` - Supplementary figures

### 📊 Source Data
- `CardiacArrestPrognos_DATA_LABELS_2025-01-12_2011 .corrected.csv` - Primary dataset containing patient data and EEG pattern annotations
- `Table 2 demographics.xlsx` - Demographic data table

### 💻 Code Files
- `a0_CalculateStats_v3.ipynb` - Main statistical analysis notebook (latest version)
- `demographics_code.ipynb` - Code for generating demographic summary tables

### 📈 Output Files & Results

#### Statistical Results
- `summary_table_with_exact_CI_2025_02_18.csv` - Comprehensive results table with exact confidence intervals
- `ResultsTable.csv` - Formatted results table with performance metrics
- `Results_For_EEG_Report.csv` - Filtered results focusing on 72-hour patterns sorted by positive predictive value
- `Slopes.csv` - Linear regression slopes for temporal trends in EEG patterns

#### Figures
- `EEG_Metrics_Figure_1.png` - Performance metrics visualization (Figure 1 of 5)
- `EEG_Metrics_Figure_2.png` - Performance metrics visualization (Figure 2 of 5)
- `EEG_Metrics_Figure_3.png` - Performance metrics visualization (Figure 3 of 5)
- `EEG_Metrics_Figure_4.png` - Performance metrics visualization (Figure 4 of 5)
- `EEG_Metrics_Figure_5.png` - Performance metrics visualization (Figure 5 of 5)

## Key Analysis Components

### EEG Patterns Analyzed
The study examines 23 different EEG patterns including:

**Background Patterns:**
- Alpha, theta, delta activity
- Voltage attenuation (10-20 uV)
- Voltage suppression (<10 uV)
- Discontinuous EEG

**Pathological Patterns:**
- Burst suppression (with variants)
- Seizures and status epilepticus
- Periodic discharges (GPD, LPD, BIPD)
- Rhythmic delta activity (LRDA, GRDA)
- Sporadic epileptiform discharges (SED)
- Various other abnormal patterns

**Reactivity:**
- EEG reactivity
- Absent EEG reactivity

### Performance Metrics
For each EEG pattern and time period, the following metrics are calculated:
- **TPR (True Positive Rate/Sensitivity)**: Proportion of patients with poor outcomes correctly identified
- **FPR (False Positive Rate)**: Proportion of patients with good outcomes incorrectly classified as poor
- **PPV (Positive Predictive Value)**: Probability of poor outcome when pattern is present
- **NPV (Negative Predictive Value)**: Probability of good outcome when pattern is absent

All metrics include exact 95% confidence intervals using the Clopper-Pearson method.

### Temporal Analysis
The code performs linear regression analysis to identify significant temporal trends in EEG pattern performance across the four time periods, with statistical significance testing (p < 0.05).

## Usage

### Running the Analysis

1. **Main Statistical Analysis:**
   ```bash
   jupyter notebook a0_CalculateStats_v3.ipynb
   ```
   This notebook:
   - Loads the primary dataset
   - Calculates confusion matrices for each EEG pattern and time period
   - Computes performance metrics with exact confidence intervals
   - Generates visualizations showing temporal trends
   - Performs linear regression analysis for trend detection

2. **Demographics Analysis:**
   ```bash
   jupyter notebook demographics_code.ipynb
   ```
   This notebook generates demographic summary tables stratified by site and outcome.

### Key Output Files

- **`ResultsTable.csv`**: Complete formatted results table suitable for publication
- **`Results_For_EEG_Report.csv`**: 72-hour results ranked by positive predictive value
- **`Slopes.csv`**: Temporal trend analysis results
- **`EEG_Metrics_Figure_*.png`**: Publication-ready visualization plots

## Dependencies

The analysis requires the following Python packages:
- pandas
- matplotlib
- numpy
- seaborn
- scipy
- statsmodels
- polars (for demographics analysis)
- textwrap
- re

## Data Structure

The primary dataset contains:
- Patient demographic information
- EEG pattern annotations for different time periods
- Outcome measures (CPC scores)
- Timing information (arrest date, EEG start/end, discharge)

## Authors

Study conducted at Beth Israel Deaconess Medical Center (BIDMC), Brigham and Women's Hospital (BWH), and Massachusetts General Hospital (MGH).