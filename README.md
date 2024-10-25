# Weather Impact on NYC Transportation Analysis

## Overview
This project analyzes how weather conditions affect transportation patterns in New York City across different modes of public transit. Using big data analytics techniques with Apache Spark, we process and analyze large-scale transportation and weather datasets to understand correlations between weather conditions and ridership patterns. This respository will only contain the part of MTA bus and subway data.

## Repository Structure
```
├── notebooks/
│   ├── Bus_subway_Data_Ingestion.ipynb        # Data preprocessing and cleaning notebook
│   └── Weather_metro_bus_analysis.ipynb             # Main analysis and visualization notebook
├── README.md
└── requirements.txt
```

## Data Sources
The analysis combines several large-scale datasets:
- MTA Subway Hourly Ridership (8.59GB)
- MTA Bus Hourly Ridership (1.83GB)
- Citi Bike System Data - NYC (2.48GB)
- TLC Trip Record Data (12.48GB)
- Local Climatological Data from JFK Airport (12.2MB)

## Key Findings
1. Public transportation usage peaks during haze and thunder conditions
2. Taxi ridership remains relatively stable across different weather conditions
3. Temperature correlation with ridership:
   - Bus: R² = 0.0187, correlation = 0.1520
   - Subway: R² = 0.0103, correlation = 0.1231
   - Citi Bike: R² = 0.2695, correlation = 0.4795
   - Taxi: R² = 0.0069, correlation = 0.0832

4. Precipitation shows minimal correlation with ridership across all transportation modes

## Technical Implementation
- **Platform**: Google Dataproc
- **Framework**: Apache Spark
- **Language**: Scala
- **Key Libraries**:
  - `org.apache.spark.ml` for machine learning
  - `org.apache.spark.sql` for data processing
  - Various Spark SQL functions for analysis

## Data Processing Pipeline
1. Data Cleaning:
   - Timestamp standardization
   - Duplicate removal
   - Missing value handling
   - Schema harmonization
2. Feature Engineering:
   - Weather condition categorization
   - Temporal aggregations
   - Ridership calculations
3. Analysis:
   - Statistical correlation analysis
   - Linear regression modeling
   - Distribution analysis by weather condition

## Challenges Addressed
1. Data Source Integration:
   - Handling different schemas
   - Temporal alignment
   - Scale considerations
2. Data Quality:
   - Missing value imputation
   - Outlier detection
   - Schema inconsistencies

## Usage
The analysis is split into two main notebooks:
1. `data_cleaning.ipynb`: Handles data preprocessing and cleaning
   - Loads raw data
   - Standardizes formats
   - Handles missing values
   - Exports cleaned datasets

2. `analysis.ipynb`: Contains the main analysis
   - Performs statistical analysis
   - Generates visualizations
   - Builds regression models
   - Produces final results

## Results Visualization
The project includes various visualizations showing:
- Transportation mode distribution under different weather conditions
- Correlation between weather metrics and ridership
- Temporal patterns in transportation usage

## Future Improvements
1. Enhanced weather feature engineering
2. More sophisticated modeling approaches
3. Real-time data integration
4. Seasonal pattern analysis

## Acknowledgements
- MTA for providing transportation data
- National Centers for Environmental Information for weather data
- NYC Taxi & Limousine Commission
- Citi Bike System
- Google Dataproc platform

## References
1. [Citi Bike System Data](https://citibikenyc.com/system-data)
2. [NOAA LCD Data Tools](https://www.ncei.noaa.gov/cdo-web/datatools/lcd)
3. [MTA Bus Data](https://data.ny.gov/Transportation/MTA-Bus-Hourly-Ridership-Beginning-February-2022/kv7t-n8in/about_data)
4. [MTA Subway Data](https://data.ny.gov/Transportation/MTA-Subway-Hourly-Ridership-Beginning-February-202/wujg-7c2s/about_data)
5. [TLC Trip Record Data](https://www.nyc.gov/site/tlc/about/tlc-trip-record-data.page)