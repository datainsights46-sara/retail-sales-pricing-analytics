Retail Sales & Competitor Pricing Analytics Project (Google Sheets)
(Data Cleaning • Product Hierarchy Mapping • Pricing Analysis • Franchise Metrics • Dashboard)
This project showcases my ability to clean raw retail sales data, structure product categories, create automated calculations using ARRAYFORMULA, analyze pricing vs competitors, and build a complete dashboard used for commercial decision-making.

1. Data Cleaning & Preparation
I started by creating a working copy of the raw dataset and naming it Cleaned_Data.
 The goal here was to make the dataset analysis-ready without losing any original information.
Key steps included:
Freezing header rows for easier navigation.


Using filters to identify blanks and fill missing values:


Categorical → “Unknown”


Numeric → Median values


Date → Placeholder: 2024-01-01


Removing duplicate rows using Google Sheets’ cleanup tool.


Correcting number, currency, and date formats.


Manually checking for outliers by sorting numeric columns.
Raw data:

Cleaned data: 






2. Standardizing Product Hierarchy
To bring structure to the product catalog, I created a new sheet called Product_Hierarchy.
What I did:
Copied Category & Product columns


Removed duplicates to get unique items


Added two new classification columns:


WEBU_Category


WEBU_Subcategory


Then I manually mapped each product into a clean hierarchy so later analysis would group correctly.

Smart Step: Creating a Unique Key
To avoid lookup errors (e.g., same product name appearing in multiple categories), I created a Key:
=ARRAYFORMULA(B2:B & "|" & C2:C)

This Key was used for VLOOKUP to map WEBU_Category & Subcategory back to Cleaned_Data.









3. Pricing & Competitor Analysis Columns
I added several analytical columns that update automatically using ARRAYFORMULA:
• Margin
=ARRAYFORMULA(IF(F2:F="", "", F2:F - E2:E))

• Margin %
=ARRAYFORMULA(IF(F2:F="", "", (F2:F - E2:E) / F2:F))

• Competitor Gap
=ARRAYFORMULA(IF(F2:F="", "", F2:F - G2:G))

• Price Band (Low/Medium/High)
=ARRAYFORMULA(IF(F2:F="", "", IFS(
  F2:F < 3, "Low",
  F2:F < 6, "Medium",
  TRUE, "High"
)))

These allow quick comparisons between our prices and competitor prices, and help segment products.








4. Pivot Tables for Insights
To turn the cleaned data into business insights, I built several pivot tables:
1 Competitor Gap by Category
Shows whether we are priced above or below competitors.


2 Margin % by Product
Helps identify high-profit vs low-profit items.
3 Units Sold by Region
Gives a regional performance snapshot for commercial teams.
4 Monthly Sales Trend
Created by generating a Month column:
=ARRAYFORMULA(IF(I2:I="", "", TEXT(I2:I, "MMM-YY")))

Then used in a pivot table to track monthly sales movement.

5. Franchisee Metrics Simulation
To simulate a real business environment, I created a Franchisee_Metrics sheet.
KPIs included:
Total Revenue


Month-over-Month Growth


Average Margin %


Average Competitor Gap


% of Items Cheaper Than Competitors


Example formula for "% items cheaper":
=COUNTIF(Cleaned_Data!O2:O, "<0") / COUNTA(Cleaned_Data!A2:A)



6. Dashboard Creation
Finally, I created a full dashboard bringing all the insights together.
 This included four charts:

1  Price vs Competitor (Clustered Column Chart)
Visual comparison of our price vs competitor price for each product.
2 Sales by Region (Bar Chart)
Quick view of performance across regions.
3 Product Mix (Pie Chart)
Shows distribution across WEBU categories.
4 Units Sold Over Time (Line Chart)
Shows trends and seasonality.

7. Tools & Skills Used
Google Sheets (Advanced)


ARRAYFORMULA / VLOOKUP / IFS / COUNTIF


Pivot Tables


Dashboard Creation


Data Cleaning


Data Structuring & Hierarchy Mapping


Pricing & Competitor Analysis


Sales Trend Analysis



8. Summary
This project demonstrates end-to-end handling of a retail dataset — from raw, messy files to a structured, automated, and insight-rich dashboard.

