☕ Cafe Sales Data Cleaning & Analysis

📌 Project Overview
This project focuses on the end-to-end data preparation and cleaning of a messy, real-world cafe sales dataset. The primary objective was to transform raw, inconsistent transaction records into a clean, structured format suitable for business intelligence reporting and exploratory data analysis (EDA).

By addressing missing values, data entry errors, and formatting inconsistencies, this project ensures high data integrity for downstream financial and operational analysis.

📊 Dataset Details
Source: Practice dataset sourced from the internet.
Size: ~10,000 rows, 8 columns.
Domain: Retail & Food Service.
Features Include: Transaction ID, Item, Quantity, Price Per Unit, Total Spent, Payment Method, Location, and Transaction Date.

🧹 Data Cleaning & Preprocessing Pipeline
The raw dataset contained significant data quality issues, including ~30% missing or corrupt data in key categorical columns. The following strategies were implemented to standardize the dataset:

Handling Missing Categorical Data (Payment Method & Location):
Identified missing values (MCAR - Missing Completely At Random) and "ERROR" string inputs.
Strategy: Created an "Unknown" category placeholder instead of using mode imputation. This preserved the underlying 50/50 and 33/33/33 distributions of the valid data and prevented the introduction of analytical bias into future marketing or financial models.
Standardizing Time-Series Data (Transaction Date):
Identified ~4.6% of rows containing blanks or unparseable "ERROR" strings instead of valid dates.
Strategy: Applied row-deletion for records lacking a date to preserve the integrity of time-series analysis (e.g., day-of-week trends), as the data was unordered and sequential imputation was impossible.
Converted raw serial numbers into standard YYYY-MM-DD Short Date formats.

Data Validation: * Locked in dynamic formulas using hard-coded values to ensure dataset stability.
Verified mathematical consistency between Quantity, Price Per Unit, and Total Spent.

🛠️ Tools & Technologies
Microsoft Excel: Data manipulation, logical functions (IF, OR, ISBLANK), date formatting, and data validation.
Pivot Tables: Used for post-cleaning aggregation and summary statistics.

📈 Key Insights (Post-Cleaning)
Following the data cleaning process, initial exploratory analysis via Pivot Tables revealed:
Total Revenue: Successfully verified overall sales tracking at $89,165.
Top Performing Items (by Quantity): Cake (4,204 units) and Smoothie (4,029 units) drive the highest volume.
Sales Distribution: Revenue is balanced exceptionally well across all valid payment methods (Cash, Credit Card, Digital Wallet) and purchase locations (In-store vs. Takeaway).
