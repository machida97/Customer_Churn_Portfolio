# 📊 Customer Churn Prediction – Telecom Case Study

## 📌 Project Overview  
Customer churn is a critical challenge in the telecom industry. Acquiring new customers is often **5–7x more expensive** than retaining existing ones, so predicting and preventing churn is a key driver of profitability.  

In this project, I analyze the **Telco Customer Churn dataset** and build machine learning models to predict which customers are at risk of leaving. Beyond standard modeling, I simulate a **deployment scenario** where the trained model identifies the **top 20 high-risk customers** and generates **actionable business insights** for retention strategies.  

---

## 📂 Repository Structure

customer-churn-prediction/
│
├── data/
│ ├── Telco-Customer-Churn.csv # Original dataset
│ └── dataset_part_1_cleaned.csv # Cleaned/preprocessed version
│
├── notebooks/
│ ├── Customer_Churn_Analysis_(EDA).ipynb # Exploratory Data Analysis
│ └── Customer_Churn_(Prediction).ipynb # Modeling & deployment simulation
│
├── models/
│ └── reduced_rf_churn_model.pkl # Saved Random Forest model
│
├── requirements.txt # Python dependencies
├── README.md # Documentation
└── .gitignore

---

## 📊 Dataset  
- **Source:** [Kaggle – Telco Customer Churn Dataset](https://www.kaggle.com/blastchar/telco-customer-churn)  
- **Rows:** 7,043 customers  
- **Features:** 21 (customer demographics, services, account information, and churn status)  

**Target variable:**  
- `Churn` → Whether the customer left the company (Yes/No).  

---

## 🔍 Exploratory Data Analysis (EDA)  
EDA was conducted in `Customer_Churn_Analysis_(EDA).ipynb`.  

### Key Insights:
- **Tenure** is the strongest predictor: customers with <12 months are far more likely to churn.  
- **Contract type:** Month-to-month contracts show the highest churn rates.  
- **Online security & tech support:** Absence of these services strongly correlates with churn.  
- **Senior citizens:** Churn at a higher rate compared to younger customers.  

📈 Visualizations include churn distribution, categorical churn rates, tenure distributions, and correlation heatmaps.

---

## 🤖 Modeling  
Implemented in `Customer_Churn_(Prediction).ipynb`.  

### Steps:
1. **Preprocessing:** Encoding categorical variables, scaling, feature engineering (e.g., Estimated Lifetime Value).  
2. **Train/Test Split:** 80/20 split with stratification on `Churn`.  
3. **Baseline Models Tested:**
   - Logistic Regression  
   - Decision Tree  
   - Random Forest  
   - Gradient Boosting  
   - Support Vector Machine  
4. **Evaluation Metrics:**
   - AUC (ROC curve)  
   - Confusion Matrix  
   - Classification Report (Precision, Recall, F1)  

### Best Model:
- **Reduced-feature Random Forest**  
- Balanced predictive power + interpretability.  

| Model              | AUC   | Accuracy | Recall (Churn) |
|--------------------|-------|----------|----------------|
| Logistic Regression | ~0.82 | ~0.80   | ~0.70          |
| Decision Tree       | ~0.79 | ~0.78   | ~0.68          |
| **Random Forest**   | **0.86** | **0.83** | **0.74**      |
| Gradient Boosting   | ~0.85 | ~0.82   | ~0.72          |
| SVM                 | ~0.81 | ~0.80   | ~0.69          |

---

## 🚀 Deployment Simulation  
To illustrate real-world use, the final notebook includes a **simulation of deployment**:  
- The trained Random Forest model identifies the **top 20 customers with the highest churn probability**.  
- Results show that:  
  - Most at-risk customers are **new (low tenure)**.  
  - A subset have **high monthly charges**, making them valuable retention targets.  
  - Combining churn probability with tenure, charges, and lifetime value provides **actionable retention strategies**.  

🔑 **Business Recommendation:**  
- Focus retention on **new customers** with personalized onboarding.  
- Prioritize high-value customers for targeted retention campaigns.  
- Use churn probability + financial metrics to **optimize resource allocation**.  

---

## ⚙️ How to Run
1. Clone the repository:  
   ```bash
   git clone https://github.com/<your-username>/customer-churn-prediction.git
   cd customer-churn-prediction

2. Install dependencies:

pip install -r requirements.txt

3. Run notebooks in Jupyter or VSCode:
- notebooks/Customer_Churn_Analysis_(EDA).ipynb
- notebooks/Customer_Churn_(Prediction).ipynb

📈 Skills Demonstrated
- Data wrangling, feature engineering
- Classification modeling (LogReg, Tree-based models, SVM)
- Model evaluation with multiple metrics
- Feature importance analysis
- Deployment simulation & business translation

📌 Next Steps
- Extend project to include customer lifetime value regression modeling.
- Build a time series churn forecasting pipeline.
- Deploy model with Flask/FastAPI + Streamlit dashboard for interactive churn prediction.

