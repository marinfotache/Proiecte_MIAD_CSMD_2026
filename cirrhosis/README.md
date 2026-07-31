# Cirrhosis Prediction Dataset

## Overview

Cirrhosis is a late stage of scarring (fibrosis) of the liver caused by many forms of liver diseases and conditions, such as hepatitis and chronic alcoholism. This dataset contains information collected from the Mayo Clinic trial in primary biliary cirrhosis (PBC) of the liver conducted between **1974 and 1984**.

## Context

A total of 424 PBC patients, referred to Mayo Clinic during that ten-year interval, met eligibility criteria for the randomized placebo-controlled trial of the drug D-penicillamine. The first 312 cases in the dataset participated in the randomized trial and contain largely complete data. The additional 112 cases did not participate in the clinical trial but consented to have basic measurements recorded and to be followed for survival. Six of those cases were lost to follow-up shortly after diagnosis, so the data here are on an additional 106 cases as well as the 312 randomized participants.

**Total Cases in Dataset**: 418 (312 randomized + 106 additional cases)

## Source

**Trial**: Mayo Clinic trial in primary biliary cirrhosis (PBC)  
**Time Period**: 1974-1984  
**Location**: Mayo Clinic

**References**:
- **Fleming, T.R. and Harrington, D.P. (1991)**. Counting Processes and Survival Analysis. Wiley Series in Probability and Mathematical Statistics: Applied Probability and Statistics, John Wiley and Sons Inc., New York. (Dataset can be found in appendix D)
- **Dickson, et al., Hepatology 10:1-7 (1989)**
- **Markus, et al., N Eng J of Med 320:1709-13 (1989)**

**Kaggle Source**:  
fedesoriano. (August 2021). Cirrhosis Prediction Dataset. Retrieved from https://www.kaggle.com/fedesoriano/cirrhosis-prediction-dataset.

## Dataset Information

- **Total Instances**: 418
- **Number of Attributes**: 20 (1 identifier + 19 features)
- **Data Format**: CSV
- **Task**: Survival analysis / Classification (predicting patient status)

## Variable Descriptions

### Identification

1. **ID** (numeric)
   - Unique identifier for each patient
   - Patient ID number

### Survival Information

2. **N_Days** (numeric)
   - Number of days between registration and the earlier of:
     - Death
     - Transplantation
     - Study analysis time in July 1986
   - Measured in days
   - Used for survival analysis

3. **Status** (categorical)
   - Status of the patient at the end of follow-up
   - Values:
     - `C`: Censored (patient was alive at the end of the study)
     - `CL`: Censored due to liver transplantation
     - `D`: Death
   - Distribution: C (232, 55.5%), CL (25, 6.0%), D (161, 38.5%)
   - **Note**: This is the primary outcome variable for survival analysis

### Treatment Information

4. **Drug** (categorical)
   - Type of drug received in the randomized trial
   - Values: `D-penicillamine`, `Placebo`
   - Distribution: D-penicillamine (158, 50.6%), Placebo (154, 49.4%)
   - **Note**: Only the 312 randomized participants have drug assignment

### Demographic Variables

5. **Age** (numeric)
   - Age of the patient
   - Measured in days
   - **Note**: Age is recorded in days, not years

6. **Sex** (categorical)
   - Sex of the patient
   - Values: `M` (Male), `F` (Female)
   - Distribution: Female (374, 89.5%), Male (44, 10.5%)
   - **Note**: PBC is more common in women

### Clinical Signs

7. **Ascites** (binary)
   - Presence of ascites (fluid accumulation in the abdomen)
   - Values: `N` (No), `Y` (Yes)
   - Ascites is a common complication of cirrhosis

8. **Hepatomegaly** (binary)
   - Presence of hepatomegaly (enlarged liver)
   - Values: `N` (No), `Y` (Yes)
   - Indicates liver enlargement

9. **Spiders** (binary)
   - Presence of spider angiomas (spider-like blood vessels on the skin)
   - Values: `N` (No), `Y` (Yes)
   - Common sign of liver disease

10. **Edema** (categorical)
    - Presence of edema (swelling due to fluid retention)
    - Values:
      - `N`: No edema and no diuretic therapy for edema
      - `S`: Edema present without diuretics, or edema resolved by diuretics
      - `Y`: Edema despite diuretic therapy
    - Indicates severity of fluid retention

### Laboratory Values

11. **Bilirubin** (numeric)
    - Serum bilirubin level
    - Measured in milligrams per deciliter (mg/dl)
    - Elevated bilirubin indicates liver dysfunction
    - Normal range: typically 0.1-1.2 mg/dl

12. **Cholesterol** (numeric)
    - Serum cholesterol level
    - Measured in milligrams per deciliter (mg/dl)
    - May be elevated in liver disease

13. **Albumin** (numeric)
    - Serum albumin level
    - Measured in grams per deciliter (gm/dl)
    - Low albumin indicates liver dysfunction
    - Normal range: typically 3.5-5.0 gm/dl

14. **Copper** (numeric)
    - Urine copper level
    - Measured in micrograms per day (ug/day)
    - Elevated in primary biliary cirrhosis

15. **Alk_Phos** (numeric)
    - Alkaline phosphatase level
    - Measured in units per liter (U/liter)
    - Liver enzyme, elevated in liver disease

16. **SGOT** (numeric)
    - Serum glutamic-oxaloacetic transaminase (also known as AST)
    - Measured in units per milliliter (U/ml)
    - Liver enzyme, elevated in liver damage

17. **Tryglicerides** (numeric)
    - Triglycerides level
    - Measured in milligrams per deciliter (mg/dl)
    - **Note**: Column name in CSV is "Tryglicerides" (typo for "Triglycerides")
    - Blood lipid level

18. **Platelets** (numeric)
    - Platelet count
    - Measured per cubic milliliter, divided by 1000 (ml/1000)
    - Low platelets can indicate liver disease complications
    - Normal range: typically 150-450 × 10³/μL

19. **Prothrombin** (numeric)
    - Prothrombin time
    - Measured in seconds (s)
    - Measures blood clotting function
    - Prolonged time indicates liver dysfunction
    - Normal range: typically 10-13 seconds

### Disease Staging

20. **Stage** (categorical/numeric)
    - Histologic stage of disease
    - Values: `1`, `2`, `3`, `4`
    - Higher stages indicate more advanced disease
    - Distribution: Stage 1 (21, 5.0%), Stage 2 (92, 22.0%), Stage 3 (155, 37.1%), Stage 4 (144, 34.5%)

## Data Characteristics

### Primary Biliary Cirrhosis (PBC)

PBC is a chronic autoimmune liver disease that:
- Primarily affects women (reflected in the dataset: 89.5% female)
- Causes progressive destruction of bile ducts
- Leads to cirrhosis and liver failure
- Has no known cure, but treatment can slow progression

### Survival Analysis Context

This dataset is designed for **survival analysis**, which studies:
- Time until an event occurs (death, transplantation)
- Censoring (patients still alive or lost to follow-up)
- Factors that influence survival time

### Missing Values

The dataset contains some missing values (denoted as `NA` in the CSV):
- More complete data in the first 312 randomized cases
- Additional 106 cases may have more missing values
- Common missing variables: Cholesterol, Platelets, Tryglicerides

### Treatment Trial

- **Randomized controlled trial**: D-penicillamine vs. Placebo
- **312 patients** in the randomized trial
- **106 additional patients** followed for survival (not in trial)
- D-penicillamine was being tested as a treatment for PBC

## Usage

This dataset is suitable for:

- **Survival Analysis**: Analyzing time-to-event data (death, transplantation)
- **Predictive Modeling**: Predicting patient status or survival time
- **Clinical Research**: Understanding factors affecting PBC progression
- **Treatment Evaluation**: Comparing D-penicillamine vs. Placebo effectiveness
- **Risk Stratification**: Identifying high-risk patients based on clinical and laboratory features
- **Educational Purposes**: Teaching survival analysis and medical data analysis

## Important Considerations

1. **Survival Analysis**: This dataset is designed for survival analysis, not just classification. Consider:
   - Using survival analysis methods (Kaplan-Meier, Cox regression)
   - Accounting for censoring (Status = C or CL)
   - Time-to-event modeling (N_Days)

2. **Missing Values**: The dataset contains missing values. Consider:
   - Imputation strategies appropriate for medical data
   - Analyzing patterns in missing data
   - Using algorithms that handle missing values
   - The first 312 cases have more complete data

3. **Censoring**: Many patients are censored (alive at end of study or transplanted). Consider:
   - Censored observations provide valuable information
   - Survival analysis methods properly handle censoring
   - Simply classifying as "alive" vs. "dead" loses time information

4. **Age in Days**: Age is recorded in days, not years. Consider:
   - Converting to years for interpretability: Age (years) = Age (days) / 365.25
   - Or keeping in days if precision is important

5. **Sex Imbalance**: The dataset is heavily skewed toward women (89.5%). Consider:
   - This reflects the epidemiology of PBC (more common in women)
   - Analyzing men and women separately may be informative
   - Small sample size for men (44 cases) limits subgroup analysis

6. **Disease Stage**: Stage is an important prognostic factor. Consider:
   - Stage as a key predictor
   - Interactions between stage and other variables
   - Stage progression over time (if longitudinal data available)

7. **Laboratory Values**: Many laboratory values are included. Consider:
   - Normal ranges and clinical significance
   - Correlations between different lab values
   - Creating composite scores (e.g., MELD score components)

8. **Treatment Effect**: Drug assignment is available for randomized patients. Consider:
   - Analyzing treatment effect on survival
   - Comparing D-penicillamine vs. Placebo
   - Note: D-penicillamine was later found to have limited efficacy for PBC

## Evaluation Metrics

For survival analysis, consider:
- **Kaplan-Meier Curves**: Visualizing survival over time
- **Log-Rank Test**: Comparing survival between groups
- **Cox Proportional Hazards Model**: Multivariable survival analysis
- **C-index (Concordance Index)**: Measure of predictive accuracy
- **Time-dependent ROC curves**: For time-to-event prediction

For classification tasks (if converting to classification), consider:
- **Accuracy**: Overall classification accuracy
- **Precision, Recall, F1-Score**: Per-class metrics
- **Confusion Matrix**: Detailed breakdown
- **ROC-AUC**: For binary classification

## Medical Context

### Primary Biliary Cirrhosis (PBC)

- **Epidemiology**: More common in women (middle-aged)
- **Pathophysiology**: Autoimmune destruction of bile ducts
- **Progression**: Can lead to cirrhosis, liver failure, need for transplantation
- **Treatment**: Ursodeoxycholic acid (UDCA) is now standard treatment; D-penicillamine was tested but found ineffective

### Clinical Signs

- **Ascites**: Fluid in abdomen, indicates advanced disease
- **Hepatomegaly**: Enlarged liver
- **Spiders**: Spider angiomas, sign of liver disease
- **Edema**: Swelling, indicates fluid retention and liver dysfunction

### Laboratory Interpretation

- **Elevated Bilirubin**: Jaundice, liver dysfunction
- **Low Albumin**: Liver synthetic function impairment
- **Elevated Liver Enzymes**: Liver damage (Alk_Phos, SGOT)
- **Low Platelets**: May indicate portal hypertension
- **Prolonged Prothrombin Time**: Impaired blood clotting, liver dysfunction

## Feature Engineering Opportunities

1. **Age Conversion**: Convert age from days to years
2. **BMI**: Calculate Body Mass Index if weight/height available (not in this dataset)
3. **Lab Ratios**: 
   - Bilirubin/Albumin ratio
   - AST/ALT ratio (if ALT available)
4. **Composite Scores**: 
   - MELD score components
   - Child-Pugh score components
5. **Time Features**: 
   - Survival time in years
   - Risk groups based on N_Days

## Files

- `cirrhosis.csv`: Dataset in CSV format with all features

## Additional Notes

- The dataset represents real clinical trial data from Mayo Clinic
- Study period: 1974-1984 (historical data)
- D-penicillamine trial was conducted before current standard treatments
- The dataset is well-documented in survival analysis literature
- Missing values are present, especially in non-randomized cases
- Column name note: "Tryglicerides" in CSV (should be "Triglycerides")

## Citation

If you use this dataset, please cite:

**Primary Reference**:  
Fleming, T.R. and Harrington, D.P. (1991). Counting Processes and Survival Analysis. Wiley Series in Probability and Mathematical Statistics: Applied Probability and Statistics, John Wiley and Sons Inc., New York.

**Additional References**:  
- Dickson, et al., Hepatology 10:1-7 (1989)
- Markus, et al., N Eng J of Med 320:1709-13 (1989)

**Kaggle Citation**:  
fedesoriano. (August 2021). Cirrhosis Prediction Dataset. Retrieved [Date Retrieved] from https://www.kaggle.com/fedesoriano/cirrhosis-prediction-dataset.


