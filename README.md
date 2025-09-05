# Banking-Transaction-Fraud-Detection-ML-PowerBI-

# 🏦 Bank Transaction Fraud Detection (IEEE-CIS Dataset)

## 📌 Overview
This project focuses on detecting fraudulent online transactions using the **IEEE-CIS Fraud Detection dataset**.  
The dataset is highly imbalanced, making fraud detection a challenging task.  
We applied **feature engineering, resampling techniques (SMOTE), machine learning models, and Power BI visualizations** to build a fraud detection system that improves the recall for minority class (fraudulent transactions).

---

## 📂 Dataset
- **Source**: [IEEE-CIS Fraud Detection Dataset (Kaggle)](https://www.kaggle.com/c/ieee-fraud-detection)
- **Rows**: ~6,00,000  
- **Features**: Transaction-related attributes (`TransactionAmt`, `ProductCD`, `card1-card6`, `addr1`, `DeviceType`, `V1-V339`, etc.)  
- **Target**:  
  - `isFraud = 1` → Fraudulent transaction  
  - `isFraud = 0` → Genuine transaction  

---

## ⚙️ Preprocessing & Feature Engineering
- Handled missing values using mode/mean sampling.
- Feature mapping:  
  - **Fraud Rate Encoding**: Mapped fraud rates for categorical variables (`overall`, `hourly`, `daily`, `monthly`).  
  - **Frequency Encoding**: Added frequency counts for categorical variables.  
- Binned continuous variables like `TransactionAmt`.  
- Removed low-correlation V-features.  
- Applied **SMOTE** to handle class imbalance.  

---

## 🧠 Models Used
- **Logistic Regression** (with class weights, scaled features)  
- **Random Forest Classifier**  
- **LightGBM**  
- **CatBoost**  
- **Neural Networks (Keras/TensorFlow)**  

---

## 📊 Evaluation Metrics
Due to imbalanced nature, we focused on **Recall** and **F1-score** for fraud class (`isFraud=1`):  
- **Accuracy**  
- **Precision**  
- **Recall**  
- **F1-score**  
- **ROC-AUC Score**  

---

## 🚀 Results
- **SMOTE** significantly improved recall for class `1` (frauds).  
- **LightGBM** and **CatBoost** outperformed baseline models.  
- Feature engineering with fraud-rate & frequency mappings boosted performance.  

| Model              | Accuracy | Recall (Fraud) | Precision (Fraud) | F1-score |
|--------------------|----------|----------------|-------------------|----------|
| Logistic Regression | 96%     | 0.45           | 0.62              | 0.52     |
| Random Forest      | 97%     | 0.51           | 0.65              | 0.57     |
| LightGBM           | 98%     | 0.59           | 0.72              | 0.65     |
| CatBoost           | 98%     | 0.61           | 0.74              | 0.67     |

---

## 📈 Visualization (Power BI)
To make fraud insights more interpretable, an **interactive dashboard** was created using **Power BI**:  
- Fraud count by **hour/day/month**  
- Fraud count by **Transaction Amount bins**  
- Fraud distribution by **categorical variables (ProductCD, card types, etc.)**  
- Model performance metrics visualization  

The Power BI dashboard provides a business-friendly view of fraud patterns and model predictions.  

---

## 💡 Key Learnings
- Class imbalance is a major challenge in fraud detection.  
- Feature engineering (fraud-rate mapping, frequency encoding) improves predictive power.  
- Combining ML models with **Power BI dashboards** bridges the gap between data science and business insights.  

---

## 📌 How to Run
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/ieee-fraud-detection.git
   cd ieee-fraud-detection
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Download dataset from Kaggle and place it in `data/` folder.  
4. Run preprocessing and training notebooks:
   ```bash
   jupyter notebook
   ```
5. Open the Power BI file (`fraud_dashboard.pbix`) to explore the visualizations.  

---

## 📚 Requirements
- Python 3.8+  
- pandas, numpy  
- scikit-learn  
- imbalanced-learn  
- lightgbm  
- catboost  
- tensorflow / keras  
- matplotlib, seaborn  
- Power BI Desktop  

---

## 🙌 Acknowledgements
- Dataset: [IEEE-CIS Fraud Detection](https://www.kaggle.com/c/ieee-fraud-detection)  
- Kaggle community discussions for feature engineering insights.  

---

✨ *This project demonstrates practical fraud detection techniques using real-world financial data and interactive dashboards.*  
