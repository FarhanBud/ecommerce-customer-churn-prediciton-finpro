# E-Commerce Customer Churn Analysis and Prediction

## Final Project - Data Science & Machine Learning - Purwadhika Digital School

Group Beta 
- Muhamad Farhan Budiana
- Muhammad Ghifari
- Shadrina Putri Nabila

## Project Overview

Customer churn represents a significant business challenge in the e-commerce industry due to its direct impact on revenue stability, customer lifetime value, and marketing efficiency. Understanding why customers discontinue transactions is essential for designing effective retention strategies and sustaining long-term growth.

This project analyzes historical e-commerce customer data to identify behavioral patterns and characteristics associated with churn. The analysis focuses on building a strong analytical foundation through data exploration, preprocessing, and metric alignment to support reliable churn prediction.

### 1. Business Problem Understanding
#### 1.1 Business Context

In a competitive e-commerce environment, customer retention plays a critical role in maintaining profitability. Acquiring new customers is substantially more expensive than retaining existing ones, making churn a high-impact business risk.

The company has observed a non-trivial portion of customers becoming inactive over time. Without a clear understanding of churn drivers, retention efforts risk being inefficient and poorly targeted.

#### 1.2 Problem Statement

The primary business problem is the lack of analytical insight into customer churn behavior. The company needs a structured, data-driven approach to:

- Understand the characteristics of churned customers

- Identify behavioral patterns that signal churn risk

- Support future predictive and retention-focused initiatives

#### 1.3 Goals

The objectives of this analysis are to:

- Explore customer behavior and transactional patterns related to churn

- Identify features that meaningfully differentiate churned and retained customers

- Prepare a clean, well-structured dataset suitable for predictive modeling

- Establish evaluation criteria aligned with business priorities

#### 1.4 Analytical Approach

The analysis follows a systematic data science workflow:

- Business problem formulation

- Data understanding and validation

- Exploratory data analysis (EDA)

- Data preparation and feature engineering

- Metric definition and evaluation alignment

This structured approach ensures analytical rigor, reproducibility, and relevance to real-world business decision-making.

#### 1.5 Evaluation Metrics

Customer churn data exhibits class imbalance, where churned customers represent a minority of observations. In this context, Recall is emphasized as the primary evaluation metric.

Recall measures the ability of a model to correctly identify churned customers. From a business perspective, failing to detect a churn-prone customer (false negative) represents a missed opportunity for proactive retention actions.

Other metrics such as Accuracy, Precision, and F1-Score are acknowledged as complementary indicators but are treated as secondary due to their limitations under imbalanced class conditions.

### 2. Data Understanding
#### 2.1 Unit of Analysis

Each row in the dataset represents an individual customer, including demographic attributes, transaction behavior, engagement indicators, and service-related information.

#### 2.2 Attribute Information

The target variable is Churn, a binary indicator reflecting whether a customer has stopped transacting within the observed period.

#### 2.3 Data Quality Assessment

Initial data inspection focuses on:

- Verifying data types and schema consistency

- Identifying missing or invalid values

- Assessing class distribution of the target variable

- Detecting potential anomalies

These checks ensure that the dataset is suitable for exploratory and preparatory analysis.

2.4 Descriptive Statistics

Descriptive statistics are used to summarize numerical features, providing insights into customer behavior patterns such as transaction frequency, tenure, and engagement intensity.

This step helps establish baseline understanding and informs subsequent analytical decisions.

### 3. Exploratory Data Analysis (EDA)

Exploratory analysis examines differences between churned and non-churned customers across multiple dimensions, including:

- Transaction activity and recency

- Customer engagement levels

- Satisfaction and complaint behavior

- Categorical segmentation variables

Visualization and comparative analysis are used to uncover meaningful patterns and potential churn indicators.

#### 3.1 Key Insights from EDA

The EDA reveals distinct behavioral differences between churned and retained customers, reinforcing the relevance of selected features for churn analysis. These findings provide empirical support for feature selection and downstream modeling decisions.

### 4. Data Preparation and Feature Engineering

Data preparation ensures consistency, prevents data leakage, and enables reliable model development.

Key steps include:

- Defining target (y) and feature set (X)

- Applying stratified train-test splitting to preserve churn distribution

- Building a preprocessing pipeline using ColumnTransformer

- Standardizing numerical features and encoding categorical variables

All transformations are applied through a unified pipeline to ensure reproducibility and consistent application across training and evaluation datasets.


Repository Structure
├── data/
│   └── ecommerce_churn_analysis_final.csv
├── notebooks/
│   └── finpro.ipynb
├── README.md

Tools and Technologies

1. Python
2. Pandas, NumPy
3. Matplotlib, Seaborn
4. Scikit-learn
5. Jupyter Notebook
