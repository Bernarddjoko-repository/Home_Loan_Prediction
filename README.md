📌 Project Overview

This project focuses on predicting loan default risk using machine learning techniques. Financial institutions need accurate models to assess credit risk and minimize losses due to loan defaults. We built and evaluated multiple models—including Logistic Regression, Random Forest, and XGBoost—to determine the best-performing model for predicting loan status.

🚀 Goal: Develop a robust classification model that helps lenders decide whether to approve or reject loan applications based on risk assessment.

⚡ Challenges Faced
Imbalanced Dataset:

The dataset had 78% non-default (0) and 22% default (1) cases. This imbalance could lead models to favor predicting non-defaulters, hurting recall.
Feature Selection & Engineering:

Some features were highly correlated, while others had little impact on predictions. Determining which features to retain was critical.
Outlier Handling & Scaling:

The dataset contained outliers, requiring careful handling using IQR, Winsorization, and Log Transformations.
Features had different ranges, necessitating Standardization for normally distributed features and Normalization for skewed features.
Model Selection & Evaluation:

While Logistic Regression was a strong baseline, it underperformed compared to tree-based models.
Choosing the best model required analyzing AUC-ROC, Precision, Recall, and F1-score rather than just accuracy.
🔬 Step-by-Step Approach
🟢 Step 1: Data Preparation
Loaded & explored the dataset to understand its structure.
Handled missing values using median imputation (for skewed distributions).
Checked for duplicates and removed 165 duplicate rows.
🟢 Step 2: Feature Engineering & Selection
Identified numerical and categorical features.
Encoded categorical variables:
Used Label Encoding for Ordinal variables (loan_grade).
Used One-Hot Encoding for Nominal features (loan_intent, home_ownership).
Dropped least important feature (cb_person_cred_hist_length) based on feature importance analysis.
🟢 Step 3: Handling Outliers & Scaling
Applied IQR, Log Transformations, and Winsorization to handle outliers.
Used Standardization (Z-score) for normally distributed features.
Used Min-Max Normalization for skewed distributions.
🟢 Step 4: Addressing Class Imbalance
Detected class imbalance (78%-22%) and applied SMOTE oversampling to balance the dataset.
Ensured the training set had a more balanced distribution to improve model learning.
🟢 Step 5: Model Training & Evaluation
Trained three models:
✅ Logistic Regression (Baseline)
✅ Random Forest
✅ XGBoost (Best Model)

Evaluated models based on:

AUC-ROC (Most important metric)
Precision (To avoid rejecting too many good customers)
Recall (To avoid missing risky borrowers)
F1-Score (Balance between Precision & Recall)
📊 Results:

Metric	Logistic Regression	Random Forest	XGBoost
Accuracy	79.04%	92.78%	93.18%
Precision	51.17%	91.43%	93.90%
Recall	77.52%	73.68%	73.39%
F1 Score	61.65%	81.60%	82.39%
AUC-ROC	86.56%	93.19%	94.31%
🔹 Final Decision:

XGBoost was the best model with the highest AUC-ROC (94.31%), making it the most reliable for predicting loan defaults.
While Logistic Regression had the highest Recall, its Precision was too low (51.17%), making it unfit for real-world deployment.
Random Forest performed well but was slightly outperformed by XGBoost.
🚀 Future Improvements & Recommendations
💡 1. Hyperparameter Tuning:

Use Grid Search or Bayesian Optimization to fine-tune XGBoost parameters for even better performance.
💡 2. Model Explainability (SHAP Analysis):

Implement SHAP (SHapley Additive Explanations) to interpret how each feature affects loan decisions.
💡 3. Deploy Model as an API:

Use Flask or FastAPI to deploy the model and make real-time predictions.
Alternatively, use Streamlit to create an interactive web dashboard for lenders.
💡 4. Feature Engineering Enhancements:

Include additional external credit bureau data or borrower behavioral insights.
Engineer new features such as debt-to-income ratio trends over time.
