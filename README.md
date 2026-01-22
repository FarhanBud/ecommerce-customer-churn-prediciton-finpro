# E-Commerce Customer Churn Analysis and Prediction

**Final Project - Data Science & Machine Learning Program**
**Institution:** Purwadhika Digital School
**Group Beta:**
- Muhamad Farhan Budiana
- Muhammad Ghifari
- Shadrina Putri Nabila

## Project Overview

Customer churn presents a significant challenge in the e-commerce sector, directly impacting revenue stability and increasing operational costs due to the high expense of acquiring new customers compared to retaining existing ones. This project aims to develop a robust machine learning model capable of predicting customer churn, thereby enabling proactive retention strategies.

The analysis follows a comprehensive end-to-end data science workflow, including data cleaning, rigorous preprocessing to prevent data leakage, handling class imbalance, and hyperparameter tuning to optimize model performance.

## Business Context and Objective

### Problem Statement
<img width="613" height="511" alt="image" src="https://github.com/user-attachments/assets/5d9daa6d-9dd1-49d0-90c3-25e8b87856e5" />


The company is currently experiencing a customer churn rate of approximately 16.8%. The lack of a predictive mechanism results in a reactive approach to customer retention, leading to inefficient marketing spend and lost revenue opportunities.

### Objectives
1.  **Predictive Modeling:** Develop a binary classification model to identify customers at high risk of churn.
2.  **Metric Optimization:** Prioritize **Recall** to minimize False Negatives (identifying as many potential churners as possible).
3.  **Business Insight:** Analyze feature importance to understand key drivers of customer attrition.

## Analytical Approach

To ensure model validity and performance, the following methodology was applied:

1.  **Data Quality & Leakage Prevention:**
    - Removed lagging indicators (e.g., `DaySinceLastOrder`) to prevent look-ahead bias and data leakage.
    - Standardized categorical values to reduce dimensionality and improve consistency.

2.  **Preprocessing Pipeline:**
    - **Data Splitting:** Applied stratified sampling to maintain class distribution in training and testing sets.
    - **Imputation:** Implemented median and mode imputation within a pipeline to prevent statistical leakage from the test set.
    - **Scaling & Encoding:** Utilized StandardScaler for distance-based algorithms and OneHotEncoder for categorical variables.

3.  **Handling Class Imbalance:**
    - Integrated SMOTE (Synthetic Minority Over-sampling Technique) within the cross-validation process to address the minority class (churners) without overfitting.

4.  **Model Selection:**
    - Benchmarked multiple algorithms: Logistic Regression, K-Nearest Neighbors (KNN), Random Forest, and XGBoost.
    - Selected the optimal model based on Recall performance on the validation set.

## Key Results

### Final Model Performance
The **K-Nearest Neighbors (KNN)** algorithm was selected as the final model after hyperparameter tuning.

-   **Hyperparameters:** `n_neighbors=11`, `weights='distance'`, `metric='euclidean'`
-   **Recall (Test Set):** ~91%
-   **Interpretation:** The model successfully identifies approximately 91% of customers who are actually at risk of churning. This high recall ensures that retention efforts cover the vast majority of at-risk customers.

### Business Recommendations
Based on the Exploratory Data Analysis (EDA) and model insights:

1.  **Early Lifecycle Retention:** Churn risk is highest during the initial months of subscription (low tenure). Implementation of an intensive 90-day onboarding program is recommended.
2.  **Complaint Management:** Customers with a history of complaints show a significantly higher propensity to churn. A dedicated task force with an accelerated Service Level Agreement (SLA) should be established for priority complaint resolution.
3.  **Re-engagement Strategy:** Inactivity is a strong predictor of churn. Automated, personalized re-engagement campaigns should be triggered for users showing declining app usage.

## Repository Structure

-   **data/**: Contains the dataset files used for analysis.
-   **model/**: Stores the serialized model artifacts (pickle files) for deployment.
-   **dashboard/**: Directory for the deployment application (Streamlit).
-   **notebooks/**: Jupyter notebooks containing the detailed analysis and modeling code.
-   **requirements.txt**: List of Python dependencies required to reproduce the environment.

## Installation and Usage

To replicate the analysis or run the model:

1.  Clone the repository:
    ```bash
    git clone [https://github.com/your-username/E-Commerce-Churn-Analysis.git](https://github.com/your-username/E-Commerce-Churn-Analysis.git)
    ```

2.  Install the required dependencies:
    ```bash
    pip install -r requirements.txt
    ```

3.  Run the Jupyter Notebook:
    ```bash
    jupyter notebook
    ```
