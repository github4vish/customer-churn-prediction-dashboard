
---

# 📊 Customer Churn Prediction Dashboard – Simple 6 Steps Guide

---

## ✅ Step 1: Understand File Structure (Diagram + Purpose)

### 📁 Project Structure

```id="c1k9zr"
churn-dashboard/
│
├── index.html
├── css/
│   └── styles.css
├── js/
│   └── dashboard.js
│
├── models/
│       model.pkl
│
├── training/
│       train_model.py
│       notebook.ipynb
│
└── app.py
```

### 📌 Purpose of Each File

| File/Folder        | Purpose                              |
| ------------------ | ------------------------------------ |
| **index.html**     | Main dashboard UI                    |
| **styles.css**     | Styling and layout design            |
| **dashboard.js**   | Handles API calls and UI updates     |
| **models/**        | Stores trained ML model              |
| **train_model.py** | Converts notebook into trained model |
| **notebook.ipynb** | Used for ML training (Random Forest) |
| **app.py**         | Backend API server                   |

---

## ✅ Step 2: Design Dashboard (index.html Structure)

Use:

* Bootstrap 5
* DC.js
* Crossfilter2
* D3.js

### 📊 Dashboard Layout Diagram

```id="m8v2qp"
---------------------------------------------------------
📊 Customer Churn Prediction Dashboard
---------------------------------------------------------
Navbar:
[ Dashboard | Analytics | Model Performance | Prediction ]
---------------------------------------------------------
KPI Cards:
[ Total Customers ] [ Churned ] [ Churn Rate ] [ Accuracy ]
---------------------------------------------------------
Analytics Section:
[ Churn Distribution ] [ Gender vs Churn ]
[ Spend vs Churn ] [ Tenure vs Churn ]
---------------------------------------------------------
Model Performance:
[ Confusion Matrix ] [ Classification Report ]
---------------------------------------------------------
Prediction Section:
[ Customer Input Form ] [ Prediction Result ]
---------------------------------------------------------
Dataset Section:
[ Customer Data Table ]
---------------------------------------------------------
Footer
---------------------------------------------------------
```

### 🎯 Goal

* Create responsive dashboard using Bootstrap
* Use grid layout for sections
* Allocate areas for charts (DC.js)

---

## ✅ Step 3: Create Model Training Script

### 📌 Task

Create **train_model.py** using the `.ipynb` file.

### 🎯 Purpose

* Load customer dataset
* Perform preprocessing (encoding, normalization)
* Train Random Forest model
* Evaluate model performance

---

## ✅ Step 4: Generate and Save Model

### 📌 Task

Run the training script.

### 🎯 Output

* Save trained model into:

```id="z7p4xm"
/models/model.pkl
```

* This model will be used by backend APIs

---

## ✅ Step 5: Create Backend API (app.py)

### 📌 API Design (Names, Routes, Purpose)

| API Name              | Route                               | Purpose                      |
| --------------------- | ----------------------------------- | ---------------------------- |
| Health Check          | `/api/health`                       | Check API status             |
| Dataset Summary       | `/api/customers/summary`            | Total, churn, rate, accuracy |
| Customer Data         | `/api/customers`                    | All customer records         |
| Churn Distribution    | `/api/analytics/churn-distribution` | Churn vs stay                |
| Gender Churn          | `/api/analytics/gender-churn`       | Gender-based churn           |
| Spend Analysis        | `/api/analytics/spend-churn`        | Spend vs churn               |
| Tenure Analysis       | `/api/analytics/tenure-churn`       | Tenure vs churn              |
| Model Performance     | `/api/model/performance`            | Accuracy & metrics           |
| Confusion Matrix      | `/api/model/confusion-matrix`       | Matrix data                  |
| Classification Report | `/api/model/classification-report`  | Performance metrics          |
| Predict Churn         | `/api/predict-churn`                | Predict customer churn       |

### 🎯 Goal

* Connect dashboard with ML model
* Provide structured JSON responses

---

## ✅ Step 6: Create dashboard.js (Frontend Logic)

### 📌 Responsibilities

dashboard.js connects **index.html ↔ app.py**

### 🔧 Tasks

1. On Page Load

   * Fetch dataset summary
   * Fetch model performance
   * Load charts

2. Prediction Handling

   * Collect user input
   * Send request to prediction API
   * Display churn result (Churn/Stay)

3. Display Data

   * Update KPI cards
   * Populate dataset table
   * Show classification report

4. Chart Rendering

   * Churn Distribution
   * Gender vs Churn
   * Spend vs Churn
   * Confusion Matrix

5. Handle

   * Loading indicators
   * Error handling
   * Dynamic updates

---

## 🎯 Final Flow

```id="n5x2rl"
User → index.html (Dashboard UI)
        ↓
dashboard.js (Frontend Logic)
        ↓
app.py (Backend API)
        ↓
ML Model (Prediction)
        ↓
Response → Dashboard Visualization
```

---

