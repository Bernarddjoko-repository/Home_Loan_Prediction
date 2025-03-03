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

Model	Accuracy	Precision	Recall	F1-Score	AUC-ROC<br>
Logistic Regression	Moderate	Moderate	Moderate	Moderate	Good
Random Forest	Best	High	High	Best	Best
XGBoost	Competitive	High	Moderate	Good	Very Good
The Random Forest Classifier emerged as the best model due to:<br>
✔ High Accuracy and Recall: It effectively captured patterns in loan approvals.<br>
✔ Robustness to Outliers and Missing Data: Unlike Logistic Regression, it handled noisy financial data better.<br>
✔ Feature Importance Interpretability: Enabled clear insights using SHAP values.<br>

Hyperparameter tuning was performed to optimize tree depth, number of estimators, and splitting criteria, ensuring maximum predictive performance.<br>

3️⃣ Model Explainability with SHAP<br>
SHAP values were used to explain how individual features influenced loan approval.<br>
Key insights from SHAP analysis:<br>
Loan amount, annual income, and debt-to-income ratio had the most impact.<br>
Higher income and lower debt improved approval chances.<br>
Loan term (36 vs. 60 months) played a moderate role in decision-making.<br>
This interpretability made the model trustworthy and explainable, which is crucial in financial decision-making.<br>

4️⃣ Deployment as a Flask API<br>
The trained Random Forest model was wrapped in a Flask API.<br>
Swagger UI was integrated to provide interactive documentation for API users.<br>
The API exposed:<br>
A home route (/) to verify the API is running.<br>
A prediction route (/predict) that accepts loan applicant data and returns approval predictions.<br>
A Swagger UI (/apidocs/) to visualize API endpoints and test predictions.<br>

5️⃣ Problems Faced & Solutions<br>

🔹 1. Imbalanced Dataset<br>
Problem: The dataset was heavily skewed towards rejected loans, leading to biased predictions.<br>
✅ Solution: Used SMOTE to generate synthetic examples and balance the dataset.

🔹 2. Slow SHAP Computation<br>
Problem: SHAP calculations were computationally expensive for large datasets.<br>
✅ Solution: Reduced the dataset sample size for SHAP analysis, maintaining interpretability while improving performance.<br>

🔹 3. Flask API Deployment Issues<br>
Problem: The API initially failed to start due to SystemExit errors and dependency conflicts.<br>
✅ Solution: Disabled the Flask reloader, corrected dependency mismatches, and resolved boto3 issues.<br>

🔹 4. Swagger UI Not Displaying Endpoints<br>
Problem: Swagger UI loaded but did not show the /predict endpoint.<br>
✅ Solution: Ensured correct function docstrings and verified that Swagger(app) was properly initialized.<br>

Final Results & Key Takeaways<br>
✔ Best ML Model: Random Forest Classifier (outperformed Logistic Regression and XGBoost).<br>
✔ SHAP Visualizations: Explained the top features influencing loan approval.<br>
✔ Fully Deployed Flask API: Interactive Swagger UI and functional prediction endpoint.<br>
✔ Technical Issues Resolved: Overcame imbalanced data, API deployment errors, and performance bottlenecks.<br>

Recommendations for Further Improvement<br>
🚀 Dockerize the Application<br>

Package into a Docker container for seamless deployment across environments.<br>
🌍 Deploy on Cloud Services<br>

Host the API on AWS Lambda, Google Cloud, or Azure for broader accessibility.<br>
📊 Build a User-Friendly Interface<br>

Develop a Streamlit or React UI to let users enter loan details and receive predictions.<br>
🔍 Enhance Model Performance<br>

Experiment with additional models like CatBoost or deep learning architectures.<br>
📡 Implement API Monitoring & Logging<br>

Use tools like AWS CloudWatch or ELK Stack for tracking API performance.<br>

Conclusion<br>
This project showcases end-to-end machine learning skills, including model selection, hyperparameter tuning, interpretability, and API deployment. It is a strong portfolio project demonstrating expertise in MLOps, data science, and Flask API engineering.

🔥 If you find this project useful, give it a ⭐ on GitHub! 🚀

