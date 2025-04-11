# OIBSIP-Airbnb Dataset Cleaning and Outlier Detection Project
## Table Of Content
- [Description](#description)
- [Data Overview](#data-overview)
- [Project Objective](#project-objective)
- [Data Source and cleaning](#data-source-and-cleaning)
- [Tools Used](#tools-used)
- [Step-by-Step Data Cleaning Process](#step-by-step-data-cleaning-process)
- [Cleaned Dataset Output](#cleaned-dataset-output)
- [Conclusion](#conclusion)

### Description
---
This project involves cleaning and preparing an Airbnb dataset for analysis by handling missing values, removing duplicates, standardizing formats, and detecting outliers in key numerical fields such as price, minimum_nights and reviews_per_month. The goal is to ensure data accuracy, consistency, and readiness for deeper analysis or machine learning tasks. Excel was used for transformation and visual outlier detection using statistical formulas and Box & Whisker charts.

### Data Overview
---
This project focuses on cleaning and preparing an Airbnb dataset for accurate analysis and modeling. The process includes handling missing data, removing duplicates, standardizing data formats, and detecting outliers using statistical methods. This documentation outlines all steps taken and serves as a reference for reviewing the dataset cleaning phase.

#### Project Objective
1.	Ensure data integrity and consistency.
2.	Handle missing or incomplete data.
3.	Eliminate duplicate records.
4.	Standardize formatting across key fields.
5.	Detect and flag potential outliers for critical numerical variables.

#### Data Source and cleaning
The dataset used is titled Airbnb_dataset.csv, which contains 48,895 entries across 16 columns representing Airbnb listings.
- Data Source: - <a href="https://www.kaggle.com/datasets/dgomonov/new-york-city-airbnb-open-data">Data source</a>
- Dataset used: - <a href="https://github.com/Conyegwara/OIBSIP-/blob/main/Airbnb_dataset.xlsx">Dataset</a>

#### Tools Used

- Microsoft Excel
- Visual tools: Excel Box & Whisker Chart

#### Step-by-Step Data Cleaning Process
- **Step 1: Data Integrity Check**
   - Inspection: Headers were reviewed for clarity and consistency.
   - Filtering Enabled: Excel filters were applied to each column to review values individually.
   - Freezing Panes: The top row was frozen for easy navigation.
   - Data validation: created a dropdown list for columns like host name, neighborhood group, neighborhood and room type(Data tab - click Data Validation - Under Allow, 
     choose List- In the Source box choose a range in the cell.
   - Used conditional formatting to highlight inconsistencies: Select your data range → Home → Conditional Formatting → highlight duplicates, blank cells, etc.

- **Step 2: Handling Missing Data**
  - Name and host_name:	Fill with previous entry: $=IF(A2="", A1, A2)$ — then drag down.
  - last_review	Filled with a placeholder date (1900-01-01)
  - reviews_per_month	Filled with 0

- **Step 3: Duplicate Removal**
  - Duplicates feature was used across key identifying fields.(Entire dataset was selected - Data - remove duplicate)
  - Duplicate rows were eliminated to maintain data uniqueness.

- **Step 4: Standardization**
  - Price Formatting: Removed $ and ,, converted to float.
  - Text Fields: Trimmed whitespace and standardized case.($=TRIM(A2)$ ($=PROPER(A2)$
  - Date Fields: Ensured consistent formatting using Excel date format tools.
  - Dataset colum and row: (selected entire dataset - Home - Format- Autofit row height and Autofit column width)

- **Step 5: Outlier Detection**
  - Method: Mean and Standard Deviation
    Used the formula: $=IF(ABS(A2 - AVERAGE(A:A)) > 2 * STDEV.P(A:A), "Outlier", "OK")$
  - Columns Processed:
     - minimum_nights
     - reviews_per_month
     - Price
  - Steps for Each Column:
    - Calculate the mean and standard deviation using: =AVERAGE(range) and =STDEV.P(range).
    - Used a helper column to flag outliers.
    - Applied conditional formatting for visual distinction
  - Alternative Method (Visual): Box & Whisker Plot
    - Used Excel’s built-in Box & Whisker Chart for price, minimum_nights and reviews_per_month to visualize outliers.
    - Outliers appeared as individual points outside the whiskers.

 <img width="247" alt="Min_night_outlier" src="https://github.com/user-attachments/assets/51416f5d-482d-42e6-a70b-f32342cd2e95" />

 
##### Cleaned Dataset Output
- Exported As Airbnb_Cleaned_Dataset xlsx
- Added columns:
  - Price_Outlier
  - Min_nights_outlier
  - Reviews_Outlier
 
<img width="171" alt="price outlier" src="https://github.com/user-attachments/assets/2daa245b-eeca-4849-a15a-d793bc290302" />


### Conclusion
This project ensured that the Airbnb dataset is clean, consistent, and ready for further analysis or modeling. Outliers were systematically detected and flagged for review, and the data structure now adheres to analysis-ready standards.

📚
🎯
💻


