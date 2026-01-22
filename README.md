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

### Conclusion and Recommendation

After going through a comprehensive *Data Science* workflow—ranging from data cleaning and handling *data leakage* to model optimization—we have reached the final stage to draw strategic conclusions. This section summarizes the technical performance of the model, its potential business impact, and actionable recommendations for the company.

#### Project Conclusion (Technical Summary)

Based on the evaluation results on the *Test Set*, the project concludes the following:

1.  **Best Model:** The **K-Nearest Neighbors (KNN)** algorithm was selected as the best-performing model after undergoing *Hyperparameter Tuning* and *Benchmarking*.
2.  **Metric Performance (Recall):**
    * The model achieved a **Recall score of ~91%** on the Churn class.
    * **Interpretation:** The model is capable of detecting approximately **9 out of 10 customers** who are actually at risk of churning.
    * The *False Negative* rate (missed detection) is very low, which is the primary priority in *Churn Prediction* cases.

#### Business Impact Analysis

What is the economic value of this model for the company? Let's perform a simple simulation.

**Business Assumptions:**
* **Customer Acquisition Cost (CAC):** $50 (Marketing/ad cost to replace 1 lost customer).
* **Retention Cost:** $10 (Discount vouchers/promos to retain customers identified as potential Churn).
* **Total Customers:** 10,000 users.
* **Churn Rate:** 16.8% (approximately 1,680 customers at risk of churn).

**Scenario 1: Without Model (Reactive)**
The company does not know who will leave. All 1,680 churned customers are lost and must be replaced by new customers.
* Total Loss Cost = 1,680 x $50 (CAC) = **$84,000**

**Scenario 2: With Machine Learning Model (Proactive)**
The model detects 91% of potential churners (Recall 91%).
* Detected Customers: 91% x 1,680 = 1,529 customers.
* Retention Cost: 1,529 x $10 = $15,290.
* Remaining Undetected Churners (Lost): 151 customers x $50 = $7,550.
* **Total Cost:** $15,290 + $7,550 = **$22,840**

**POTENTIAL SAVINGS:**
$84,000 - $22,840 = **$61,160 (Saving ~73% of Churn Costs)**

> *Conclusion: Implementing this model has the potential to save the company's budget significantly by shifting the marketing strategy to be more targeted and efficient.*

#### Business Conclusion (Strategic Recommendations)

Based on the results of *Exploratory Data Analysis (EDA)* and patterns learned by the model, here are strategic recommendations to reduce the Churn Rate:

1.  **Focus on the "Golden Period" (Early Months)**
    * *Insight:* Data shows the highest churn risk occurs at low **Tenure** (new customers).
    * *Action:* Create a special **Onboarding Program** for the first 3 months. Provide intensive application usage guides and *gamification* to increase *engagement* in the early subscription period.

2.  **Improve Complaint Mechanism**
    * *Insight:* Customers who have filed a **Complain** have a very high tendency to churn.
    * *Action:* Form a priority *Task Force* to handle complaints. Every incoming complaint must be resolved within <24 hours with small compensation (e.g., points/discounts) as an apology (implementing the "Service Recovery Paradox").

3.  **Optimize Mobile App User Experience**
    * *Insight:* Users who *Uninstall* or rarely open the application are detected as strong churn signals.
    * *Action:* Use personalized **Push Notifications** (avoiding spam) to remind users who have been inactive for >7 days, offering exclusive *App-Only* promotions.

### 7.4 Model Implementation

To enable this model to be used by the IT team or integrated into a business dashboard, we will save the final model into a ready-to-use file format (`pickle`).
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
