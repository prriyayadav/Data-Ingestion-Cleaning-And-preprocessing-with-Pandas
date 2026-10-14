# Customer Data Cleaning & Preprocessing (Pandas)

Cleaning and preprocessing of a real-world customer dataset
(51,000 rows, 23 columns) using Python and Pandas.

## Files
- Data_Cleaning_Preprocessing.ipynb - full notebook with before/after cleaning
- Customer_Segmentation.csv - raw dataset
- clean_dataset.csv - cleaned dataset (51,000 rows, 30 columns)

## What was done
- Loaded and audited the raw data (missing values, duplicates, invalid values, data types)
- Filled 34 missing country_code values (Namibia = "NA")
- Set 1 invalid phone number to missing
- Removed extra and stray spaces in 85 text cells and lowercased emails
- Checked duplicates (none found) and outliers (valid coordinates; large
  street numbers kept as real identifiers)
- Converted data types (street_number to text, low-cardinality columns to category)
- Engineered 7 features: full_name, email_domain, email_tld, is_free_email,
  area_code, has_valid_phone, tz_region
- Exported the cleaned dataset and compared before vs after

## Before vs After
| Check | Before | After |
|---|---|---|
| Missing values | 34 | 1 |
| Invalid phone numbers | 1 | 0 |
| Cells with extra spaces | 85 | 0 |
| Columns | 23 | 30 |

## Note
When reloading clean_dataset.csv, use
pd.read_csv("clean_dataset.csv", keep_default_na=False, na_values=[""])
because Namibia's country code "NA" is otherwise read as missing.

## Tools
Python, Pandas, NumPy, Matplotlib, Jupyter Notebook