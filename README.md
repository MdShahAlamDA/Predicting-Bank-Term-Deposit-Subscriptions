## **Overview**
This project aims to predict whether a bank customer will subscribe to a term deposit based on demographic, financial, and campaign-related features. The dataset originates from a Portuguese banking institution’s direct marketing campaigns. Accurate predictions can help optimize telemarketing efforts and reduce costs.

---

## **Problem Statement**
Term deposits are a significant source of income for banks. Telemarketing is a key method to reach potential customers but requires substantial investment. To reduce inefficiencies, we aim to build a predictive model that identifies the customers most likely to subscribe to a term deposit, enabling targeted outreach.

---

## **Dataset Description**

The dataset contains information about direct marketing campaigns conducted through phone calls.

### **Columns:**

- **Bank Client Data:**
  - `age`: Age of the client (numeric).
  - `job`: Type of job (categorical).
  - `marital`: Marital status (categorical).
  - `education`: Level of education (categorical).
  - `default`: Has credit in default? (binary).
  - `balance`: Average yearly balance in euros (numeric).
  - `housing`: Has a housing loan? (binary).
  - `loan`: Has a personal loan? (binary).

- **Campaign Data:**
  - `contact`: Communication type (categorical).
  - `day`: Last contact day of the month (numeric).
  - `month`: Last contact month of the year (categorical).
  - `duration`: Last contact duration in seconds (numeric).

- **Historical Campaign Data:**
  - `campaign`: Number of contacts performed during this campaign (numeric).
  - `pdays`: Number of days since the client was last contacted (numeric; -1 indicates not previously contacted).
  - `previous`: Number of contacts before this campaign (numeric).
  - `poutcome`: Outcome of the previous marketing campaign (categorical).

- **Target Variable:**
  - `y`: Whether the client subscribed to a term deposit (binary: "yes", "no").

---

## **Project Workflow**

### **1. Exploratory Data Analysis (EDA):**
- **Objective:** Identify patterns, trends, and anomalies.
- **Techniques:**
  - Histograms and boxplots for numerical features.
  - Count plots for categorical variables.
  - Correlation heatmaps for feature relationships.
  - Scatter plots to explore interactions between key variables.

### **2. Data Preprocessing:**
- Handle categorical variables using:
  - Label Encoding for binary columns.
  - One-Hot Encoding for multi-class categorical columns.
- Scale numerical features using StandardScaler.
- Feature engineering:
  - Interaction terms: `duration * balance`, `age * balance`.
  - Removal of low-importance features like `pdays`.

### **3. Model Building:**
- Models Implemented:
  - Logistic Regression
  - Decision Tree
  - Random Forest
  - Gradient Boosting (Hyperparameter-tuned using GridSearchCV)
- Performance Evaluation:
  - Metrics: Accuracy, Precision, Recall, F1-score, ROC-AUC.
  - Visualization: Confusion Matrix, Feature Importance.

### **4. Prediction:**
- Use the best-performing model to generate predictions on the test dataset.
- Save predictions in the required format (`TeamName.csv`).

### **5. Visualization:**
- Use Power BI for interactive dashboards:
  - Age group vs. subscription.
  - Job distribution.
  - Month-wise success rates.

---

## **Key Findings**
- **Demographics:**
  - Middle-aged clients (30–40) with higher balances are more likely to subscribe.
  - Customers with tertiary education show higher subscription rates.

- **Behavioral Patterns:**
  - Longer call durations strongly correlate with successful subscriptions.
  - Clients contacted via cellular phones respond better than those contacted via telephones.

- **Campaign Performance:**
  - Persistent follow-ups (2–3 contacts) improve success, but excessive contacts may reduce effectiveness.
  - Months like May and October show higher subscription rates.

---

## **Technologies Used**
- **Programming:** Python (pandas, seaborn, scikit-learn, matplotlib).
- **Visualization:** Power BI.
- **Machine Learning Models:** Logistic Regression, Decision Tree, Random Forest, Gradient Boosting.

---

## **How to Run the Project**

1. **Set Up the Environment:**
   - Install dependencies:
     ```bash
     pip install pandas numpy scikit-learn seaborn matplotlib xgboost lightgbm
     ```

2. **Run EDA:**
   - Use `project.py` to explore the data and visualize key patterns.

3. **Preprocess Data:**
   - Execute `encoding.py` to encode features, scale data, and engineer new features.

4. **Train Models:**
   - Use `testing.py` to train models and evaluate performance.

5. **Generate Predictions:**
   - Apply the trained model on the test dataset.
   - Save the output in the format `TeamName.csv`.

---

## **Deliverables**
1. **Prediction File:** CSV file with predictions.
2. **EDA Report:** Insights and visualizations exported to PDF (from Power BI or Python).
3. **Presentation:** A PowerPoint file summarizing the approach, key findings, and results.
4. **GitHub Repository:** Include all scripts, README.md, and deliverables.

---

## **Acknowledgments**
- **Dataset:** Portuguese banking institution.
- **Tools:** Python, Power BI, scikit-learn.
- **Guidance:** Project mentors and teammates.

