Telco Customer Churn Dashboard

An interactive Power BI dashboard analyzing customer churn drivers using the public Telco Customer Churn dataset (7,043 records).

Key Finding

Contract type is the single strongest predictor of churn in this dataset:

Contract Type	Churn Rate
Month-to-month	42.7%
One year	11.3%
Two year	2.8%

Overall churn rate: 26.5%

Customers on flexible, no-commitment contracts churn at roughly 15x the rate of customers on two-year contracts — a clear signal that contract structure (not just service quality) drives retention.

Dashboard

Churn Rate card — headline KPI, dynamically updates with slicer selection
Churn Rate by Contract — clustered column chart showing the contract-type breakdown above
Payment Method slicer — filters both visuals by payment method (Electronic check customers churn at 45.3%, more than double any other method)
Tools & Approach
Power BI Desktop for data modeling and visualization
DAX measures for churn rate calculations:
  Churn Rate = 
  DIVIDE(
      CALCULATE(COUNTROWS(Telco), Telco[Churn] = "Yes"),
      COUNTROWS(Telco)
  )
Interactive slicers for cross-filtering by payment method and contract type
Dataset

Source: IBM Sample Data Sets / Kaggle — 7,043 customer records, 21 fields covering demographics, account information, and services signed up for.

Files
churn-dashboard.pbix — Power BI project file
WA_Fn-UseC_-Telco-Customer-Churn.csv — source dataset
