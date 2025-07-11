# Electric Vehicles Specification Analysis – 2025

##  Project Overview

This project is part of the Advanced Big Data and Data Mining course (Bi-term 2). It aims to provide hands-on experience with real-world data mining workflows, starting with data collection, cleaning, and exploratory data analysis (EDA). The dataset chosen for Deliverable 1 contains detailed specifications for electric vehicles released in 2025.

##  Dataset Summary

**Dataset Name:** `electric_vehicles_spec_2025.csv`  
**Number of Records:** 500+  
**Number of Attributes:** 30+

This dataset provides a comprehensive view of electric vehicle (EV) specifications from various manufacturers. Key attributes include:

- `brand`, `model`: Manufacturer and model of the vehicle
- `battery_capacity`: Battery size in kWh
- `acceleration`: Time taken (in seconds) for 0–100 km/h
- `charging_speed`, `charging_port_type`: Charging capabilities and port type (e.g., CCS)
- `range`: Estimated range (in km) per charge
- `drivetrain`, `body_style`: Performance and design characteristics
- `segment`, `vehicle_weight`, `top_speed`, and more

The data supports rich analysis opportunities, including predictive modeling (e.g., predicting range or acceleration), clustering (e.g., market segments), and classification (e.g., drivetrain prediction).

##  Justification for Dataset Selection

This dataset was selected because it meets the following criteria:

- Contains over 500 rows and more than 8 relevant attributes
- Includes both categorical and numerical data
- Represents a trending real-world domain (EV technology)
- Supports various data mining tasks (regression, classification, clustering)
- Offers valuable industry insights for sustainable transportation analytics

##  Data Cleaning Summary

The dataset required several cleaning operations to prepare it for analysis:

###  Missing Values Handling
- Checked for missing values using `df.isnull().sum()`
- For numerical features (e.g., acceleration): Used median or mean imputation
- For categorical features (e.g., drivetrain): Used mode or removed rows if sparsely populated

###  Duplicate Removal
- Identified and removed duplicate rows using `df.drop_duplicates()`

###  Data Type Conversion
- Converted relevant string columns to numeric (e.g., acceleration, range)
- Cleaned suffixes from values where present (e.g., "s" in acceleration time)

###  Inconsistencies Fixed
- Standardized text formatting across columns (e.g., body style, segment)
- Replaced inconsistent values such as charging port names and units

##  Exploratory Data Analysis (EDA)

The EDA process was conducted using Pandas, Seaborn, and Matplotlib. Key steps and findings are summarized below.

###  Distribution of Battery Capacity
- Most EVs fall within the 50–100 kWh range
- Premium models exceed 100 kWh

###  Battery Capacity vs Range
- Positive linear relationship observed between battery size and driving range
- Indicates range can be reliably predicted from battery capacity and drivetrain type

###  Acceleration Analysis
- High-performance EVs (e.g., Audi e-tron GT) have acceleration under 4 seconds
- SUVs and crossovers show slower acceleration due to weight

###  Drivetrain and Charging Port Distribution
- AWD and FWD are most common drivetrain types
- CCS is the most widely adopted fast charging standard

###  Correlation Matrix
- Strong correlation between battery capacity, motor power, range, and weight
- Weak correlation between body style and performance metrics

##  Key Insights

- **Battery Capacity** and **Motor Power** are top predictors of **Range**
- **Acceleration** is often lower (faster) in vehicles with higher power output
- Most EVs are **SUVs or hatchbacks**, indicating consumer preference
- Standardization around **CCS charging ports** shows industry convergence

These insights will shape future modeling tasks in Deliverable 2 (e.g., regression to predict range or classification of drivetrain).

##  Challenges Encountered

| Challenge | Resolution |
|----------|------------|
| Missing or inconsistent values | Used imputation, row removal, and formatting |
| Mixed data types (e.g., numeric stored as strings) | Cleaned using `pd.to_numeric()` |
| Outliers in acceleration and charging time | Detected and optionally removed for analysis |
| Lack of data dictionary | Used column exploration and sample URLs to infer meaning |
