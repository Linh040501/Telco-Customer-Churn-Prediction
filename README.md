# Telco Customer Churn Prediction

This project utilizes machine learning techniques and the R programming language to predict customer churn for Telco, a telecommunications company. The primary objective is to identify and analyze key variables influencing customer churn and to provide actionable insights for enhancing customer retention strategies.

Logistic regression is employed for predicting customer churn, as it is specifically designed for binary outcomes (e.g., churn or no churn). This makes it a suitable choice for determining whether a customer will churn. However, to gain a comprehensive understanding, additional models such as linear regression and curvilinear regression will be explored.

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

![Count(churn)](https://github.com/user-attachments/assets/7b1c8c52-54a7-497c-a93b-cf8bc7751cca)

**Analysis of Services Each Customer Uses**
- **Finding**: By evaluating the service attributes, the following conclusions can be drawn:
  - Customers with phone service exhibit a moderately higher churn rate.
  - Customers with fiber optic internet service have a higher churn rate compared to those with DSL or no internet service.
  - The churn rate is significantly higher for customers without online security.
  - Customers lacking access to tech support tend to churn more frequently than those with tech support.
  - Customers without online backup and device protection also experience a higher churn rate.
![Analysis Services Each Customer](https://github.com/user-attachments/assets/226afaa0-a7d5-46e7-ade9-b49b621a072b)

**Analysis of Customer Account Information — Categorical Variables**
- **Finding**: The analysis of categorical variables in customer account information reveals:
  - Customers with month-to-month contracts are more likely to churn.
  - There is a moderately higher churn rate among customers using electronic checks as their payment method.
  - Customers with paperless billing exhibit higher churn rates.
![Analysis Customer Account Information — Numerical Variables](https://github.com/user-attachments/assets/30d89999-4a07-4314-a519-797969443c9d)

**Analysis of Customer Account Information — Numerical Variables**
- **Finding**: The analysis of numerical variables in customer account information reveals:
  - Customers with shorter tenure are more likely to churn.
  - Customers who incur higher monthly charges exhibit higher churn rates.
  - Customers with higher total charges also tend to churn more frequently.
![Analysis Customer Account Information — Numerical Variables](https://github.com/user-attachments/assets/d437b7a5-349b-4143-9de3-91580f5f17b4)

**Analysis of Customer's Demographic Information**
- **Finding**: The analysis of demographic information indicates:
  - There is no significant difference in churn rates between different genders.
  - Younger customers are more likely to churn compared to older customers.
  - Customers with a partner are less likely to churn compared to those without a partner.
![Analysis of Customer's Demographic Info](https://github.com/user-attachments/assets/66df2b10-5e57-4490-a53a-4fbad08b6664)

## Modeling

### Excel Linear Regression Model

- **First Model**: This model was developed using Microsoft Excel to perform linear regression analysis<img width="626" alt="Screen Shot 2024-08-08 at 16 15 21" src="https://github.com/user-attachments/assets/5b10bfe1-258d-40ef-911a-cf509f9f735d">
- **P-Value Analysis**: The p-values for some independent variables are greater than 0.05, suggesting that these variables may not have a significant effect on the outcome variable. It's crucial to consider the significance of predictors when selecting the best model. Variables with high p-values may be candidates for removal if they do not contribute meaningfully to the model's performance.
**Finding the Best Model**
<img width="598" alt="Screen Shot 2024-08-08 at 16 18 28" src="https://github.com/user-attachments/assets/7de9cbae-f0ab-4cab-8c20-fd330ffe5da2">
### Finding the Best Model

- **R-Squared and Adjusted R-Squared**: The R-squared value of 0.273 indicates that only 27.3% of the variance in the dependent variable is explained by the model. The adjusted R-squared has increased slightly from 0.271 to 0.272, suggesting that this model is a better fit compared to previous iterations.
- **F-Test and T-Test**: Both the F-test and T-test results support the model's validity. All p-values are less than 0.05, indicating that the predictors are statistically significant at the 95% confidence level.


### R Cullinear Regression Model
<img width="261" alt="Screen Shot 2024-08-08 at 13 29 59" src="https://github.com/user-attachments/assets/8cb1f8d4-63ff-46ad-bca5-76766ca2390c">
<img width="475" alt="Screen Shot 2024-08-08 at 13 35 41" src="https://github.com/user-attachments/assets/b14d1822-ce97-4f67-9833-fc00bf99d2e1">

- **Curvilinear Regression Model**: The R-squared value is approximately 0.29, and the adjusted R-squared is slightly higher, around 0.30. This indicates that the model explains only about 29% of the variability in the outcome variable.
### Logistic Regression Model

- **Coefficients**: The coefficients of the logistic regression model provide insight
<img width="723" alt="Screen Shot 2024-08-13 at 16 02 14" src="https://github.com/user-attachments/assets/f2bf055a-eebf-481b-964a-35ec02ba7436">

## Logistic Regression Model Results

### Significant Predictors

- **Tenure**: Negative estimate (-0.1466), indicating that as tenure increases, the likelihood of churn decreases. The p-value is very small (<<0.05), making it highly significant.

- **Tenure Squared**: Positive estimate (0.0036), showing a non-linear effect of tenure on churn. The p-value is very small (<<0.05), making it highly significant.

- **Tenure Cubed**: Negative estimate (-0.00003), indicating a cubic effect of tenure on churn. The p-value is very small (<<0.05), making it highly significant.

- **Monthly Charges**: Positive estimate (0.0916), meaning higher monthly charges are associated with higher churn. The p-value is small (<0.05), making it significant.

- **Senior Citizen**: Positive estimate (0.2312), indicating that senior citizens are more likely to churn. The p-value is small (<0.01), making it significant.

- **Phone Service**: Negative estimate (-1.334), showing that customers with phone service are less likely to churn. The p-value is very small (<<0.05), making it highly significant.

- **Paperless Billing**: Positive estimate (0.3599), indicating that customers with paperless billing are more likely to churn. The p-value is very small (<<0.05), making it highly significant.

- **Online Security (Yes)**: Negative estimate (-0.5749), showing that customers with online security are less likely to churn. The p-value is very small (<<0.05), making it highly significant.

- **Online Backup (Yes)**: Negative estimate (-0.3753), indicating that having online backup is associated with lower churn. The p-value is small (<0.01), making it significant.

- **Tech Support (Yes)**: Negative estimate (-0.5485), showing that customers with tech support are less likely to churn. The p-value is very small (<<0.05), making it highly significant.

- **Contract (One Year)**: Negative estimate (-0.7153), indicating that a one-year contract is associated with reduced churn. The p-value is very small (<<0.05), making it highly significant.

- **Contract (Two Years)**: Negative estimate (-1.5143), showing that a two-year contract is even more associated with reduced churn. The p-value is very small (<<0.01), making it very significant.

- **Payment Method (Electronic Check)**: Positive estimate (0.2587), indicating that paying via electronic check is associated with higher churn. The p-value is small (<0.01), making it significant.

### Non-Significant Predictors

- **Gender, Partner, Dependents, etc.**: These predictors have p-values > 0.05, indicating they are not significant in predicting churn in this model.

- **McFadden's R-squared: 0.295**:This indicates that the model explains about 29.5% of the variability in the data, which is a reasonable fit for a logistic regression model.

<img width="238" alt="Screen Shot 2024-08-13 at 16 19 52" src="https://github.com/user-attachments/assets/b86c93b5-0408-4ceb-93db-9ff3d3b6ab58">


- **ROC Curve**

  ![Rplot](https://github.com/user-attachments/assets/fec91023-19fd-4586-96d6-a0abd51c4d4b)


- **AUC (Area Under the Curve)**: An AUC of 0.85 indicates that the model has a high level of discrimination. Specifically, there is an 85% chance that the model will correctly rank a randomly chosen churn case higher than a randomly chosen non-churn case.

- **Threshold**:A threshold of 0.28 means that if the model predicts a probability of 0.28 or higher for a customer, that customer is classified as "Churn" (i.e., predicted to churn). If the predicted probability is below 0.28, the customer is classified as "No Churn"

These my due to The dataset exhibits an imbalanced class distribution, with 73.4% of observations representing non-churn and 26.6% representing churn

- **Model Accuracy**: The model accuracy is 0.8259, indicating that approximately 82.59% of the predictions made by the logistic regression model are correct. This metric provides a general measure of how well the model is performing in classifying instances correctly.

<img width="369" alt="Screen Shot 2024-08-13 at 17 06 56" src="https://github.com/user-attachments/assets/c749c0db-848c-41fd-97e0-4fdc7abdeadf">
