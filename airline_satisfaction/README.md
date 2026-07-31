# Airline Passenger Satisfaction Dataset

## Overview

This dataset contains an airline passenger satisfaction survey. The dataset is designed to help identify what factors are highly correlated to a satisfied (or dissatisfied) passenger and to predict passenger satisfaction. This dataset has been cleaned up for the purposes of classification.

## Context

Understanding passenger satisfaction is crucial for airlines to improve their services, retain customers, and enhance the overall travel experience. This dataset provides comprehensive information about passengers' experiences across various service dimensions, allowing for analysis of satisfaction drivers and predictive modeling.

## Source

**Original Dataset**: Modified from a dataset by John D  
**Note**: This dataset has been cleaned up for classification purposes.

## Dataset Information

- **Total Instances**: 103,904
- **Number of Attributes**: 24 input features + 1 target variable
- **Data Format**: CSV
- **Task**: Binary/Multi-class classification (predicting passenger satisfaction)

## Target Variable

**satisfaction** (categorical)
- Airline satisfaction level
- Values: `satisfied`, `neutral or dissatisfied`

### Class Distribution
- **Satisfied**: 45,025 instances (43.3%)
- **Neutral or Dissatisfied**: 58,879 instances (56.7%)

**Note**: The dataset is slightly imbalanced, with more neutral/dissatisfied passengers than satisfied ones.

## Variable Descriptions

### Demographic and Customer Information

1. **id** (numeric)
   - Unique identifier for each passenger
   - Passenger ID number

2. **Gender** (categorical)
   - Gender of the passengers
   - Values: `Female`, `Male`

3. **Customer Type** (categorical)
   - The customer type
   - Values: `Loyal Customer`, `disloyal Customer`
   - Indicates whether the customer is a loyal/repeat customer or not

4. **Age** (numeric)
   - The actual age of the passengers
   - Measured in years
   - Range: 7-85 years

### Travel Information

5. **Type of Travel** (categorical)
   - Purpose of the flight of the passengers
   - Values: `Personal Travel`, `Business travel`
   - Indicates whether the trip is for business or personal reasons

6. **Class** (categorical)
   - Travel class in the plane of the passengers
   - Values: `Business`, `Eco`, `Eco Plus`
   - Represents the service class booked

7. **Flight Distance** (numeric)
   - The flight distance of this journey
   - Measured in miles or kilometers
   - Total distance traveled

### Service Satisfaction Ratings

All service satisfaction attributes are rated on a scale of 0-5, where:
- **0**: Not Applicable
- **1-5**: Satisfaction level (1 = very dissatisfied, 5 = very satisfied)

8. **Inflight wifi service** (numeric, 0-5)
   - Satisfaction level of the inflight wifi service
   - 0 = Not Applicable; 1-5 = Satisfaction rating

9. **Departure/Arrival time convenient** (numeric, 0-5)
   - Satisfaction level of departure/arrival time convenience
   - How convenient the scheduled times were for the passenger

10. **Ease of Online booking** (numeric, 0-5)
    - Satisfaction level of online booking
    - How easy it was to book the flight online

11. **Gate location** (numeric, 0-5)
    - Satisfaction level of gate location
    - Convenience and accessibility of the boarding gate

12. **Food and drink** (numeric, 0-5)
    - Satisfaction level of food and drink service
    - Quality and availability of food and beverages

13. **Online boarding** (numeric, 0-5)
    - Satisfaction level of online boarding
    - Experience with online check-in and boarding process

14. **Seat comfort** (numeric, 0-5)
    - Satisfaction level of seat comfort
    - Comfort level of the aircraft seat

15. **Inflight entertainment** (numeric, 0-5)
    - Satisfaction level of inflight entertainment
    - Quality and variety of entertainment options

16. **On-board service** (numeric, 0-5)
    - Satisfaction level of on-board service
    - Quality of service provided by flight attendants

17. **Leg room service** (numeric, 0-5)
    - Satisfaction level of leg room
    - Amount of legroom and space available

18. **Baggage handling** (numeric, 0-5)
    - Satisfaction level of baggage handling
    - Experience with checked baggage service

19. **Checkin service** (numeric, 0-5)
    - Satisfaction level of check-in service
    - Experience at the check-in counter or online check-in

20. **Inflight service** (numeric, 0-5)
    - Satisfaction level of inflight service
    - Overall service quality during the flight

21. **Cleanliness** (numeric, 0-5)
    - Satisfaction level of cleanliness
    - Cleanliness of the aircraft, seats, and facilities

### Operational Information

22. **Departure Delay in Minutes** (numeric)
    - Minutes delayed when departure
    - Flight departure delay in minutes
    - 0 indicates no delay

23. **Arrival Delay in Minutes** (numeric)
    - Minutes delayed when arrival
    - Flight arrival delay in minutes
    - 0 indicates no delay
    - May be affected by departure delays and in-flight adjustments

### Target Variable

24. **satisfaction** (categorical)
    - Airline satisfaction level
    - Values: `satisfied`, `neutral or dissatisfied`
    - This is the target variable for prediction

## Data Characteristics

### Satisfaction Rating Scale

All service satisfaction attributes use a consistent 0-5 scale:
- **0**: Not Applicable (service not available or not used)
- **1**: Very Dissatisfied
- **2**: Dissatisfied
- **3**: Neutral
- **4**: Satisfied
- **5**: Very Satisfied

### Key Factors for Satisfaction

Based on the dataset structure, satisfaction may be influenced by:
- **Service Quality**: Multiple service dimensions (wifi, food, entertainment, etc.)
- **Operational Performance**: Flight delays (departure and arrival)
- **Customer Profile**: Loyalty status, travel type, class
- **Demographics**: Age, gender
- **Travel Characteristics**: Flight distance, class of service

### Delay Impact

Flight delays (both departure and arrival) are likely important factors:
- Delays can significantly impact passenger satisfaction
- Arrival delays may compound departure delays
- Zero delays may correlate with higher satisfaction

## Usage

This dataset is suitable for:

- **Binary Classification**: Predicting passenger satisfaction (satisfied vs. neutral/dissatisfied)
- **Customer Satisfaction Analysis**: Identifying key drivers of satisfaction
- **Service Quality Assessment**: Understanding which service aspects most impact satisfaction
- **Customer Segmentation**: Analyzing satisfaction patterns by customer type, travel class, etc.
- **Predictive Analytics**: Building models to predict satisfaction for new passengers
- **Business Intelligence**: Informing service improvement strategies
- **Educational Purposes**: Teaching classification algorithms with real-world business data

## Important Considerations

1. **Class Imbalance**: The dataset has slight imbalance (56.7% neutral/dissatisfied vs. 43.3% satisfied). Consider:
   - Using appropriate evaluation metrics (precision, recall, F1-score, ROC-AUC)
   - Applying resampling techniques if needed
   - Using class weights in algorithms

2. **Rating Scale Interpretation**: Service ratings use 0-5 scale where 0 means "Not Applicable". Consider:
   - Treating 0 as missing data or as a separate category
   - Analyzing patterns in "Not Applicable" responses
   - Some services may not be available in all classes

3. **Delay Variables**: Both departure and arrival delays are included. Consider:
   - Creating derived features (total delay, delay ratio, etc.)
   - Analyzing correlation between delays and satisfaction
   - Handling cases where delays are 0 (no delay)

4. **Customer Loyalty**: The "Customer Type" variable distinguishes loyal vs. disloyal customers. Consider:
   - Loyal customers may have different expectations
   - Loyalty may correlate with satisfaction patterns
   - Important for customer retention analysis

5. **Travel Context**: Type of travel (Business vs. Personal) and Class may strongly influence satisfaction. Consider:
   - Business travelers may have different priorities
   - Class differences in service expectations
   - Interaction effects between travel type and class

6. **Feature Engineering**: Consider creating:
   - Average service rating across all services
   - Number of services rated as "Not Applicable"
   - Delay impact score
   - Service quality composite scores

7. **Missing Values**: Check for missing values and handle appropriately:
   - Some service ratings may be missing
   - Delay information should be verified

## Evaluation Metrics

For binary classification, consider:
- **Accuracy**: Overall classification accuracy
- **Precision**: Of predicted satisfied passengers, how many are actually satisfied?
- **Recall (Sensitivity)**: Of actual satisfied passengers, how many did we correctly identify?
- **Specificity**: Of actual neutral/dissatisfied passengers, how many did we correctly identify?
- **F1-Score**: Harmonic mean of precision and recall
- **ROC-AUC**: Area under the ROC curve
- **Confusion Matrix**: Detailed breakdown of predictions

Given the business context, both precision and recall are important:
- **Precision**: Important for identifying truly satisfied customers
- **Recall**: Important for not missing satisfied customers who could be targeted for loyalty programs

## Business Applications

### Customer Retention

- Identify satisfied customers for loyalty program enrollment
- Understand factors that drive satisfaction in loyal vs. disloyal customers
- Predict which customers are at risk of becoming dissatisfied

### Service Improvement

- Identify service areas with lowest satisfaction ratings
- Prioritize improvements based on impact on overall satisfaction
- Understand class-specific service expectations

### Operational Excellence

- Analyze impact of delays on satisfaction
- Identify operational factors that most affect passenger experience
- Optimize service delivery based on passenger segments

## Feature Engineering Opportunities

1. **Service Aggregates**:
   - Average service rating (excluding "Not Applicable")
   - Number of services rated 4 or 5 (high satisfaction count)
   - Number of services rated 1 or 2 (low satisfaction count)
   - Service rating variance

2. **Delay Features**:
   - Total delay impact
   - Delay severity categories
   - Delay ratio (arrival delay / departure delay)

3. **Customer Segments**:
   - Loyalty × Travel Type combinations
   - Class × Travel Type interactions
   - Age groups

4. **Composite Scores**:
   - Overall service quality index
   - Operational performance score
   - Customer experience score

## Files

- `airline_satisfaction.csv`: Dataset in CSV format with all features and target variable

## Additional Notes

- The dataset has been cleaned for classification purposes
- All service ratings use a consistent 0-5 scale
- The dataset represents real-world airline passenger survey data
- Large dataset size (103K+ instances) allows for robust model training
- Multiple service dimensions provide rich feature space for analysis

## Research Questions

This dataset can help answer:
- What service aspects are most correlated with overall satisfaction?
- How do flight delays impact passenger satisfaction?
- Do business travelers have different satisfaction drivers than personal travelers?
- How does travel class affect satisfaction expectations and ratings?
- What distinguishes loyal customers who are satisfied vs. dissatisfied?
- Can we predict satisfaction based on service ratings and operational factors?

## Citation

If you use this dataset, please acknowledge:
- Original dataset by John D
- Modified and cleaned for classification purposes

