# Data Cleaning Log

This document records data quality issues identified in the dataset and the corresponding cleaning actions performed.

---

## Column-Level Cleaning Summary

| Column Name         | Meaning                    | Data Type | Example                                               | Issue Found                                              | Cleaning Action                                                                 |
|---------------------|----------------------------|-----------|-------------------------------------------------------|----------------------------------------------------------|----------------------------------------------------------------------------------|
| name                | Listing name               | Text      | Stylish Remodeled House with Deck, Steps to Dining   | Missing values and inconsistent capitalization           | Capitalized values and replaced missing values with `"Not Specified"`            |
| neighbourhood_group | Broad location group       | Text      | Manhattan                                             | Missing values                                           | Filled missing values with `"Not Specified"`                                     |
| neighbourhood       | Area name                  | Text      | Hollywood                                             | Inconsistent naming, contained numeric values            | Converted all entries to text and standardized naming                            |
| city                | City of listing            | Text      | San Diego                                             | Capitalization issues                                    | Standardized capitalization across values                                         |
| room_type           | Type of property           | Category  | Entire Home/Apt                                       | Minor inconsistencies                                    | Standardized categories and added `"Not Specified"` for missing values           |
| price               | Nightly price              | Numeric   | $215                                                  | Stored as text                                           | Removed currency symbols and converted to numeric                                |
| price               | Nightly price              | Numeric   | 1000                                                  | Outliers detected                                        | Removed outliers using IQR method                                                |
| minimum_nights      | Minimum booking nights     | Numeric   | 30                                                    | Extreme outliers                                         | Capped extreme values using IQR method                                           |
| availability_365    | Available days per year    | Numeric   | 300                                                   | Invalid values                                           | Clipped values to valid range (0–365)                                            |
| last_review         | Last review date           | Date      | 12/7/2020                                             | Stored as text                                           | Converted to proper datetime format                                              |
| reviews_per_month   | Average monthly reviews    | Numeric   | 0.44                                                  | Missing values                                           | Filled missing values with `0`                                                   |

---

## Methods Used

- Missing value imputation
- Capitalization standardization
- Data type conversion
- Outlier detection using **Interquartile Range (IQR)**
- Value clipping for valid ranges
- Category standardization

---

## Notes

- `"Not Specified"` was used consistently for missing categorical/text values.
- Numeric conversions were validated post-cleaning.
- Outlier treatment was applied conservatively to avoid excessive data loss.

