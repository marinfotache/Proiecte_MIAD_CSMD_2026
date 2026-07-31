# Heart Failure Prediction Dataset

## Overview

Cardiovascular diseases (CVDs) are the number 1 cause of death globally, taking an estimated **17.9 million lives each year**, which accounts for **31% of all deaths worldwide**. Four out of 5 CVD deaths are due to heart attacks and strokes, and one-third of these deaths occur prematurely in people under 70 years of age. Heart failure is a common event caused by CVDs, and this dataset contains 11 features that can be used to predict a possible heart disease.

People with cardiovascular disease or who are at high cardiovascular risk (due to the presence of one or more risk factors such as hypertension, diabetes, hyperlipidaemia, or already established disease) need early detection and management, wherein a machine learning model can be of great help.

## Dataset Information

- **Total Instances**: 918
- **Number of Attributes**: 11 input features + 1 target variable
- **Data Format**: CSV
- **Task**: Binary classification (heart disease prediction)

## Target Variable

**HeartDisease** (binary)
- `1`: Heart disease present
- `0`: Normal (no heart disease)

### Class Distribution
- **Heart Disease (1)**: 508 instances (55.3%)
- **Normal (0)**: 410 instances (44.7%)

**Note**: The dataset is relatively balanced, with a slight majority of heart disease cases.

## Variable Descriptions

### Demographic Attributes

1. **Age** (numeric)
   - Age of the patient
   - Measured in years

2. **Sex** (categorical)
   - Sex of the patient
   - Values: `M` (Male), `F` (Female)
   - Distribution: Male (725, 79.0%), Female (193, 21.0%)

### Clinical Symptoms

3. **ChestPainType** (categorical)
   - Type of chest pain experienced
   - Values:
     - `TA`: Typical Angina
     - `ATA`: Atypical Angina
     - `NAP`: Non-Anginal Pain
     - `ASY`: Asymptomatic

### Vital Signs and Laboratory Values

4. **RestingBP** (numeric)
   - Resting blood pressure
   - Measured in millimeters of mercury (mm Hg)
   - Blood pressure measured while the patient is at rest

5. **Cholesterol** (numeric)
   - Serum cholesterol level
   - Measured in milligrams per deciliter (mg/dl)
   - Blood cholesterol concentration

6. **FastingBS** (binary)
   - Fasting blood sugar
   - Values: `1` (if FastingBS > 120 mg/dl), `0` (otherwise)
   - Indicates elevated fasting blood sugar, which may suggest diabetes or prediabetes

### Electrocardiographic Features

7. **RestingECG** (categorical)
   - Resting electrocardiogram results
   - Values:
     - `Normal`: Normal ECG
     - `ST`: Having ST-T wave abnormality (T wave inversions and/or ST elevation or depression of > 0.05 mV)
     - `LVH`: Showing probable or definite left ventricular hypertrophy by Estes' criteria

8. **MaxHR** (numeric)
   - Maximum heart rate achieved
   - Numeric value between 60 and 202
   - Typically measured during exercise stress testing

9. **ExerciseAngina** (binary)
   - Exercise-induced angina
   - Values: `Y` (Yes), `N` (No)
   - Indicates whether the patient experiences chest pain during exercise

10. **Oldpeak** (numeric)
    - ST depression
    - Numeric value measured in depression
    - Represents the ST segment depression observed during exercise testing

11. **ST_Slope** (categorical)
    - The slope of the peak exercise ST segment
    - Values:
      - `Up`: Upsloping
      - `Flat`: Flat
      - `Down`: Downsloping
    - Describes the pattern of the ST segment during peak exercise

### Target Variable

12. **HeartDisease** (binary)
    - Output class indicating presence of heart disease
    - Values: `1` (heart disease), `0` (Normal)
    - This is the target variable for prediction

## Medical Context

### Cardiovascular Disease Risk Factors

The dataset captures several important risk factors for cardiovascular disease:

- **Age**: Risk increases with age
- **Sex**: Men generally have higher risk at younger ages
- **Blood Pressure**: High resting blood pressure is a major risk factor
- **Cholesterol**: Elevated cholesterol contributes to atherosclerosis
- **Blood Sugar**: Elevated fasting blood sugar indicates diabetes/prediabetes risk
- **Chest Pain**: Different types of chest pain have different clinical significance
- **ECG Abnormalities**: ST-T wave changes and left ventricular hypertrophy indicate cardiac issues
- **Exercise Response**: Exercise-induced angina and ST changes during exercise are important diagnostic indicators

### Clinical Significance

- **Typical Angina (TA)**: Chest pain that occurs with exertion and is relieved by rest, highly suggestive of coronary artery disease
- **Atypical Angina (ATA)**: Chest pain with some but not all characteristics of typical angina
- **Non-Anginal Pain (NAP)**: Chest pain not characteristic of angina
- **Asymptomatic (ASY)**: No chest pain, but may still have underlying heart disease
- **ST-T Wave Abnormalities**: Can indicate ischemia, myocardial infarction, or other cardiac conditions
- **Left Ventricular Hypertrophy (LVH)**: Thickening of the heart muscle, often due to hypertension

## Usage

This dataset is suitable for:

- **Binary Classification**: Predicting heart disease based on clinical and demographic features
- **Medical Diagnosis Support**: Assisting in early detection of cardiovascular disease
- **Risk Stratification**: Identifying patients at high risk for heart disease
- **Feature Importance Analysis**: Understanding which factors are most predictive of heart disease
- **Healthcare Analytics**: Analyzing patterns in cardiovascular risk factors
- **Educational Purposes**: Teaching classification algorithms with medical data

## Important Considerations

1. **Class Balance**: The dataset is relatively balanced (55.3% vs 44.7%), but consider:
   - Using appropriate evaluation metrics (precision, recall, F1-score, ROC-AUC)
   - The slight imbalance may still warrant attention depending on the application

2. **Sex Distribution**: The dataset has a significant imbalance in sex distribution (79% male, 21% female). Consider:
   - Analyzing performance separately by sex
   - Ensuring models don't overfit to sex as a predictor
   - Accounting for sex-specific risk patterns

3. **Clinical Features**: The dataset includes both subjective (chest pain type) and objective (ECG, lab values) features. Consider:
   - The reliability and reproducibility of different feature types
   - Missing data patterns (if any)
   - Clinical interpretation of feature combinations

4. **Medical Context**: 
   - This dataset should not replace professional medical diagnosis
   - Always consult healthcare professionals for actual diagnosis
   - Consider regulatory and ethical implications for medical AI applications

5. **Feature Engineering**: Consider:
   - Creating composite risk scores
   - Age-sex interactions
   - Normalizing continuous variables
   - Handling potential outliers in vital signs

6. **Data Quality**: 
   - Verify reasonable ranges for continuous variables (e.g., blood pressure, cholesterol, heart rate)
   - Check for missing values
   - Validate categorical variable encodings

## Evaluation Metrics

For binary classification, consider:
- **Accuracy**: Overall classification accuracy
- **Precision**: Of predicted heart disease cases, how many actually have heart disease?
- **Recall (Sensitivity)**: Of actual heart disease cases, how many did we correctly identify?
- **Specificity**: Of actual normal cases, how many did we correctly identify?
- **F1-Score**: Harmonic mean of precision and recall
- **ROC-AUC**: Area under the ROC curve
- **Confusion Matrix**: Detailed breakdown of predictions

Given the medical context, **recall (sensitivity)** is particularly important - we want to minimize false negatives (missing actual heart disease cases).

## Medical Notes

### Early Detection Importance

Early detection of cardiovascular disease is crucial because:
- Early intervention can prevent or delay complications
- Lifestyle changes and medications can be more effective when implemented early
- Regular monitoring can help manage the condition better
- One-third of CVD deaths occur prematurely in people under 70 years of age

### Risk Factors Captured

The dataset includes several modifiable and non-modifiable risk factors:
- **Non-modifiable**: Age, Sex
- **Modifiable**: Blood pressure, cholesterol, blood sugar, exercise capacity
- **Clinical indicators**: Chest pain, ECG changes, exercise response

### Clinical Workflow

In clinical practice, these features are typically collected through:
- Patient history and physical examination
- Resting electrocardiogram
- Exercise stress testing
- Laboratory blood tests

## Files

- `heart_failure.csv`: Dataset in CSV format with all features and target variable

## Additional Resources

- **World Health Organization (WHO)**: Cardiovascular diseases fact sheets and statistics
- **American Heart Association**: Heart disease and stroke statistics
- **Centers for Disease Control and Prevention (CDC)**: Heart disease information
- **European Society of Cardiology**: Clinical guidelines and resources

## Disclaimer

This dataset is intended for educational and research purposes only. It should not be used for actual medical diagnosis. Always consult qualified healthcare professionals for medical advice, diagnosis, and treatment. Machine learning models should be validated in clinical settings before use in medical decision-making.

