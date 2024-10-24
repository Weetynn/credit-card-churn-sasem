# Predictive Analytics in Credit Card Churn: Model Comparison and Strategic Insights

## 📚 Introduction 

This study addresses the pressing issue of customer churn in credit card services within the banking sector, where retaining existing customers is more cost-effective than acquiring new ones. The main objective is to develop a predictive model to identify customers likely to churn, providing actionable insights to help banks reduce attrition. Specifically, the study aims to identify the key factors driving churn and offer strategic recommendations to improve customer retention.

## 📋 Main Areas of Discussion

### 1.0 Problem Analysis

#### 📌 Problem Statements

    ▪️ Credit card customer churn is a growing issue for banks, where losing customers results in both direct revenue loss and reputational damage.
    
    ▪️ Retaining customers is five to seven times cheaper than acquiring new ones, according to industry studies (Kumar, 2022).
    
    ▪️ Customer churn signals potential problems in a bank’s processes, customer service, or competitive offerings, necessitating effective monitoring and prediction techniques to manage churn rates.
    

#### 📌 Objectives of the Study

    ▪️ Develop a predictive model using machine learning to forecast customer churn in the credit card domain.
    
    ▪️ Identify key factors contributing to customer churn.
    
    ▪️ Equip bank managers with actionable insights and recommendations for improving retention rates by predicting which customers are likely to churn and why.

  
#### 📌 Scope of the Study

    ▪️ Focuses on credit card churn within the banking sector.
    
    ▪️ The study uses a dataset of 16,998 records and 21 variables from Goyal (2021), containing customer demographic and transaction information.
    
    ▪️ Preprocessing steps include data sampling, undersampling to handle class imbalance, feature selection, and partitioning into training and validation sets.
    
    ▪️ The study limits its predictive modeling to tree-based models (Decision Tree, Extreme Gradient Boosting, High-Performance Tree, High-Performance Forest) and neural networks.
    

#### 📌 Methodology of the Study

Adopts the CRISP-DM framework (Cross-Industry Standard Process for Data Mining), focusing on five phases:

    ▪️ Business Understanding: Identifying the problem of customer churn and setting objectives for predictive analytics.
    
    ▪️ Data Understanding: Performing exploratory data analysis (EDA) using SAS Enterprise Miner’s StatExplore and MultiPlot tools to detect missing values, variable distributions, and relationships.
    
    ▪️ Data Preparation: Includes handling skewed distributions through logarithmic transformation, feature selection based on variable worth, and undersampling to balance the class distribution of churned vs. non-churned customers.
    
    ▪️ Modeling: Implemented five tree-based models (e.g., Decision Tree, Extreme Gradient Boosting, High-Performance Forest) and five neural network models with varying hyperparameters and architecture, tested with SAS Enterprise Miner.
    
    ▪️ Evaluation: Models are evaluated using metrics such as F1 score, precision, recall, specificity, sensitivity, misclassification rate, and ROC/AUC curve analysis.

---

### 2.0 Solution Development

#### 📌 Data Pipeline in SAS Enterprise Miner

![Screenshot 2024-10-24 141242](https://github.com/user-attachments/assets/35bfb374-51c0-4ae2-8287-679fa97e878f)

    ▪️ The workflow begins with importing the dataset into SAS Enterprise Miner, followed by exploratory data analysis (EDA), data preprocessing, model building, and comparison.
    
    ▪️ The data pipeline includes several key steps: data transformation, undersampling, and data partitioning into training and validation sets before modeling and evaluation.


#### 📌 Metadata of Dataset

![Screenshot 2024-10-24 141540](https://github.com/user-attachments/assets/d837e206-0aba-4244-8f45-689c9b8016bc)

    ▪️ The dataset consists of 16,998 records and 21 variables, including 1 ID variable, 19 input variables, and 1 binary target variable (Attrition Flag).
    
    ▪️ Input variables cover customer demographics, transaction history, and banking relationships (e.g., Total Transaction Count, Credit Limit, Total Revolving Balance).
    
    ▪️ A detailed breakdown of the variables (nominal, ordinal, interval) is provided, ensuring a comprehensive understanding of the dataset's structure.






