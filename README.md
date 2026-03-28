# Assignment: Customer Churn Prediction Dashboard

## Course
Machine Learning / Data Science / Data Visualization

## Objective
The goal of this assignment is to design and implement a **Customer Churn Prediction Dashboard** that visualizes customer behavior and predicts whether a customer is likely to churn using a machine learning model.

Students will:

- Convert an ML script into a conceptual **Backend API**
- Design a **Frontend Dashboard**
- Display **analytics, model performance, and predictions**
- Use **Bootstrap + DC.js / Chart.js** for visualization

---

# 1. Problem Statement

Customer churn occurs when customers stop using a company's services. Predicting churn helps businesses retain customers by identifying risky customers early.

You are given a **machine learning churn prediction script** that uses:

- Python
- Pandas
- Scikit-learn
- Random Forest Classifier

Your task is to design a **web dashboard** that visualizes churn analytics and interacts with the ML model through API endpoints.

---

# 2. Given Machine Learning Workflow

The ML system performs the following steps:

1. Load customer dataset
2. Encode categorical data
3. Normalize features
4. Train Random Forest model
5. Evaluate model performance
6. Predict churn for a new customer

### Input Features

The model uses the following customer attributes:

| Feature | Description |
|------|------|
| Age | Age of the customer |
| Gender | Male / Female |
| Spend | Customer spending amount |
| Tenure | Number of months as customer |
| Visits | Number of service visits |

### Output

The model predicts:

```

Customer is likely to CHURN
or
Customer is likely to STAY

```

---

# 3. Assignment Tasks

Students must design a **Customer Churn Prediction Dashboard** consisting of:

1. Dashboard Layout
2. Data Visualization
3. Model Evaluation Display
4. Customer Prediction Tool

---

# 4. Dashboard Layout Structure

The dashboard should contain the following sections:

```
┌─────────────────────────────────────────────────────────┐ │ NAVIGATION BAR (Bootstrap Navbar) │ │ Dashboard | Analytics | Model Performance | Prediction │ └─────────────────────────────────────────────────────────┘

┌─────────────┬──────────────┬────────────┬──────────────┐ │ Total │ Churned │ Churn Rate │ Model │ │ Customers │ Customers │ (%) │ Accuracy (%) │ │ │ │ │ │ │ (Bootstrap KPI Cards) │ └─────────────┴──────────────┴────────────┴──────────────┘

┌──────────────────────────┬──────────────────────────┐ │ │ │ │ Churn Distribution │ Gender vs Churn │ │ (Pie Chart - DC.js) │ (Stacked Bar - DC.js) │ │ │ │ ├──────────────────────────┼──────────────────────────┤ │ │ │ │ Spend vs Churn │ Tenure vs Churn │ │ (Scatter Plot - D3.js) │ (Bar Chart - DC.js) │ │ │ │ └──────────────────────────┴──────────────────────────┘

┌──────────────────────────────────────────────────────┐ │ MODEL PERFORMANCE SECTION │ │ ┌──────────────────┐ ┌──────────────────────┐ │ │ │ Confusion Matrix │ │ Classification Report │ │ │ │ (Heatmap) │ │ (Grouped Bar Chart) │ │ │ └──────────────────┘ └──────────────────────┘ │ └──────────────────────────────────────────────────────┘

┌──────────────────────────────────────────────────────┐ │ PREDICTION TOOL SECTION │ │ Form with input fields and Predict button │ │ Result display with color coding (Green/Red) │ └──────────────────────────────────────────────────────┘

┌──────────────────────────────────────────────────────┐ │ CUSTOMER DATASET TABLE │ │ DataTables.js with search, sort, pagination, export │ └──────────────────────────────────────────────────────┘

┌──────────────────────────────────────────────────────┐ │ FOOTER │ └──────────────────────────────────────────────────────┘
---

## Header / Navigation Bar

## KPI Summary Cards

## Customer Behavior Analytics

## Model Performance Section

## Customer Churn Prediction Tool

## Customer Dataset Table

## Footer

```

---

# 5. Section 1: Navigation Bar

The top navigation bar should contain:

- Dashboard Title  
- Navigation links  

### Menu Items

- Dashboard
- Customer Analytics
- Model Evaluation
- Prediction Tool

Optional:

- Refresh Data
- Export Report

Use **Bootstrap Navbar**.

---

# 6. Section 2: KPI Summary Cards

Display key metrics using **Bootstrap Cards**.

### Required KPI Cards

| KPI | Description |
|----|----|
| Total Customers | Total number of customers |
| Churn Customers | Number of customers who left |
| Churn Rate | Percentage of churn |
| Model Accuracy | Accuracy of the ML model |

Example layout:

```

| Total Customers | Churn Customers | Churn Rate | Model Accuracy |

```

---

# 7. Section 3: Customer Behavior Analytics

This section visualizes customer patterns related to churn.

Use **DC.js or Chart.js**.

### Required Charts

#### 1. Churn Distribution

Chart Type:

```

Pie Chart

```

Shows:

```

Stayed vs Churned

```

---

### 2. Gender vs Churn

Chart Type:

```

Stacked Bar Chart

```

Shows churn distribution by gender.

---

### 3. Spend vs Churn

Chart Type:

```

Scatter Plot

```

Shows relationship between:

```

Customer Spending
and
Churn Status

```

---

### 4. Tenure vs Churn

Chart Type:

```

Bar Chart

```

Shows how long-term customers behave compared to new customers.

---

# 8. Section 4: Model Performance Dashboard

Display machine learning evaluation results.

### Required Visualizations

#### Confusion Matrix

Display as:

```

Heatmap

```

Example:

```

```
           Predicted
        Stay    Churn
```

Actual Stay    2        0
Actual Churn   0        1

```

---

### Classification Report Visualization

Display metrics:

- Precision
- Recall
- F1 Score

For classes:

```

Stay
Churn

```

Use:

```

Grouped Bar Chart

```

---

# 9. Section 5: Customer Churn Prediction Tool

Create a form that allows users to input customer information.

### Input Fields

| Field | Type |
|------|------|
| Age | Number |
| Gender | Dropdown |
| Monthly Spend | Number |
| Tenure | Number |
| Visits | Number |

Example layout:

```

Customer Churn Prediction

Age: [   ]

Gender: [Male/Female]

Spend: [   ]

Tenure: [   ]

Visits: [   ]

[ Predict Churn ]

```

---

### Prediction Result Display

Display prediction result such as:

```

Customer is likely to CHURN

```

or

```

Customer is likely to STAY

```

Use color indicators:

| Result | Color |
|------|------|
| Churn | Red |
| Stay | Green |

---

# 10. Section 6: Customer Dataset Table

Display dataset records in a table.

### Table Columns

| Column |
|------|
CustomerID |
Age |
Gender |
Spend |
Tenure |
Visits |
Churn |

Features required:

- Search
- Pagination
- Sorting
- Export CSV

Use:

```

DataTables.js

```

---

# 11. Backend API Design (Conceptual)

Assume the ML script is converted into a **Flask API**.

Students must design endpoints that the dashboard can consume.

### API Endpoints

#### System Endpoint

```

GET /api/health

```

Check API status.

---

#### Dataset Summary

```

GET /api/customers/summary

```

Returns:

- total_customers
- churn_customers
- churn_rate
- model_accuracy

---

#### Customer Dataset

```

GET /api/customers

```

Returns all customer records.

---

#### Churn Distribution

```

GET /api/analytics/churn-distribution

```

Returns number of:

- churned customers
- retained customers

---

#### Gender vs Churn

```

GET /api/analytics/gender-churn

```

Returns churn statistics by gender.

---

#### Spend vs Churn

```

GET /api/analytics/spend-churn

```

Returns spending vs churn dataset.

---

#### Tenure vs Churn

```

GET /api/analytics/tenure-churn

```

Returns tenure based churn statistics.

---

#### Model Performance

```

GET /api/model/performance

```

Returns:

- accuracy
- confusion matrix
- precision
- recall
- f1 score

---

#### Confusion Matrix

```

GET /api/model/confusion-matrix

```

Returns matrix values.

---

#### Classification Report

```

GET /api/model/classification-report

```

Returns metrics for churn and stay classes.

---

#### Churn Prediction

```

POST /api/predict-churn

```

Input:

```

age
gender
spend
tenure
visits

```

Output:

```

churn_prediction
probability_churn
probability_stay

```

---

# 12. Suggested Frontend Technologies

Students should use:

| Technology | Purpose |
|------|------|
Bootstrap 5 | Layout and UI |
DC.js / Chart.js | Charts |
D3.js | Data visualization |
DataTables.js | Table display |
JavaScript Fetch API | API calls |

---

# 13. Suggested Folder Structure

```

churn-dashboard
│
├── index.html
├── css
│   └── style.css
│
├── js
│   ├── dashboard.js
│   ├── charts.js
│   ├── prediction.js
│
├── data
│   └── churn_data.json
│
└── assets

```

---

# 14. Expected Outcome

Students should produce:

- A **functional dashboard UI**
- Interactive charts
- Customer prediction form
- Dataset visualization
- Model performance display

---

# 15. Evaluation Criteria

| Criteria | Marks |
|------|------|
Dashboard Layout | 20 |
Data Visualization | 20 |
Prediction Tool | 20 |
API Design | 20 |
Code Quality & UI | 20 |

Total Marks: **100**

---

# 16. Bonus Task (Optional)

Add advanced features:

- Feature Importance Chart
- Churn Risk Score
- Download Analytics Report
- Dark Mode Dashboard

---

# End of Assignment
Customer Churn Prediction Dashboard
```

---
