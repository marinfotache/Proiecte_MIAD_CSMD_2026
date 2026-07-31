# Air Quality and Pollution Assessment Dataset

## Overview

This dataset focuses on air quality assessment across various regions. The dataset contains **5,000 samples** and captures critical environmental and demographic factors that influence pollution levels.

## Source

This dataset is derived from several real-world sources that monitor air quality and environmental factors:

- **World Health Organization (WHO)**: [Air Pollution](https://www.who.int/health-topics/air-pollution)
- **World Bank Data**: [Population Density Indicator](https://data.worldbank.org/indicator/EN.POP.DNST)
- **Kaggle Dataset**: [Air Quality and Pollution Assessment](https://www.kaggle.com/datasets/mujtabamatin/air-quality-and-pollution-assessment)

## Dataset Information

- **Total Samples**: 5,000
- **Features**: 9 environmental and demographic variables
- **Target Variable**: Air Quality Levels (4 categories)
- **Data Format**: CSV (converted from ARFF format)

## Target Variable: Air Quality Levels

The dataset classifies air quality into four categories:

- **Good**: Clean air with low pollution levels
- **Moderate**: Acceptable air quality but with some pollutants present
- **Poor**: Noticeable pollution that may cause health issues for sensitive groups
- **Hazardous**: Highly polluted air posing serious health risks to the population

### Class Distribution

- **Good**: 2,000 samples (40%)
- **Moderate**: 1,500 samples (30%)
- **Poor**: 1,000 samples (20%)
- **Hazardous**: 500 samples (10%)

## Variable Descriptions

### Environmental Variables

1. **Temperature** (REAL, in Celsius)
   - Average temperature of the region
   - Continuous variable

2. **Humidity** (REAL, percentage)
   - Relative humidity recorded in the region
   - Continuous variable (0-100%)

3. **PM2.5** (REAL, μg/m³)
   - Fine particulate matter levels
   - Particles with diameter less than 2.5 micrometers
   - Continuous variable

4. **PM10** (REAL, μg/m³)
   - Coarse particulate matter levels
   - Particles with diameter less than 10 micrometers
   - Continuous variable

5. **NO2** (REAL, ppb - parts per billion)
   - Nitrogen dioxide levels
   - A toxic gas produced by combustion processes
   - Continuous variable

6. **SO2** (REAL, ppb - parts per billion)
   - Sulfur dioxide levels
   - A gas produced by burning fossil fuels containing sulfur
   - Continuous variable

7. **CO** (REAL, ppm - parts per million)
   - Carbon monoxide levels
   - A colorless, odorless gas produced by incomplete combustion
   - Continuous variable

8. **Proximity_to_Industrial_Areas** (REAL, km)
   - Distance to the nearest industrial zone
   - Continuous variable
   - Lower values indicate closer proximity to industrial areas

### Demographic Variable

9. **Population_Density** (INTEGER, people/km²)
   - Number of people per square kilometer in the region
   - Integer variable
   - Higher values indicate more densely populated areas

### Target Variable

10. **Air_Quality** (STRING)
    - Categorical target variable
    - Values: `Good`, `Moderate`, `Poor`, `Hazardous`

## Data Characteristics

### Air Quality Standards Context

Understanding typical air quality thresholds can help interpret the data:

- **PM2.5**: WHO guideline is 15 μg/m³ annual mean, 35 μg/m³ 24-hour mean
- **PM10**: WHO guideline is 45 μg/m³ annual mean, 70 μg/m³ 24-hour mean
- **NO2**: WHO guideline is 10 μg/m³ annual mean (approximately 5.2 ppb)
- **SO2**: WHO guideline is 40 μg/m³ 24-hour mean (approximately 15.4 ppb)
- **CO**: WHO guideline is 10 mg/m³ 8-hour mean (approximately 8.7 ppm)

### Key Relationships

The dataset captures relationships between:
- **Environmental factors**: Temperature, humidity, and various pollutant concentrations
- **Geographic factors**: Proximity to industrial areas
- **Demographic factors**: Population density
- **Outcome**: Overall air quality classification

## Usage

This dataset is suitable for:

- **Classification tasks**: Predicting air quality levels based on environmental and demographic factors
- **Regression tasks**: Predicting specific pollutant concentrations
- **Exploratory data analysis**: Understanding relationships between environmental factors and air quality
- **Feature importance analysis**: Identifying which factors most strongly influence air quality
- **Environmental research**: Studying the impact of industrial proximity and population density on air quality
- **Educational purposes**: Teaching machine learning and data analysis concepts

## Files

- `air-quality.csv`: Dataset in CSV format with proper column headers
- `air-quality.arff`: Original dataset in ARFF (Attribute-Relation File Format)

## Data Preprocessing Notes

- The dataset has been converted from ARFF format to CSV for easier use
- All numeric columns have been properly typed (REAL/INTEGER as specified)
- The target variable (Air_Quality) is stored as a string/categorical variable
- No missing values are present in the dataset (based on the original ARFF structure)

## Potential Applications

1. **Air Quality Prediction Models**: Build classifiers to predict air quality categories
2. **Pollution Source Analysis**: Analyze the relationship between industrial proximity and pollution levels
3. **Urban Planning**: Use population density and environmental factors to inform urban development
4. **Public Health Research**: Study correlations between air quality and demographic factors
5. **Environmental Monitoring**: Develop models to assess air quality based on measurable environmental parameters

## Citation

If you use this dataset, please cite the original sources:
- World Health Organization (WHO) - Air Pollution data
- World Bank - Population Density data
- Kaggle Dataset: [Air Quality and Pollution Assessment](https://www.kaggle.com/datasets/mujtabamatin/air-quality-and-pollution-assessment)

## Additional Resources

- [WHO Air Pollution Guidelines](https://www.who.int/health-topics/air-pollution)
- [World Bank Population Density Data](https://data.worldbank.org/indicator/EN.POP.DNST)
- [EPA Air Quality Index Guide](https://www.airnow.gov/aqi/aqi-basics/)

