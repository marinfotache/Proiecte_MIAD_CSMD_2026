# Dermatology Dataset

## Overview

This database contains dermatological data for the differential diagnosis of erythemato-squamous diseases. The dataset includes both clinical and histopathological features to classify six different types of erythemato-squamous diseases.

## Source Information

**Original Owners**:
1. **Nilsel Ilter, M.D., Ph.D.**  
   Gazi University, School of Medicine  
   06510 Ankara, Turkey  
   Phone: +90 (312) 214 1080

2. **H. Altay Guvenir, PhD.**  
   Bilkent University, Department of Computer Engineering and Information Science  
   06533 Ankara, Turkey  
   Phone: +90 (312) 266 4133  
   Email: guvenir@cs.bilkent.edu.tr

**Donor**: H. Altay Guvenir (Bilkent University)

**Date**: January, 1998

## Citation

If you use this dataset, please cite:

**G. Demiroz, H. A. Govenir, and N. Ilter**, "Learning Differential Diagnosis of Eryhemato-Squamous Diseases using Voting Feature Intervals", Artificial Intelligence in Medicine.

## Dataset Information

- **Total Instances**: 366
- **Number of Attributes**: 34 (33 linear-valued + 1 nominal)
- **Data Format**: CSV (converted from ARFF format)
- **Task**: Multi-class classification (6 disease types)

## Problem Description

The differential diagnosis of erythemato-squamous diseases is a real problem in dermatology. These diseases all share the clinical features of erythema and scaling, with very little differences. The diseases in this group are:

1. **Psoriasis**
2. **Seboreic dermatitis**
3. **Lichen planus**
4. **Pityriasis rosea**
5. **Chronic dermatitis**
6. **Pityriasis rubra pilaris**

### Diagnostic Challenges

- Usually a biopsy is necessary for diagnosis, but these diseases share many histopathological features as well
- A disease may show the features of another disease at the beginning stage and may have the characteristic features at the following stages
- Patients were first evaluated clinically with 12 features, then skin samples were taken for the evaluation of 22 histopathological features

## Class Distribution

| Class Code | Disease | Number of Instances |
|------------|---------|-------------------|
| 1 | Psoriasis | 112 (30.6%) |
| 2 | Seboreic dermatitis | 61 (16.7%) |
| 3 | Lichen planus | 72 (19.7%) |
| 4 | Pityriasis rosea | 49 (13.4%) |
| 5 | Chronic dermatitis | 52 (14.2%) |
| 6 | Pityriasis rubra pilaris | 20 (5.5%) |

## Variable Descriptions

### Clinical Attributes

These attributes take values 0, 1, 2, 3 (unless otherwise indicated), where:
- **0**: Feature was not present
- **1, 2**: Relative intermediate values
- **3**: Largest amount possible

1. **erythema** (0-3)
   - Redness of the skin

2. **scaling** (0-3)
   - Presence of scales on the skin

3. **definite_borders** (0-3)
   - Clarity of lesion borders

4. **itching** (0-3)
   - Degree of itching

5. **koebner_phenomenon** (0-3)
   - Appearance of new lesions at sites of skin injury

6. **polygonal_papules** (0-3)
   - Presence of polygonal-shaped papules

7. **follicular_papules** (0-3)
   - Presence of follicular papules

8. **oral_mucosal_involvement** (0-3)
   - Involvement of oral mucosa

9. **knee_and_elbow_involvement** (0-3)
   - Involvement of knees and elbows

10. **scalp_involvement** (0-3)
    - Involvement of the scalp

11. **family_history** (0 or 1)
    - Family history of disease
    - **1**: If any of these diseases has been observed in the family
    - **0**: Otherwise

### Histopathological Attributes

These attributes take values 0, 1, 2, 3. The values of the histopathological features are determined by an analysis of the samples under a microscope.

12. **melanin_incontinence** (0-3)
    - Presence of melanin incontinence

13. **eosinophils_in_the_infiltrate** (0-2)
    - Presence of eosinophils in the infiltrate

14. **PNL_infiltrate** (0-3)
    - Polymorphonuclear leukocyte infiltrate

15. **fibrosis_of_the_papillary_dermis** (0-3)
    - Fibrosis in the papillary dermis

16. **exocytosis** (0-3)
    - Migration of inflammatory cells into the epidermis

17. **acanthosis** (0-3)
    - Thickening of the epidermis

18. **hyperkeratosis** (0-3)
    - Thickening of the stratum corneum

19. **parakeratosis** (0-3)
    - Retention of nuclei in the stratum corneum

20. **clubbing_of_the_rete_ridges** (0-3)
    - Clubbing of rete ridges

21. **elongation_of_the_rete_ridges** (0-3)
    - Elongation of rete ridges

22. **thinning_of_the_suprapapillary_epidermis** (0-3)
    - Thinning of the suprapapillary epidermis

23. **spongiform_pustule** (0-3)
    - Presence of spongiform pustules

24. **munro_microabcess** (0-3)
    - Presence of Munro microabscesses

25. **focal_hypergranulosis** (0-3)
    - Focal hypergranulosis

26. **disappearance_of_the_granular_layer** (0-3)
    - Disappearance of the granular layer

27. **vacuolisation_and_damage_of_basal_layer** (0-3)
    - Vacuolisation and damage of the basal layer

28. **spongiosis** (0-3)
    - Intercellular edema in the epidermis

29. **saw-tooth_appearance_of_retes** (0-3)
    - Saw-tooth appearance of rete ridges

30. **follicular_horn_plug** (0-3)
    - Follicular horn plug

31. **perifollicular_parakeratosis** (0-3)
    - Perifollicular parakeratosis

32. **inflammatory_monoluclear_inflitrate** (0-3)
    - Inflammatory mononuclear infiltrate

33. **band-like_infiltrate** (0-3)
    - Band-like infiltrate

### Demographic Attribute

34. **Age** (INTEGER)
    - Age of the patient
    - **Missing Values**: 8 instances have missing age values (marked as '?')

### Target Variable

35. **class** (categorical)
    - Disease classification
    - Values: `1`, `2`, `3`, `4`, `5`, `6`
    - Corresponds to the six disease types listed above

## Missing Values

- **Total Missing Values**: 8
- **Location**: All missing values are in the `Age` attribute
- **Representation**: Missing values are represented as `NA` in the CSV file (originally marked as '?' in the ARFF file)

## Data Characteristics

### Feature Value Interpretation

For clinical and histopathological features (except family_history and Age):
- **0**: Feature was not present
- **1**: Minimal presence
- **2**: Moderate presence
- **3**: Maximum/largest amount possible

### Data Collection Process

1. **Clinical Evaluation**: Patients were first evaluated clinically with 12 features
2. **Biopsy**: Skin samples were taken for histopathological evaluation
3. **Microscopic Analysis**: The values of the 22 histopathological features were determined by analysis of samples under a microscope

## Usage

This dataset is suitable for:

- **Multi-class Classification**: Predicting the type of erythemato-squamous disease
- **Medical Diagnosis Support**: Assisting in differential diagnosis of skin diseases
- **Feature Importance Analysis**: Understanding which clinical and histopathological features are most important for diagnosis
- **Medical Machine Learning**: Benchmarking classification algorithms on medical data
- **Educational Purposes**: Teaching machine learning with real medical data

## Important Considerations

1. **Class Imbalance**: The dataset has some class imbalance, with pityriasis rubra pilaris (class 6) having only 20 instances (5.5%) compared to psoriasis (class 1) with 112 instances (30.6%).

2. **Missing Values**: 8 instances have missing age values. Consider:
   - Imputation techniques (mean, median, mode)
   - Removing instances with missing values
   - Using algorithms that handle missing values

3. **Ordinal Features**: Most features are ordinal (0-3 scale), not strictly categorical or continuous. Consider:
   - Treating them as ordinal variables
   - Using ordinal encoding
   - Some algorithms may benefit from treating them as continuous

4. **Feature Types**: The dataset contains:
   - Clinical features (observable symptoms)
   - Histopathological features (microscopic analysis)
   - Demographic feature (age)
   - Family history (binary)

5. **Medical Context**: This is real medical data. Consider:
   - Privacy and ethical considerations
   - Clinical validation requirements
   - Regulatory compliance if used in medical applications

## Evaluation Metrics

For multi-class classification, consider:
- **Accuracy**: Overall classification accuracy
- **Confusion Matrix**: Detailed breakdown by class
- **Precision, Recall, F1-Score**: Per-class and macro/micro averages
- **Cohen's Kappa**: Agreement between predicted and actual classes

Given the class imbalance, consider:
- **Weighted F1-Score**: Accounts for class imbalance
- **Per-class metrics**: Evaluate performance for each disease type

## Related Research

**G. Demiroz, H. A. Govenir, and N. Ilter**, "Learning Differential Diagnosis of Eryhemato-Squamous Diseases using Voting Feature Intervals", Artificial Intelligence in Medicine.

## Files

- `dermatology.csv`: Dataset in CSV format with proper column headers
- `dermatology.arff`: Original dataset in ARFF (Attribute-Relation File Format)

## Additional Notes

- Patient names and ID numbers were recently removed from the database for privacy
- The dataset represents a real-world medical diagnosis problem with practical applications
- The combination of clinical and histopathological features makes this dataset valuable for understanding disease classification

