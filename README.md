# MSc-Advanced-computer-science-Final-project
# Explainable Machine Learning Framework for Credit Card Fraud Detection and Risk Management in Banking Systems

## Project Overview

Credit card fraud is a significant challenge for the banking and financial services industry. The increasing use of digital payment systems has created a need for intelligent fraud detection approaches capable of identifying suspicious transactions accurately while minimising false-positive alerts.

This project develops and evaluates an Explainable Machine Learning Framework for Credit Card Fraud Detection and Risk Management. It investigates the application of machine learning algorithms, class imbalance handling techniques and Explainable Artificial Intelligence (XAI) to identify fraudulent credit card transactions and improve the interpretability of model predictions.

The project uses the European Credit Card Fraud Detection dataset and evaluates five machine learning approaches: Logistic Regression, Random Forest, XGBoost, Isolation Forest and Hybrid XGBoost. SHapley Additive exPlanations (SHAP) is incorporated to examine feature contributions and provide insights into model behaviour.

## Project Aim

To develop and evaluate an explainable machine learning framework for detecting fraudulent credit card transactions and supporting fraud risk management in banking systems.

## Research Question

How can explainable machine learning be leveraged in detecting fraud on retail banking transactions made through credit cards, and what is the trade-off between model explainability and performance?

## Project Objectives

- Review existing research on credit card fraud detection, machine learning and Explainable Artificial Intelligence.
- Acquire and preprocess a publicly available credit card transaction dataset.
- Investigate transaction patterns, class imbalance and feature relationships through Exploratory Data Analysis (EDA).
- Develop and evaluate Logistic Regression, Random Forest and XGBoost classification models.
- Apply SMOTE to address the imbalance between legitimate and fraudulent transactions during model training.
- Investigate Isolation Forest and Hybrid XGBoost for anomaly-based fraud detection.
- Integrate SHAP to examine feature importance and model predictions.
- Evaluate model performance using precision, recall, F1-score and ROC-AUC.
- Examine the trade-off between predictive performance and model explainability.

## Dataset Description

**Dataset:** European Credit Card Fraud Detection

**Source:** Machine Learning Group – Université Libre de Bruxelles (ULB)

**Platform:** Kaggle

**Dataset Link:** https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud

The original dataset contains 284,807 credit card transactions, including 492 fraudulent transactions.

Following duplicate removal, the cleaned dataset contains:

| Description | Records |
|---|---:|
| Original transactions | 284,807 |
| Original fraudulent transactions | 492 |
| Cleaned transactions | 283,726 |
| Legitimate transactions | 283,253 |
| Fraudulent transactions | 473 |

The dataset includes 30 original columns, consisting of Time, Amount, 28 anonymised PCA-transformed features (V1–V28) and the target variable Class.

The Class variable identifies legitimate transactions (0) and fraudulent transactions (1).

## Technologies and Tools

| Category | Technologies |
|---|---|
| Programming Language | Python |
| Development Environment | Google Colab / Jupyter Notebook |
| Data Manipulation | Pandas, NumPy |
| Data Visualisation | Matplotlib, Seaborn |
| Machine Learning | Scikit-learn |
| Gradient Boosting | XGBoost |
| Class Imbalance Handling | SMOTE |
| Explainable AI | SHAP |
| Model Evaluation | Confusion Matrix, ROC Curve, Precision–Recall Curve |

## Project Methodology

The project follows a structured machine learning workflow.

### 1. Data Acquisition

The European Credit Card Fraud Detection dataset was obtained from Kaggle and loaded into the Python development environment.

### 2. Data Preprocessing

The dataset was inspected and prepared for model development. Duplicate records were removed, and the transaction features were retained for subsequent analysis.

### 3. Exploratory Data Analysis

EDA was conducted to investigate:

- Fraudulent versus legitimate transaction distribution.
- Transaction amount distributions.
- Transaction amount variation by fraud status.
- Feature correlation patterns.
- Distribution of selected PCA features.
- Pairwise relationships between selected features.
- Transaction amount variation across observations.

### 4. Handling Class Imbalance

SMOTE (Synthetic Minority Over-sampling Technique) was applied to the training data to increase the representation of fraudulent transactions and address the severe class imbalance.

### 5. Machine Learning Model Development

Five approaches were implemented and evaluated:

| Model | Description |
|---|---|
| Logistic Regression | Baseline supervised classification algorithm |
| Random Forest | Ensemble learning using multiple decision trees |
| XGBoost | Gradient boosting classification algorithm |
| Isolation Forest | Unsupervised anomaly detection approach |
| Hybrid XGBoost | XGBoost incorporating an additional anomaly_score feature |

### 6. Model Evaluation

The models were evaluated using:

- Precision
- Recall
- F1-score
- ROC-AUC
- Confusion matrices
- ROC curves
- Precision–Recall curves

These metrics were selected to examine the models' ability to identify fraudulent transactions while considering false-positive and false-negative predictions.

### 7. Explainable AI Using SHAP

SHAP was integrated with an XGBoost model using TreeExplainer.

The explainability analysis included:

- Global feature importance.
- SHAP summary plots.
- SHAP beeswarm visualisation.
- Feature contribution analysis.

The prominent features identified in the SHAP analysis included V14, V4, V12, anomaly_score, V11, V1, V3 and V10.

## Experimental Results

The experiments demonstrated different strengths across the evaluated approaches.

The reported comparative results showed:

| Model | Precision | Recall | F1-score | ROC-AUC |
|---|---:|---:|---:|---:|
| Logistic Regression | 0.12 | 0.86 | 0.21 | 0.9534 |
| Random Forest | 0.90 | 0.77 | 0.83 | 0.9644 |
| XGBoost | 0.71 | 0.80 | 0.75 | 0.9600 |
| Isolation Forest | 0.08 | 0.52 | 0.14 | 0.9543 |
| Hybrid XGBoost | 0.66 | 0.80 | 0.72 | 0.9796 |

**Key findings from the reported comparison:**

- Random Forest achieved the highest reported precision and F1-score.
- Logistic Regression achieved the highest reported recall.
- Hybrid XGBoost achieved the highest reported ROC-AUC.
- SHAP identified the features contributing most prominently to XGBoost predictions.

The results demonstrate that different algorithms provide different advantages depending on the evaluation metric. Model selection therefore requires consideration of both fraud detection performance and the operational impact of false alerts.

**Results validation note:** These comparative figures represent an earlier reported experimental run. Some subsequently generated confusion matrices show different prediction counts and derived metrics. The final repository results should be reconciled against one consistent notebook execution before treating this table as the definitive evaluation.

## Explainability and Feature Analysis

The SHAP analysis was used to investigate how individual features influenced XGBoost predictions.

The global feature importance analysis highlighted V14 as the most influential feature, followed by V4, V12 and anomaly_score.

The SHAP beeswarm plot provided additional information about the direction and distribution of feature contributions across observations.

As the dataset contains anonymised PCA-transformed variables, their original financial meanings cannot be directly established. Therefore, the SHAP findings are interpreted as statistical feature contributions rather than direct explanations of specific banking behaviours.

## Project Limitations

- The dataset represents historical transactions rather than live banking activity.
- The original dataset contains a severe imbalance between legitimate and fraudulent transactions.
- The PCA-transformed features limit direct business interpretation.
- Synthetic oversampling cannot fully reproduce the complexity of real fraudulent behaviour.
- Further validation is required before applying the framework in a real banking environment.
- Additional investigation of individual transaction explanations would strengthen practical interpretability.

## Future Enhancements

Potential future improvements include:

- Integration with real-time transaction monitoring systems.
- Evaluation using additional financial transaction datasets.
- Classification threshold optimisation.
- Cost-sensitive learning for fraud detection.
- Additional anomaly detection and ensemble methods.
- Individual transaction-level SHAP explanations.
- Development of an interactive fraud monitoring dashboard.
- Further validation and testing in realistic banking environments.

## Project Structure

A suggested repository organisation is:

```text
Credit-Card-Fraud-Detection/
│
├── Dataset/
│   └── creditcard.csv
│
├── Notebooks/
│   └── Credit_Card_Fraud_Detection.ipynb
│
├── Results/
│   ├── EDA/
│   ├── Confusion_Matrices/
│   ├── ROC_Curves/
│   ├── Model_Comparisons/
│   └── SHAP_Analysis/
│
├── Report/
│   └── Final_Project_Report.pdf
│
├── README.md
└── requirements.txt
```

The folder structure should be adjusted to match the files actually uploaded to the GitHub repository.

## Academic Context

**Programme:** MSc Advanced Computer Science

**Project Area:** Artificial Intelligence, Machine Learning, Explainable AI and Financial Fraud Detection

**Project Type:** Individual MSc Research and Implementation Project

## Conclusion

This project demonstrates the application of machine learning and explainable artificial intelligence to credit card fraud detection. By combining supervised classification, anomaly detection, class imbalance handling and SHAP-based explanations, the framework investigates both predictive performance and model transparency.

The experimental findings highlight the importance of selecting machine learning models using multiple evaluation metrics rather than relying on a single performance measure. The project provides an experimental foundation for further research into intelligent and explainable fraud detection systems in banking and financial services.

## References

- Chawla, N.V., Bowyer, K.W., Hall, L.O. and Kegelmeyer, W.P. (2002). SMOTE: Synthetic minority over-sampling technique. *Journal of Artificial Intelligence Research*, 16, pp. 321–357.
- Lundberg, S.M. and Lee, S.I. (2017). A unified approach to interpreting model predictions. *Advances in Neural Information Processing Systems*, 30, pp. 4765–4774.
- Machine Learning Group – ULB (n.d.). Credit Card Fraud Detection. Kaggle dataset. https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud.

---

**Note:** This repository is intended for academic and research purposes. The project uses an anonymised historical dataset and is not a production-ready banking fraud detection system.
