# Telecom Customer Churn Analysis - Power BI Dashboards

This repository contains interactive Power BI dashboards for analyzing customer churn, revenue insights, and service utilization in a telecom company. The analysis uses the Telecom Customer Churn dataset, which includes various customer attributes like tenure, monthly charges, service types, and churn status.

## Dashboards Overview

### 1. **Churn Analysis Dashboard**
   - **Key Metrics:**
     - Total customers
     - Number of churned customers
     - Churn rate (calculated measure)
   - **Churn by Gender (Bar Chart):**
     - A clustered bar chart showing churn rate by demographic fields like Gender, SeniorCitizen, and Partner.
     - The chart is filtered to show only churned customers.
   
### 2. **Revenue Insights Dashboard**
   - **Monthly Charges vs. Tenure (Line Chart):**
     - A line chart showing the relationship between customer tenure and their average monthly charges.
   - **Revenue by Internet Service (Pie Chart):**
     - A pie chart displaying the distribution of revenue based on Internet service types (e.g., Fiber optic, DSL).

### 3. **Service Utilization Dashboard**
   - **Services (Stacked Bar Chart):**
     - A stacked bar chart showing the distribution of customers using PhoneService.
   - **Service Distribution (Treemap):**
     - A treemap visualizing the distribution of customers using StreamingTV service.

## Dataset

The dataset used in these dashboards is the **Telecom Customer Churn Dataset**, which contains the following columns:

- **Churn**: Indicates whether the customer churned (Yes/No).
- **Tenure**: Number of months the customer has been with the company.
- **MonthlyCharges**: Monthly charges for the customer.
- **TotalCharges**: Total charges over the duration of the contract.
- **InternetService**: Type of internet service (e.g., Fiber optic, DSL).
- **Gender**: Gender of the customer (Male/Female).
- **SeniorCitizen**: Whether the customer is a senior citizen (Yes/No).
- **Contract**: Type of contract (Month-to-month, One year, Two year).

## Steps to Reproduce the Dashboards

### Step 1: Load Data into Power BI
1. Open Power BI Desktop.
2. Click on **Home** → **Get Data** → Select **Excel**, **CSV**, or the relevant format for your dataset.
3. Browse and load your dataset into Power BI.
4. Ensure that columns like `MonthlyCharges` and `TotalCharges` are recognized as numeric values and `Churn` as a text field.
5. Clean the data if necessary in **Power Query Editor**:
   - Replace missing values or remove rows with nulls.
   - Create new calculated columns, such as `Churn = "Yes"` or `Churn = "No"`.

### Step 2: Data Modeling
1. Create relationships between tables if using multiple tables.
2. Define measures for aggregation:
   - **Churn Rate**: 
     ```DAX
     Churn Rate = DIVIDE(CALCULATE(COUNTROWS(CustomerData), CustomerData[Churn] = "Yes"), COUNTROWS(CustomerData))
     ```
   - **Total Revenue**: 
     ```DAX
     Total Revenue = SUM(CustomerData[MonthlyCharges])
     ```

### Step 3: Build the Dashboards
1. **Dashboard 1: Churn Analysis**
   - Add Key Metrics cards for:
     - Total customers
     - Number of churned customers
     - Churn rate (using the **Churn Rate** measure).
   - Create a clustered bar chart for churn by demographics (e.g., Gender, SeniorCitizen).
   - Filter the bar chart to show only churned customers.

2. **Dashboard 2: Revenue Insights**
   - Add a line chart to display **MonthlyCharges vs. Tenure**.
   - Add a pie chart to display **Revenue by Internet Service** type.

3. **Dashboard 3: Service Utilization**
   - Add a stacked bar chart for service usage (e.g., **PhoneService**, **MultipleLines**, **OnlineSecurity**).
   - Create a treemap to show the **Service Distribution** for **StreamingTV** and **StreamingMovies**.

### Step 4: Add Filters
1. Use **Slicers** for:
   - **Gender**
   - **SeniorCitizen**
   - **Contract**
   - **Churn**

2. Apply these slicers to make the dashboards interactive and filter the data accordingly.

## Files Included

- **Power BI Files**:
  - `Telecom_Customer_Churn.pbix`: The Power BI report file containing all dashboards and visualizations.
  
- **Dataset**:
  - `Telecom_customer_churn.csv`: The dataset used for the analysis (or specify the file type and location).

## How to Use

1. Download the `.pbix` file from this repository.
2. Open it in **Power BI Desktop**.
3. Review the dashboards and interact with the slicers to explore the insights.


