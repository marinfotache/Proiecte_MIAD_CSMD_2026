# Sleep Health and Lifestyle Dataset

## Overview

The Sleep Health and Lifestyle Dataset comprises 374 rows and 13 columns, covering a wide range of variables related to sleep and daily habits. It includes details such as gender, age, occupation, sleep duration, quality of sleep, physical activity level, stress levels, BMI category, blood pressure, heart rate, daily steps, and the presence or absence of sleep disorders.

This dataset provides a comprehensive view of sleep patterns and their relationship with lifestyle factors, making it valuable for understanding the factors that influence sleep quality and the occurrence of sleep disorders.

## Key Features of the Dataset

- **Comprehensive Sleep Metrics**: Explore sleep duration, quality, and factors influencing sleep patterns.
- **Lifestyle Factors**: Analyze physical activity levels, stress levels, and BMI categories.
- **Cardiovascular Health**: Examine blood pressure and heart rate measurements.
- **Sleep Disorder Analysis**: Identify the occurrence of sleep disorders such as Insomnia and Sleep Apnea.

## Dataset Information

- **Number of Rows**: 374
- **Number of Columns**: 13
- **Missing Values**: None
- **Target Variable**: `Sleep Disorder` (classification problem)

## Dataset Columns

### 1. Person ID
- **Type**: Numeric (Integer)
- **Description**: An identifier for each individual in the dataset.

### 2. Gender
- **Type**: Categorical
- **Description**: The gender of the person.
- **Values**: Male, Female
- **Distribution**: 
  - Male: 189 (50.5%)
  - Female: 185 (49.5%)

### 3. Age
- **Type**: Numeric (Integer)
- **Description**: The age of the person in years.

### 4. Occupation
- **Type**: Categorical
- **Description**: The occupation or profession of the person.
- **Sample Values**: Software Engineer, Doctor, Sales Representative, Teacher, Nurse, Engineer, Accountant, Scientist, Lawyer, Salesperson, etc.

### 5. Sleep Duration (hours)
- **Type**: Numeric (Float)
- **Description**: The number of hours the person sleeps per day.

### 6. Quality of Sleep (scale: 1-10)
- **Type**: Numeric (Integer)
- **Description**: A subjective rating of the quality of sleep, ranging from 1 to 10, where higher values indicate better sleep quality.

### 7. Physical Activity Level (minutes/day)
- **Type**: Numeric (Integer)
- **Description**: The number of minutes the person engages in physical activity daily.

### 8. Stress Level (scale: 1-10)
- **Type**: Numeric (Integer)
- **Description**: A subjective rating of the stress level experienced by the person, ranging from 1 to 10, where higher values indicate higher stress levels.

### 9. BMI Category
- **Type**: Categorical
- **Description**: The BMI category of the person.
- **Values**: Underweight, Normal, Normal Weight, Overweight, Obese
- **Distribution**:
  - Normal: 195 (52.1%)
  - Overweight: 148 (39.6%)
  - Normal Weight: 21 (5.6%)
  - Obese: 10 (2.7%)

### 10. Blood Pressure (systolic/diastolic)
- **Type**: Categorical (String)
- **Description**: The blood pressure measurement of the person, indicated as systolic pressure over diastolic pressure (e.g., "120/80").

### 11. Heart Rate (bpm)
- **Type**: Numeric (Integer)
- **Description**: The resting heart rate of the person in beats per minute.

### 12. Daily Steps
- **Type**: Numeric (Integer)
- **Description**: The number of steps the person takes per day.

### 13. Sleep Disorder
- **Type**: Categorical (Target Variable)
- **Description**: The presence or absence of a sleep disorder in the person.
- **Values**: None, Insomnia, Sleep Apnea
- **Distribution**:
  - None: 219 (58.6%)
  - Insomnia: 77 (20.6%)
  - Sleep Apnea: 78 (20.9%)

## Details about Sleep Disorder Column

- **None**: The individual does not exhibit any specific sleep disorder.
- **Insomnia**: The individual experiences difficulty falling asleep or staying asleep, leading to inadequate or poor-quality sleep.
- **Sleep Apnea**: The individual suffers from pauses in breathing during sleep, resulting in disrupted sleep patterns and potential health risks.

## Data Characteristics

### Class Distribution
The dataset shows a class imbalance in the target variable:
- **None** (no sleep disorder): 58.6% of cases
- **Insomnia**: 20.6% of cases
- **Sleep Apnea**: 20.9% of cases

This imbalance should be considered when building classification models. Techniques such as stratified sampling, class weighting, or resampling methods (SMOTE, undersampling, oversampling) may be beneficial.

### Data Quality
- **No Missing Values**: The dataset is complete with no missing values across all 13 columns.
- **Data Types**: The dataset contains a mix of numeric (continuous and discrete) and categorical variables.

## Usage

This dataset is suitable for:

1. **Classification Tasks**: Predict sleep disorders (Insomnia, Sleep Apnea, or None) based on lifestyle and health factors.
2. **Exploratory Data Analysis**: Understand relationships between sleep quality, lifestyle factors, and health metrics.
3. **Feature Engineering**: Create derived features such as:
   - Sleep efficiency (quality of sleep / sleep duration)
   - Activity-to-sleep ratio
   - Stress-to-sleep quality ratio
   - BMI category encoding
   - Blood pressure category extraction (normal, elevated, high)
4. **Correlation Analysis**: Examine correlations between sleep duration, quality, physical activity, stress, and sleep disorders.
5. **Healthcare Research**: Study the impact of lifestyle factors on sleep health.

## Considerations

1. **Class Imbalance**: The target variable has an imbalanced distribution. Consider using appropriate evaluation metrics (F1-score, precision, recall, ROC-AUC) and resampling techniques.

2. **Subjective Measures**: Quality of Sleep and Stress Level are subjective ratings (1-10 scale). Individual interpretations may vary.

3. **Blood Pressure Format**: Blood pressure is stored as a string in "systolic/diastolic" format. You may need to split this into two separate numeric columns for analysis.

4. **BMI Category Inconsistency**: Note that both "Normal" and "Normal Weight" categories exist. Consider consolidating these categories if needed.

5. **Synthetic Data**: This dataset is synthetic and created for illustrative purposes (see Acknowledgement section).

6. **Feature Scaling**: For machine learning models, consider scaling numeric features (Age, Sleep Duration, Physical Activity Level, Stress Level, Heart Rate, Daily Steps).

## Evaluation Metrics

For classification tasks, consider using:
- **Accuracy**: Overall correctness (may be misleading due to class imbalance)
- **Precision**: For each class (Insomnia, Sleep Apnea, None)
- **Recall**: For each class
- **F1-Score**: Harmonic mean of precision and recall (better for imbalanced data)
- **Macro-averaged F1**: Average F1-score across all classes
- **Weighted F1**: F1-score weighted by class frequency
- **Confusion Matrix**: Visualize classification performance
- **ROC-AUC**: For binary classification tasks (e.g., disorder vs. no disorder)

## Research Questions

Potential research questions to explore:
1. What lifestyle factors are most predictive of sleep disorders?
2. How do physical activity levels correlate with sleep quality?
3. What is the relationship between stress levels and sleep disorders?
4. Do certain occupations have higher rates of sleep disorders?
5. How do cardiovascular health indicators (blood pressure, heart rate) relate to sleep disorders?
6. What is the optimal sleep duration for different age groups and occupations?

## Feature Engineering Ideas

1. **Blood Pressure Parsing**: Split "Blood Pressure" into `systolic_bp` and `diastolic_bp` numeric columns.
2. **BMI Consolidation**: Merge "Normal" and "Normal Weight" into a single category if appropriate.
3. **Sleep Efficiency**: Calculate `Quality of Sleep / Sleep Duration`.
4. **Activity Intensity**: Categorize physical activity levels (Low: <30 min, Moderate: 30-60 min, High: >60 min).
5. **Stress Categories**: Categorize stress levels (Low: 1-3, Moderate: 4-6, High: 7-10).
6. **Age Groups**: Create age bins (e.g., 18-30, 31-45, 46-60, 60+).
7. **Steps Categories**: Categorize daily steps (Sedentary: <5000, Low: 5000-7500, Moderate: 7500-10000, High: >10000).

## Medical Notes

- **Sleep Duration**: The recommended sleep duration for adults is typically 7-9 hours per night. Values significantly outside this range may indicate sleep issues.
- **Quality of Sleep**: Subjective ratings can vary between individuals. Consider this when interpreting results.
- **Sleep Apnea**: Often associated with obesity, high blood pressure, and cardiovascular issues. Look for correlations with BMI and blood pressure.
- **Insomnia**: May be related to stress, anxiety, and lifestyle factors. Examine relationships with stress levels and occupation.

## Acknowledgement

I would like to clarify that the data I am presenting is synthetic and created by me for illustrative purposes.

---

**Note**: This dataset is intended for educational and research purposes. For clinical applications, consult with healthcare professionals and use validated medical datasets.

