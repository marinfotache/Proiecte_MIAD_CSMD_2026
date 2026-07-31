# Vehicle Claims Dataset

## Overview

This dataset contains vehicle insurance claims data designed for **unsupervised anomaly detection for auditing data**. The dataset includes information about vehicles, their characteristics, reported issues, and repair details. It is particularly useful for studying the impact of categorical encodings on anomaly detection algorithms and identifying fraudulent or anomalous claims.

## Source

**Dataset**: Vehicle Claims  
**Reference**: https://paperswithcode.com/dataset/vehicle-claims

**Research Context**: Unsupervised Anomaly Detection for Auditing Data and Impact of Categorical Encodings

## Dataset Information

- **Total Instances**: 268,255
- **Number of Attributes**: 25 (vehicle characteristics, issue details, repair information, and anomaly labels)
- **Data Format**: CSV
- **Task**: Unsupervised anomaly detection (with labeled anomalies for evaluation)

## Target Variables

The dataset includes two anomaly labels:

1. **Label** (binary)
   - Overall anomaly label
   - Values: `0` (normal), `1` (anomaly)
   - Distribution: Normal (211,506, 78.9%), Anomaly (56,749, 21.1%)

2. **category_anomaly** (binary)
   - Categorical anomaly label
   - Values: `0` (normal), `1` (anomaly)
   - Distribution: Normal (243,287, 90.7%), Anomaly (24,968, 9.3%)

## Variable Descriptions

### Vehicle Identification

1. **Maker** (categorical)
   - The brand of the vehicle
   - Examples: Bentley, BMW, Audi, etc.

2. **Genmodel** (categorical)
   - The model of the vehicle
   - Specific model name within the brand

3. **Genmodel_ID** (categorical)
   - Model identifier code
   - Encoded identifier for the specific model variant

### Vehicle Characteristics

4. **Color** (categorical)
   - Color of the vehicle
   - Examples: Silver, Grey, Blue, Black, White, Green, etc.

5. **Reg_year** (numeric/categorical)
   - Year of registration
   - The year when the vehicle was first registered

6. **Bodytype** (categorical)
   - Body type of the vehicle
   - Examples: Saloon, SUV, Convertible, Hatchback, Estate, etc.

7. **Runned_Miles** (numeric)
   - Distance covered by the vehicle
   - Total mileage/odometer reading in miles
   - Measured in miles

8. **Engin_size** (numeric/categorical)
   - Size of engine
   - Engine displacement (e.g., 6.8L, 4.4L, 2.0L)

9. **Gearbox** (categorical)
   - Transmission type
   - Values: `Automatic`, `Manual`

10. **Fuel_type** (categorical)
    - Type of fuel
    - Values: `Petrol`, `Diesel`, etc.

11. **Price** (numeric)
    - Price of the vehicle
    - Vehicle price in currency units

12. **Seat_num** (numeric)
    - Number of seats
    - Total seating capacity

13. **Door_num** (numeric)
    - Number of doors
    - Total number of doors on the vehicle

### Advertisement/Listing Information

14. **Adv_year** (numeric)
    - Year of advertisement/listing
    - Year when the vehicle was advertised

15. **Adv_month** (numeric)
    - Month of advertisement/listing
    - Month (1-12) when the vehicle was advertised

16. **Adv_day** (numeric)
    - Day of advertisement/listing
    - Day of month when the vehicle was advertised

### Issue Information

17. **issue** (categorical)
    - Type of damage or issue
    - Examples: Starter Motor Issue, Radiator Leaking, Steering Wheel Shaking, Electrical Issue, Windscreen Crack, Tyre Alignment, Sensor Malfunction, Flat Tyres, Transmission Issue, Gear Box Issue, Brake Pads Worn, Excessive Emissions, etc.

18. **issue_id** (categorical/numeric)
    - Specific damage identifier
    - More specific classification or ID for the issue type

### Repair Information

19. **repair_complexity** (categorical/numeric)
    - Difficulty to repair the vehicle
    - Likely a scale indicating repair complexity (e.g., 1-5 or categorical levels)

20. **repair_hours** (numeric)
    - Time required to finish the job
    - Number of hours needed for repair
    - Measured in hours

21. **repair_cost** (numeric)
    - Cost of repair
    - Total repair cost in currency units

### Temporal Information

22. **breakdown_date** (date)
    - Date when the vehicle broke down
    - Date format: YYYY-MM-DD

23. **repair_date** (date)
    - Date when the repair was completed
    - Date format: YYYY-MM-DD
    - **Note**: Can be used to calculate repair duration (days between breakdown and repair)

### Anomaly Labels

24. **Label** (binary)
    - Overall anomaly label
    - `0`: Normal claim
    - `1`: Anomalous claim
    - Used for evaluation of anomaly detection models

25. **category_anomaly** (binary)
    - Categorical anomaly label
    - `0`: Normal claim
    - `1`: Categorical anomaly
    - Indicates anomalies related to categorical feature patterns

## Data Characteristics

### Anomaly Detection Context

This dataset is designed for **unsupervised anomaly detection** in auditing scenarios. Anomalies may include:
- Fraudulent claims
- Unusual repair patterns
- Suspicious combinations of vehicle characteristics and issues
- Unrealistic repair costs or durations
- Inconsistent temporal patterns

### Temporal Anomalies

The `breakdown_date` and `repair_date` attributes were added with the idea of inserting anomalies based on the number of days required to repair the vehicle. This allows for:
- Detection of unusually long repair times
- Identification of temporal inconsistencies
- Analysis of repair duration patterns

### Categorical Encoding Impact

This dataset is particularly useful for studying the **impact of categorical encodings** on anomaly detection performance. With many categorical attributes (Maker, Genmodel, Color, Bodytype, Gearbox, Fuel_type, issue, etc.), different encoding strategies can significantly affect anomaly detection results.

## Usage

This dataset is suitable for:

- **Unsupervised Anomaly Detection**: Identifying fraudulent or anomalous vehicle insurance claims
- **Categorical Encoding Research**: Studying how different encoding methods (one-hot, target encoding, label encoding, etc.) affect anomaly detection
- **Fraud Detection**: Detecting suspicious patterns in insurance claims
- **Auditing Applications**: Identifying unusual patterns for manual review
- **Feature Engineering**: Creating derived features (e.g., repair duration, age of vehicle, etc.)
- **Benchmarking**: Comparing different anomaly detection algorithms
- **Educational Purposes**: Teaching anomaly detection with real-world insurance data

## Important Considerations

1. **Anomaly Labels**: The dataset includes two anomaly labels (`Label` and `category_anomaly`). Consider:
   - Using labels only for evaluation, not for training (unsupervised setting)
   - Understanding the difference between the two label types
   - The labels may represent different types of anomalies

2. **Class Imbalance**: Anomalies are typically rare (21.1% for Label, 9.3% for category_anomaly). Consider:
   - Using appropriate evaluation metrics (precision, recall, F1-score, ROC-AUC)
   - The imbalance reflects real-world anomaly detection scenarios
   - Focus on recall (detecting true anomalies) may be more important than precision

3. **Categorical Variables**: Many attributes are categorical. Consider:
   - Testing different encoding strategies (one-hot, target encoding, frequency encoding, etc.)
   - The impact of encoding on anomaly detection is a key research question
   - Some algorithms may require specific encoding approaches

4. **Temporal Features**: The dataset includes temporal information. Consider:
   - Creating derived features (repair duration, vehicle age, etc.)
   - Analyzing temporal patterns
   - Using breakdown_date and repair_date to identify temporal anomalies

5. **Missing Values**: Check for missing values in the dataset and handle appropriately:
   - Imputation strategies
   - Treating missing values as a separate category
   - Using algorithms that handle missing values

6. **Data Quality**: 
   - Verify reasonable ranges for numeric variables
   - Check for inconsistencies (e.g., repair_date before breakdown_date)
   - Validate categorical variable values

7. **Evaluation Attributes**: According to the source, some attributes may not be used for evaluation in the original research. Consider:
   - Focusing on the core attributes mentioned in the description
   - Understanding which attributes are most relevant for anomaly detection

## Evaluation Metrics

For anomaly detection, consider:

- **Precision**: Of predicted anomalies, how many are actually anomalies?
- **Recall (Sensitivity)**: Of actual anomalies, how many did we correctly identify?
- **F1-Score**: Harmonic mean of precision and recall
- **ROC-AUC**: Area under the ROC curve
- **Precision-Recall AUC**: Area under the precision-recall curve (better for imbalanced data)
- **Confusion Matrix**: Detailed breakdown of predictions

Given the imbalanced nature of anomaly detection, **recall** is often prioritized to minimize false negatives (missing actual anomalies).

## Feature Engineering Opportunities

1. **Temporal Features**:
   - Repair duration (days between breakdown_date and repair_date)
   - Vehicle age (current year - Reg_year)
   - Time since advertisement (breakdown_date - advertisement date)

2. **Derived Features**:
   - Cost per hour (repair_cost / repair_hours)
   - Mileage per year (Runned_Miles / vehicle age)
   - Price per mile (Price / Runned_Miles)

3. **Categorical Interactions**:
   - Maker × Bodytype combinations
   - Issue type × Repair complexity interactions
   - Fuel type × Engine size combinations

## Files

- `vehicle_claims_labeled.csv`: Dataset with anomaly labels (this file)
- `vehicle_claims.csv`: Dataset without labels (for unsupervised learning)

## Additional Notes

- The dataset is designed for research on unsupervised anomaly detection
- Categorical encoding impact is a key research focus
- Temporal anomalies based on repair duration are included
- The dataset represents real-world insurance claims scenarios
- Large dataset size (268K+ instances) allows for robust model training and evaluation

## Research Applications

This dataset is particularly valuable for:
- Comparing categorical encoding methods (one-hot, target encoding, frequency encoding, etc.)
- Evaluating unsupervised anomaly detection algorithms (Isolation Forest, LOF, Autoencoders, etc.)
- Studying the impact of feature engineering on anomaly detection
- Developing fraud detection systems for insurance claims
- Benchmarking anomaly detection algorithms on real-world data

## Citation

If you use this dataset, please cite:
- Papers with Code: https://paperswithcode.com/dataset/vehicle-claims
- Original research on "Unsupervised Anomaly Detection for Auditing Data and Impact of Categorical Encodings"

