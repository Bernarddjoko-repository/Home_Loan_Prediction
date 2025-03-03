## Loan Prediction API - Machine Learning Model Deployment with Flask and Swagger

### Project Description
This project is a Loan Prediction System that uses Machine Learning to determine the likelihood of loan approval based on applicant information such as loan amount, income, debt-to-income ratio, and credit history.

The project follows an end-to-end machine learning workflow, including:<br>
✔ Data Preprocessing & Feature Engineering<br>
✔ Machine Learning Model Selection & Optimization<br>
✔ Model Interpretability using SHAP<br>
✔ API Deployment with Flask & Swagger<br>

This project demonstrates skills in data preprocessing, model selection, explainability, and API deployment, making it a valuable portfolio piece for machine learning and MLOps roles.

### Project Challenges
The main challenges faced in this project included:<br>
🔹 Imbalanced Data: The dataset had significantly more rejected loans than approved ones.<br>
🔹 Model Selection: Identifying the best ML model with high accuracy and generalizability.<br>
🔹 Feature Interpretability: Ensuring model predictions were explainable using SHAP values.<br>
🔹 API Deployment Issues: Managing routing conflicts, dependency mismatches, and Swagger UI integration.<br>
🔹 Performance Optimization: Balancing model complexity with computational efficiency.<br>

### Step-by-Step Approach
1️⃣ Data Preprocessing & Feature Engineering<br>
Cleaned and handled missing values.<br>
Encoded categorical variables like loan purpose, home ownership, and employment length.<br>
Scaled numerical features to ensure consistency.<br>
Applied SMOTE (Synthetic Minority Over-sampling Technique) to rebalance the dataset and prevent model bias.<br>

2️⃣ Machine Learning Model Selection & Optimization<br>
Model Evaluation<br>
We evaluated multiple machine learning models to determine the best performer:<br>

Model	Accuracy	Precision	Recall	F1-Score	AUC-ROC
Logistic Regression	Moderate	Moderate	Moderate	Moderate	Good
Random Forest	Best	High	High	Best	Best
XGBoost	Competitive	High	Moderate	Good	Very Good
The Random Forest Classifier emerged as the best model due to:
✔ High Accuracy and Recall: It effectively captured patterns in loan approvals.
✔ Robustness to Outliers and Missing Data: Unlike Logistic Regression, it handled noisy financial data better.
✔ Feature Importance Interpretability: Enabled clear insights using SHAP values.

Hyperparameter tuning was performed to optimize tree depth, number of estimators, and splitting criteria, ensuring maximum predictive performance.

###3️⃣ Model Explainability with SHAP
SHAP values were used to explain how individual features influenced loan approval.
Key insights from SHAP analysis:
Loan amount, annual income, and debt-to-income ratio had the most impact.
Higher income and lower debt improved approval chances.
Loan term (36 vs. 60 months) played a moderate role in decision-making.
This interpretability made the model trustworthy and explainable, which is crucial in financial decision-making.

###4️⃣ Deployment as a Flask API
The trained Random Forest model was wrapped in a Flask API.
Swagger UI was integrated to provide interactive documentation for API users.
The API exposed:
A home route (/) to verify the API is running.
A prediction route (/predict) that accepts loan applicant data and returns approval predictions.
A Swagger UI (/apidocs/) to visualize API endpoints and test predictions.
###5️⃣ Problems Faced & Solutions
🔹 1. Imbalanced Dataset
Problem: The dataset was heavily skewed towards rejected loans, leading to biased predictions.
✅ Solution: Used SMOTE to generate synthetic examples and balance the dataset.

🔹 2. Slow SHAP Computation
Problem: SHAP calculations were computationally expensive for large datasets.
✅ Solution: Reduced the dataset sample size for SHAP analysis, maintaining interpretability while improving performance.

🔹 3. Flask API Deployment Issues
Problem: The API initially failed to start due to SystemExit errors and dependency conflicts.
✅ Solution: Disabled the Flask reloader, corrected dependency mismatches, and resolved boto3 issues.

🔹 4. Swagger UI Not Displaying Endpoints
Problem: Swagger UI loaded but did not show the /predict endpoint.
✅ Solution: Ensured correct function docstrings and verified that Swagger(app) was properly initialized.

Final Results & Key Takeaways
✔ Best ML Model: Random Forest Classifier (outperformed Logistic Regression and XGBoost).
✔ SHAP Visualizations: Explained the top features influencing loan approval.
✔ Fully Deployed Flask API: Interactive Swagger UI and functional prediction endpoint.
✔ Technical Issues Resolved: Overcame imbalanced data, API deployment errors, and performance bottlenecks.

Recommendations for Further Improvement
🚀 Dockerize the Application

Package into a Docker container for seamless deployment across environments.
🌍 Deploy on Cloud Services

Host the API on AWS Lambda, Google Cloud, or Azure for broader accessibility.
📊 Build a User-Friendly Interface

Develop a Streamlit or React UI to let users enter loan details and receive predictions.
🔍 Enhance Model Performance

Experiment with additional models like CatBoost or deep learning architectures.
📡 Implement API Monitoring & Logging

Use tools like AWS CloudWatch or ELK Stack for tracking API performance.

Conclusion
This project showcases end-to-end machine learning skills, including model selection, hyperparameter tuning, interpretability, and API deployment. It is a strong portfolio project demonstrating expertise in MLOps, data science, and Flask API engineering.

🔥 If you find this project useful, give it a ⭐ on GitHub! 🚀

💡 Hiring Managers: This project demonstrates real-world ML deployment, explainability with SHAP, and scalability using Flask APIs, making it a strong portfolio piece for machine learning roles.

