# Mobile Price Range Prediction Dataset

## Overview

Bob has started his own mobile company and wants to compete with big companies like Apple and Samsung. He does not know how to estimate the price of mobiles his company creates. In this competitive mobile phone market, you cannot simply assume things. To solve this problem, he collects sales data of mobile phones from various companies.

Bob wants to find out some relation between features of a mobile phone (e.g., RAM, Internal Memory, etc.) and its selling price. However, he is not so good at Machine Learning, so he needs help to solve this problem.

**Important**: In this problem, you do not have to predict the actual price but a **price range** indicating how high the price is.

## Dataset Information

- **Total Instances**: 2,000
- **Number of Attributes**: 20 input features + 1 target variable
- **Data Format**: CSV
- **Task**: Multi-class classification (predicting price range category)

## Target Variable

**price_range** (categorical/numeric)
- Price range category indicating how high the price is
- Values: `0`, `1`, `2`, `3`
  - `0`: Low price range
  - `1`: Medium-low price range
  - `2`: Medium-high price range
  - `3`: High price range

### Class Distribution
- **0**: 500 instances (25%)
- **1**: 500 instances (25%)
- **2**: 500 instances (25%)
- **3**: 500 instances (25%)

**Note**: The dataset is perfectly balanced across all four price range categories.

## Variable Descriptions

### Hardware Specifications

1. **battery_power** (numeric)
   - Battery power capacity
   - Measured in mAh (milliampere-hours)
   - Range: 501 to 1,998 mAh
   - Higher battery power typically indicates higher-end devices

2. **clock_speed** (numeric)
   - Processor clock speed
   - Measured in GHz (gigahertz)
   - Higher clock speed indicates faster processing

3. **int_memory** (numeric)
   - Internal memory (storage)
   - Measured in GB (gigabytes)
   - Range: 2 to 64 GB
   - More internal memory typically increases price

4. **ram** (numeric)
   - Random Access Memory
   - Measured in MB (megabytes)
   - Range: 256 to 3,998 MB
   - More RAM typically significantly increases price

5. **n_cores** (numeric)
   - Number of cores in the processor
   - More cores generally indicate better performance and higher price

6. **pc** (numeric)
   - Primary camera megapixels
   - Higher megapixel count typically increases price

7. **fc** (numeric)
   - Front camera megapixels
   - Higher megapixel count typically increases price

### Display Features

8. **px_height** (numeric)
   - Pixel resolution height
   - Higher resolution indicates better display quality

9. **px_width** (numeric)
   - Pixel resolution width
   - Higher resolution indicates better display quality
   - **Note**: Total pixels = px_height × px_width

10. **sc_h** (numeric)
    - Screen height
    - Measured in cm (centimeters)
    - Range: 5 to 19 cm

11. **sc_w** (numeric)
    - Screen width
    - Measured in cm (centimeters)
    - Range: 0 to 18 cm
    - **Note**: Screen size affects price

12. **touch_screen** (binary)
    - Whether the phone has a touch screen
    - Values: `0` (no), `1` (yes)
    - Most modern phones have touch screens

### Connectivity Features

13. **wifi** (binary)
    - Whether the phone has WiFi capability
    - Values: `0` (no), `1` (yes)
    - Standard feature in modern smartphones

14. **blue** (binary)
    - Whether the phone has Bluetooth
    - Values: `0` (no), `1` (yes)
    - Standard feature in modern smartphones

15. **dual_sim** (binary)
    - Whether the phone supports dual SIM cards
    - Values: `0` (no), `1` (yes)
    - Popular feature in many markets

16. **three_g** (binary)
    - Whether the phone supports 3G connectivity
    - Values: `0` (no), `1` (yes)
    - Older standard, but still common

17. **four_g** (binary)
    - Whether the phone supports 4G connectivity
    - Values: `0` (no), `1` (yes)
    - Standard in modern smartphones

### Physical Characteristics

18. **mobile_wt** (numeric)
    - Mobile weight
    - Measured in grams
    - Weight can affect user preference and price positioning

19. **m_dep** (numeric)
    - Mobile depth (thickness)
    - Measured in cm (centimeters)
    - Thinner phones are often premium features

20. **talk_time** (numeric)
    - Longest time that a single battery charge will last when talking
    - Measured in hours
    - Battery efficiency indicator

### Target Variable

21. **price_range** (categorical/numeric)
    - Price range category
    - Values: `0` (low), `1` (medium-low), `2` (medium-high), `3` (high)
    - This is the target variable for prediction

## Data Characteristics

### Feature Types

- **Binary Features** (0/1): blue, dual_sim, four_g, three_g, touch_screen, wifi
- **Continuous Features**: battery_power, clock_speed, fc, int_memory, m_dep, mobile_wt, n_cores, pc, px_height, px_width, ram, sc_h, sc_w, talk_time

### Key Price Drivers

Based on typical mobile phone pricing, important features likely include:
- **RAM**: Often one of the strongest predictors of price
- **Internal Memory**: Significant impact on price
- **Battery Power**: Higher capacity typically increases price
- **Camera Quality**: Both front and primary camera megapixels
- **Display Resolution**: Pixel dimensions affect price
- **Processor**: Clock speed and number of cores

### Balanced Dataset

The dataset is perfectly balanced with equal representation across all four price ranges (500 instances each). This is ideal for:
- Training classification models
- Evaluating model performance
- Avoiding class imbalance issues

## Usage

This dataset is suitable for:

- **Multi-class Classification**: Predicting price range (0, 1, 2, or 3) based on phone features
- **Feature Importance Analysis**: Understanding which features most strongly influence price
- **Price Estimation**: Helping manufacturers estimate appropriate price ranges for new phones
- **Market Analysis**: Understanding the relationship between specifications and pricing
- **Educational Purposes**: Teaching classification algorithms with balanced, real-world data
- **Business Intelligence**: Informing pricing strategies for mobile phone manufacturers

## Important Considerations

1. **Price Range vs. Actual Price**: The target is a price range category, not the actual price. Consider:
   - This is a classification problem, not regression
   - Price ranges may overlap or have different boundaries
   - The ranges are ordinal (0 < 1 < 2 < 3)

2. **Feature Engineering**: Consider creating:
   - **Total pixels**: px_height × px_width (total display resolution)
   - **Screen area**: sc_h × sc_w (screen size)
   - **Pixel density**: Total pixels / Screen area
   - **Camera total**: pc + fc (combined camera megapixels)
   - **Connectivity score**: Sum of connectivity features (wifi + blue + 3g + 4g)
   - **Performance score**: Combination of clock_speed, n_cores, ram

3. **Feature Scaling**: Many features have different scales. Consider:
   - Standardization (z-score normalization)
   - Min-max scaling
   - Some algorithms (tree-based) may not require scaling

4. **Missing Values**: Check for missing values and handle appropriately:
   - The dataset appears to have complete data
   - Verify all features are properly encoded

5. **Feature Relationships**: Consider:
   - Correlations between features (e.g., px_height and px_width)
   - Multicollinearity in linear models
   - Feature interactions (e.g., ram × int_memory)

6. **Business Context**: 
   - Different markets may value features differently
   - Brand perception (not in dataset) also affects price
   - Market positioning strategy matters

7. **Ordinal Nature**: Price range is ordinal (0 < 1 < 2 < 3). Consider:
   - Using ordinal classification methods
   - Treating as regular multi-class classification
   - Using regression and then binning (though this is not the task)

## Evaluation Metrics

For multi-class classification, consider:
- **Accuracy**: Overall classification accuracy
- **Confusion Matrix**: Detailed breakdown by price range
- **Precision, Recall, F1-Score**: Per-class and macro/micro averages
- **Cohen's Kappa**: Agreement between predicted and actual classes
- **Classification Report**: Per-class metrics

Given the balanced dataset, accuracy is a reasonable metric, but per-class metrics are still valuable to ensure good performance across all price ranges.

## Feature Importance Insights

Based on typical mobile phone pricing patterns, likely important features include:

1. **RAM**: Usually one of the strongest predictors
2. **Internal Memory**: Significant impact on price
3. **Battery Power**: Important for mid-to-high range phones
4. **Camera Quality**: Both front and primary cameras matter
5. **Display Resolution**: Higher resolution = higher price
6. **Processor**: Clock speed and cores affect performance tier

## Business Applications

### For Mobile Manufacturers

- **Pricing Strategy**: Estimate appropriate price ranges for new phone models
- **Feature Planning**: Understand which features justify higher prices
- **Market Positioning**: Determine feature sets for different price segments
- **Cost-Benefit Analysis**: Balance feature costs with price expectations

### For Retailers

- **Price Estimation**: Estimate price ranges for phones with known specifications
- **Inventory Management**: Categorize phones by price range
- **Market Analysis**: Understand pricing patterns in the market

## Feature Engineering Opportunities

1. **Display Features**:
   - Total pixels = px_height × px_width
   - Screen area = sc_h × sc_w
   - Pixel density = Total pixels / Screen area
   - Aspect ratio = px_width / px_height

2. **Camera Features**:
   - Total camera megapixels = pc + fc
   - Camera ratio = fc / pc (front to primary)

3. **Performance Features**:
   - Performance score = clock_speed × n_cores
   - Memory ratio = ram / int_memory

4. **Connectivity Score**:
   - Connectivity features count = wifi + blue + three_g + four_g

5. **Physical Features**:
   - Weight-to-size ratio = mobile_wt / (sc_h × sc_w)
   - Thinness score = 1 / m_dep (thinner = higher score)

6. **Battery Efficiency**:
   - Battery per weight = battery_power / mobile_wt
   - Talk time efficiency = talk_time / battery_power

## Files

- `mobile_price.csv`: Dataset in CSV format with all features and target variable

## Additional Notes

- The dataset is perfectly balanced (500 instances per price range)
- All features are numeric (binary features encoded as 0/1)
- The dataset represents sales data from various mobile phone companies
- Suitable for both beginners and advanced machine learning practitioners
- Well-suited for teaching classification algorithms

## Research Questions

This dataset can help answer:
- Which features are most predictive of mobile phone price range?
- How do different combinations of features affect price positioning?
- What is the relative importance of hardware vs. connectivity features?
- How do display specifications compare to performance specs in pricing?
- Can we accurately predict price range using only hardware specifications?

## Citation

If you use this dataset, please credit the author.

**Note**: This dataset is intended for educational and research purposes. The scenario described (Bob's mobile company) is fictional and used for educational illustration.


