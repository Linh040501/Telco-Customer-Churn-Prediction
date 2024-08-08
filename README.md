# Telco Customer Churn Prediction

This project utilizes machine learning techniques and the R programming language to predict customer churn for Telco, a telecommunications company. The goal is to identify and analyze key variables influencing customer churn and to provide actionable insights for enhancing customer retention strategies.

### Research Question

How can we effectively predict customer churn by identifying and analyzing critical variables within the dataset? Additionally, how can this knowledge be leveraged to assist Telco in modifying strategies to improve customer loyalty, retain valuable clients, and reduce churn rates?

### Objectives

1. **Predict Customer Churn:** Employ various machine learning algorithms, including logistic regression, decision trees, and random forests, to forecast the likelihood of customer churn.
   
2. **Analyze Key Variables:** Examine the impact of customer demographics, account information, and service usage on churn rates.

3. **Provide Actionable Insights:** Offer recommendations to help Telco adjust strategies, enhance customer satisfaction, and lower churn rates.

### Key Components

- **Data Cleaning and Preprocessing:** Address missing values, encode categorical variables, and prepare the dataset for analysis.
  
- **Model Building:** Develop and evaluate predictive models to determine the most effective method for churn prediction.

- **Evaluation Metrics:** Use performance metrics such as AUC-ROC, confusion matrix, and model summaries to assess the accuracy and effectiveness of the models.

- **Visualization and Analysis:** Create visualizations to uncover churn patterns and service usage trends, providing a detailed view of factors affecting customer retention.

### Data Limitations

1. **Limited Sample Size:** The dataset comprises 7,011 observations. This relatively small sample size may result in overfitting, where the model performs well on training data but fails to generalize effectively to new, unseen data.

2. **Class Imbalance:** The dataset exhibits an imbalanced class distribution, with 73.4% of observations representing non-churn and 26.6% representing churn. This imbalance can lead to a bias in the prediction model, where the model might be inclined to predict the majority class more frequently, potentially compromising the accuracy and reliability of churn predictions.

When interpreting the results and applying the findings to real-world scenarios, these limitations should be considered.

## Packages Used in This Project

`tidyverse`, `dplyr`, `ggplot2`, `caret`, `pROC`, `lubridate`, `geosphere`, `gridExtra`, `RColorBrewer`



## Data Cleaning

### Inspecting the Dataset

The dataset contains 7043 rows and 20 columns. To gain an understanding of the categorical variables, we will check the unique values in each column.

**Descriptive Statistics for Numerical Columns**
- The average customer has stayed with the company for 32 months, with 75% of customers having a tenure of 55 months.
- The average monthly charges amount to USD 64.76, while 25% of customers pay more than USD 89.85.
- Based on Chebyshev’s Theorem and the Empirical Rules, no significant outliers are detected in the numerical variables.

**Inspect the Structure of the Data**
- Check the data structure to ensure all columns are correctly formatted.

**Check for Missing Values**
- Identify and quantify missing values in each column.

## Analysis Process

## Analysis Process

**Analysis of Churn Distribution**
- **Visualize the Distribution of the Churn Variable**: Create visualizations to illustrate the distribution of the Churn variable, which helps in understanding the balance between churned and non-churned customers.
- **Finding**: The dataset exhibits an imbalanced distribution of churn, with a higher proportion of non-churned customers compared to churned customers. This imbalance suggests that the prediction model may be biased toward the majority class.

