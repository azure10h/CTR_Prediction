# Predicting Click-Through Rate (CTR) of an Ad

This project is a comprehensive exploration of predicting the click-through rate (CTR) of advertisements using machine learning techniques. The focus is on predicting whether user has made purchases given the advertisement. This project involves data preprocessing, feature engineering, model development, and performance optimization.

---

## Table of Contents

1. [Project Overview](#1-project-overview)
2. [Data Exploratory Analysis](#2-data-exploratory-analysis)
2. [Objective and Challenges](#objective-and-challenges)
3. [Key Contributions](#key-contributions)
4. [Data Analysis and Insights](#data-analysis-and-insights)
5. [Feature Engineering](#feature-engineering)
6. [Modeling Approach](#modeling-approach)
7. [Performance Evaluation](#performance-evaluation)
8. [Takeaways and Improvements](#takeaways-and-improvements)
9. [Project Files](#project-files)

---

## 1. Project Overview

Predicting CTR is a crucial task in online advertising to optimize campaign strategies and maximize user engagement. This project involves:
- Analyzing historical advertisement data.
- Developing and training machine learning models.
- Evaluating performance to ensure robust predictions.

The project demonstrates my ability to handle end-to-end machine learning tasks, from raw data preprocessing to model evaluation and insights extraction.

---
## 2. Data Exploratory Analysis
There are 27 data fields and around 480 thousand records in the data. Below shows the data dictionary for each data field. is_trade is the target variable, indicating whether trade happened or not.

| Field                        | Type    | Description                                                                                  |
|------------------------------|---------|----------------------------------------------------------------------------------------------|
| instance_id                  | long    | Transaction record                                                                          |
| item_id                      | long    | Advertisement product ID                                                                    |
| item_category_list           | string  | List of product categories, arranged from root (coarse) to leaf (fine), separated by semicolons |
| item_property_list           | string  | List of product properties, parallel relationships, separated by semicolons                 |
| item_brand_id                | long    | Advertisement product brand ID                                                              |
| item_city_id                 | long    | Advertisement product city ID                                                               |
| item_price_level             | int     | Product price level, starting from 0; higher values indicate higher prices                  |
| item_sales_level             | int     | Product sales level, starting from 0; higher values indicate higher sales                   |
| item_collected_level         | int     | Product collection times level, starting from 0; higher values indicate more collections    |
| item_pv_level                | int     | Product display times level, starting from 0; higher values indicate more displays          |
| user_id                      | long    | User ID                                                                                     |
| user_gender_id               | int     | Predicted gender: 0 for female, 1 for male, 2 for family users                              |
| user_age_level               | int     | Predicted age level; higher values indicate older age                                       |
| user_occupation_id           | int     | Predicted occupation ID                                                                     |
| user_star_level              | int     | User star level ID; higher values indicate higher levels                                    |
| context_id                   | long    | Context information ID                                                                      |
| context_timestamp            | long    | Product display time in seconds (timestamp)                                                 |
| context_page_id              | int     | Product display page ID, starting from 1; 1 represents the first screen                     |
| predict_category_property    | string  | Predicted category and properties list based on query term                                  |
| shop_id                      | long    | Shop information ID                                                                         |
| shop_review_num_level        | int     | Shop review number level, starting from 0; higher values indicate more reviews              |
| shop_review_positive_rate    | double  | Shop positive review rate; higher values indicate better reviews                            |
| shop_star_level              | int     | Shop star level ID; higher values indicate higher levels                                    |
| shop_score_service           | double  | Shop service attitude score; higher values indicate better scores                           |
| shop_score_delivery          | double  | Shop logistics service score; higher values indicate better scores                          |
| shop_score_description       | double  | Shop description match score; higher



## Objective and Challenges

### Objective:
To predict whether a user will click on a specific advertisement based on user, ad, and contextual features.

### Challenges:
1. Handling high-cardinality categorical features like item IDs and user IDs.
2. Managing imbalanced data, as clicks are typically rare events.
3. Ensuring interpretability of the model's predictions for actionable insights.
4. Identifying and mitigating overfitting during model training.

---

## Key Contributions

1. Designed a **pipeline** for data preprocessing, including handling missing values, encoding categorical features, and feature scaling.
2. Conducted **exploratory data analysis (EDA)** to identify key patterns and correlations.
3. Engineered new features to improve predictive power, such as interaction terms and statistical aggregations.
4. Built a **gradient boosting model (XGBoost)** optimized with hyperparameter tuning.
5. Visualized feature importance to enhance model interpretability and guide future feature engineering.

---

## Data Analysis and Insights

1. **Dataset Overview**:
   - Features include ad-specific details (e.g., price, sales level), user demographics (e.g., gender, age), and contextual information (e.g., page ID, timestamp).
   - Target variable: Binary label indicating whether the ad was clicked.

2. **Insights from EDA**:
   - High correlation between ad price level and click probability.
   - User star level influences engagement, indicating potential targeting opportunities.
   - Temporal patterns in user behavior, such as higher clicks during specific hours.

3. **Visualizations**:
   - Included heatmaps for feature correlation.
   - Distribution plots to highlight data imbalances.

---

## Feature Engineering

### Key Steps:
1. **Categorical Encoding**:
   - One-hot encoding for low-cardinality features.
   - Frequency encoding for high-cardinality features like item IDs.

2. **Numerical Transformations**:
   - Scaling features like price and sales levels for consistent model inputs.

3. **Derived Features**:
   - Interaction features combining user and ad attributes.
   - Aggregated statistics (e.g., average clicks by user group).

4. **Temporal Features**:
   - Extracted date and time information from timestamps to capture user behavior over time.

---

## Modeling Approach

### Chosen Model:
- **XGBoost**: Selected for its efficiency and ability to handle feature importance.

### Process:
1. Split data into training and testing sets to evaluate generalization performance.
2. Optimized hyperparameters (e.g., learning rate, max depth) using grid search.
3. Used early stopping to prevent overfitting.

### Model Insights:
- Visualized feature importance to identify critical factors driving CTR.
- Top features included user star level, ad price level, and temporal patterns.

---

## Performance Evaluation

### Metrics:
- **AUC (Area Under the Curve)**: Assesses classification performance.
- **Log-Loss**: Measures prediction accuracy for probabilistic models.

### Results:
- Achieved an AUC score of **[your AUC score]**, demonstrating strong predictive capability.
- Feature importance analysis highlighted actionable insights for improving ad targeting.

---

## Takeaways and Improvements

### Key Learnings:
1. Importance of feature engineering in boosting model performance.
2. Challenges of handling high-cardinality and imbalanced datasets.

### Future Improvements:
1. Explore deep learning models like neural networks for potentially better performance on large datasets.
2. Implement real-time prediction capabilities for online ad platforms.

---

## Project Files

