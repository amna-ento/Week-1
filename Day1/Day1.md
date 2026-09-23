# Daily Progress Report

## Topics Learned
- Dataset exploration
- Feature understanding
- Data quality inspection
- Missing value detection
- Data type validation
- Duplicate data detection
- Categorical data consistency checks

## Tasks Completed
- Explored the Telco Customer Churn dataset.
- Analyzed dataset features and summary statistics.
- Identified the target variable and understood feature categories.
- Checked for missing values.
- Validated data types of all columns.
- Inspected categorical columns for inconsistent values.
- Checked for duplicate records.
- Performed a complete pre-cleaning data quality assessment.

## Key Findings
- The dataset is largely clean with no duplicate records.
- Categorical columns contain consistent values with no formatting inconsistencies.
- Most columns have the correct data types.
- Identified 11 blank string values in the TotalCharges column.
- These blank strings caused totalCharges to be stored as an object datatype instead of a numeric datatype.

## Problems Faced
- `isnull()` did not detect the missing values because they were stored as lank strings instead of NaN.
- Since the values were not actual NaN, the dataset initially appeared to have no missing values.
- This also made it difficult to understand why TotalCharges had an object datatype.

## Solution 
Possible approaches to handle the issue include:


- Convert the blank strings to NaN and keep the rows if new customers are important for the analysis.
- Convert the blank strings  to NaN and drop the 11 affected rows.
- Replace the blank values with 0 only if the business rule defines that new customers should have zero total charges 
- Calculate totalCharges = tenure × MonthlyCharges where appropriate
