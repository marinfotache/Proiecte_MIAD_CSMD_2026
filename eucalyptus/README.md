# Eucalyptus Soil Conservation Dataset

## Overview

This dataset contains experimental data from eucalyptus trials conducted in New Zealand's North Island. The objective was to determine which seedlots in a species are best for soil conservation in seasonally dry hill country. The determination is based on measurement of height, diameter by height, survival, and other contributing factors.

## Source Information

**Data Source**: Bruce Bulloch  
128 Cook Street  
Palmerston North  
New Zealand

## Dataset Information

- **Total Instances**: 736
- **Number of Attributes**: 19 input attributes + 1 target variable
- **Data Format**: CSV (converted from ARFF format)
- **Task**: Multi-class classification (predicting utility rating)

## Objective

The primary objective of this dataset is to identify which eucalyptus seedlots are best suited for soil conservation in seasonally dry hill country environments. This is determined through various measurements including:
- Height growth
- Diameter at base height (DBH)
- Survival rates
- Vigour assessment
- Insect resistance
- Form characteristics (stem, crown, branch)

## Target Variable

**Utility** (categorical)
- Overall utility rating for soil conservation purposes
- Values: `none`, `low`, `average`, `good`, `best`

### Class Distribution

| Utility Rating | Number of Instances | Percentage |
|----------------|---------------------|------------|
| none | 180 | 24.5% |
| low | 107 | 14.5% |
| average | 130 | 17.7% |
| good | 214 | 29.1% |
| best | 105 | 14.3% |

## Variable Descriptions

### Site Information

1. **Abbrev** (categorical)
   - Site abbreviation code
   - Values: `Cra`, `Cly`, `Nga`, `Wai`, `K81`, `Wak`, `K82`, `WSp`, `K83`, `Lon`, `Puk`, `Paw`, `K81a`, `Mor`, `Wen`, `WSh`

2. **Rep** (numeric, integer)
   - Site replication number
   - Indicates which replicate of the experiment this observation belongs to

3. **Locality** (categorical)
   - Site locality in the North Island of New Zealand
   - Values: `Central_Hawkes_Bay`, `Northern_Hawkes_Bay`, `Southern_Hawkes_Bay`, `Central_Hawkes_Bay_(coastal)`, `Central_Wairarapa`, `South_Wairarapa`, `Southern_Hawkes_Bay_(coastal)`, `Central_Poverty_Bay`

4. **Map_Ref** (categorical)
   - Map location reference in the North Island
   - Grid reference format (e.g., `N135_382/137`)

5. **Latitude** (categorical)
   - Latitude approximation
   - Values encoded (e.g., `39__38`, `40__11`, `41__12`)

### Environmental Factors

6. **Altitude** (numeric, integer)
   - Altitude approximation
   - Measured in meters above sea level

7. **Rainfall** (numeric, integer)
   - Annual rainfall
   - Measured in millimeters per annum (mm pa)

8. **Frosts** (numeric, integer)
   - Frost severity
   - Measured in degrees Celsius (deg. C)
   - Negative values indicate freezing temperatures

9. **Year** (numeric, integer)
   - Year of planting
   - Indicates when the trial was established

### Species and Seedlot Information

10. **Sp** (categorical)
    - Species code
    - Eucalyptus species abbreviations
    - Values: `co`, `fr`, `ma`, `nd`, `ni`, `ob`, `ov`, `pu`, `rd`, `si`, `mn`, `ag`, `bxs`, `br`, `el`, `fa`, `jo`, `ka`, `re`, `sm`, `ro`, `nc`, `am`, `cr`, `pa`, `ra`, `te`

11. **PMCno** (numeric, integer)
    - Seedlot number (Plant Material Center number)
    - Unique identifier for the seedlot
    - **Missing Values**: 7 instances

### Growth Measurements

12. **DBH** (numeric, real)
    - Diameter at base height
    - Measured in centimeters (cm)
    - Best diameter measurement at base height
    - **Missing Values**: 1 instance

13. **Ht** (numeric, real)
    - Height
    - Measured in meters (m)
    - **Missing Values**: 1 instance

### Performance Attributes

14. **Surv** (numeric, integer)
    - Survival
    - Likely a percentage or count of surviving trees
    - **Missing Values**: 94 instances
    - **Note**: Missing data could indicate species death or lack of data collection

15. **Vig** (numeric, real)
    - Vigour rating
    - Assessment of plant health and growth vigor
    - **Missing Values**: 69 instances

16. **Ins_res** (numeric, real)
    - Insect resistance rating
    - Assessment of resistance to insect damage
    - **Missing Values**: 69 instances

### Form Characteristics

17. **Stem_Fm** (numeric, real)
    - Stem form rating
    - Assessment of stem quality and form
    - **Missing Values**: 69 instances

18. **Crown_Fm** (numeric, real)
    - Crown form rating
    - Assessment of crown shape and quality
    - **Missing Values**: 69 instances

19. **Brnch_Fm** (numeric, real)
    - Branch form rating
    - Assessment of branch structure and quality
    - **Missing Values**: 69 instances

### Target Variable

20. **Utility** (categorical)
    - Overall utility rating for soil conservation
    - Values: `none`, `low`, `average`, `good`, `best`
    - This is the target variable for classification

## Missing Values

The dataset contains **448 total missing values** across several columns:

- **PMCno**: 7 missing values
- **DBH**: 1 missing value
- **Ht**: 1 missing value
- **Surv**: 94 missing values
- **Vig**: 69 missing values
- **Ins_res**: 69 missing values
- **Stem_Fm**: 69 missing values
- **Crown_Fm**: 69 missing values
- **Brnch_Fm**: 69 missing values

### Missing Value Notes

According to the dataset documentation:

1. **Experimental Recording Procedures**: 
   - If a species was absent from one replicate at a site, it was treated as a missing value
   - If absent from two or more replicates at a site, the species was excluded from the site's analyses

2. **Morea Station Data**: 
   - Missing data is particularly common for survival, vigour, insect resistance, stem form, crown form, and utility at the Morea Station
   - This could indicate:
     - Death of species in these areas
     - Lack of data collection

## Experimental Context

### Trial Methods Evolution

**Important Note**: Eucalypt trial methods changed over time:
- **Earlier trials**: Mostly included 15-30cm tall seedlings grown in peat plots
- **Later trials**: Mostly included three replications of eight trees grown

This methodological change may contribute to less significant results and should be considered when analyzing the data.

### Data Collection

The dataset represents field trials where:
- Multiple eucalyptus species were tested
- Multiple seedlots (genetic variants) were evaluated
- Trials were conducted across different sites in the North Island
- Environmental conditions (altitude, rainfall, frosts) varied by location
- Multiple replicates were used to account for variability

## Usage

This dataset is suitable for:

- **Multi-class Classification**: Predicting utility rating based on species, environmental factors, and growth characteristics
- **Species Selection**: Identifying which eucalyptus species and seedlots perform best for soil conservation
- **Environmental Analysis**: Understanding how environmental factors (altitude, rainfall, frosts) affect tree performance
- **Agricultural/Forestry Research**: Supporting decision-making for soil conservation plantings
- **Feature Importance Analysis**: Determining which factors most strongly influence utility rating

## Important Considerations

1. **Missing Values**: The dataset has significant missing values, particularly in performance attributes. Consider:
   - Imputation techniques appropriate for the data type
   - Removing instances with excessive missing values
   - Using algorithms that handle missing values
   - Analyzing patterns in missing data (e.g., by site or species)

2. **Temporal Changes**: Trial methods changed over time, which may affect data consistency. Consider:
   - Including year as a feature
   - Analyzing performance by time period
   - Being cautious when comparing early vs. late trials

3. **Site-Specific Effects**: Different sites have different environmental conditions. Consider:
   - Including site information in models
   - Analyzing performance by locality
   - Accounting for spatial correlation

4. **Replication**: The dataset includes replication information. Consider:
   - Accounting for within-site correlation
   - Using appropriate statistical methods for repeated measures
   - Analyzing variability within replicates

5. **Class Imbalance**: The utility classes are somewhat imbalanced (ranging from 14.3% to 29.1%). Consider:
   - Using appropriate evaluation metrics
   - Applying resampling techniques if needed
   - Using class weights in algorithms

6. **Categorical Variables**: Several categorical variables have many levels (e.g., species codes, localities). Consider:
   - Encoding strategies (one-hot, target encoding, etc.)
   - Feature selection to reduce dimensionality
   - Grouping rare categories if appropriate

## Evaluation Metrics

For multi-class classification, consider:
- **Accuracy**: Overall classification accuracy
- **Confusion Matrix**: Detailed breakdown by utility class
- **Precision, Recall, F1-Score**: Per-class and macro/micro averages
- **Cohen's Kappa**: Agreement between predicted and actual classes
- **Weighted Metrics**: Account for class imbalance

## Agricultural/Forestry Context

### Soil Conservation

Eucalyptus species are often used for:
- Erosion control on slopes
- Windbreaks
- Land rehabilitation
- Agroforestry systems

### Selection Criteria

When selecting species for soil conservation, important factors include:
- **Survival**: Ability to establish and persist
- **Growth**: Height and diameter development
- **Form**: Stem, crown, and branch quality
- **Resistance**: To pests, diseases, and environmental stress
- **Vigour**: Overall health and growth performance

## Files

- `eucalyptus.csv`: Dataset in CSV format with proper column headers
- `eucalyptus.arff`: Original dataset in ARFF (Attribute-Relation File Format)

## Additional Notes

- The dataset represents real-world agricultural/forestry research data
- Geographic focus: North Island of New Zealand
- Application: Soil conservation in seasonally dry hill country
- The data spans multiple years (1980s based on year values)
- Multiple species and seedlots were tested to find optimal selections

