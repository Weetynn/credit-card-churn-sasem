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

    ▪️ The dataset consists of 16,998 records and 21 variables, including 1 ID variable, 19 input variables, and 1 binary target variable ("Attrition_Flag").
    
    ▪️ Input variables cover customer demographics, transaction history, and banking relationships (e.g., Total Transaction Count, Credit Limit, Total Revolving Balance).
    
    ▪️ A detailed breakdown of the variables (nominal, ordinal, interval) is provided, ensuring a comprehensive understanding of the dataset's structure.


#### 📌 Exploratory Data Analysis (EDA)

StatExplore was used to examine class and interval variables:

    ▪️ No missing values were found, and most variables follow a normal distribution except for five that showed skewness ("Avg_Open_To_Buy", "Credit_Limit", "Total_Amt_Chng_Q4_Q1", "Total_Ct_Chng_Q4_Q1", "Total_Trans_Amt").
    
    ▪️ Significant class imbalance was noted in the target variable, with 83.93% retained customers and 16.07% churned customers.


MultiPlot Analysis explored the relationship between variables and churn. Key findings include:

    ▪️ Customers with higher revolving balances and more frequent transactions tend to have lower churn rates.
    
    ▪️ Lower credit utilization and fewer transactions were linked to higher churn.


#### 📌 Data Preparation

Key steps included:

    ▪️ Logarithmic transformation of skewed variables to improve distribution.
    
    ▪️ Feature selection based on the variable worth diagram, removing eight variables with minimal predictive power ("Customer_Age", "Months_on_book", "Gender", "Income_Category", "Education_Level", "Dependent_count", "Marital_Status", "Card_Category").
    
    ▪️ Undersampling to balance the dataset, reducing the number of retained customers to match the number of churned customers (1,627 in each group).
    
    ▪️ Data partitioning with a 70-30 train-test split to prepare for model building.
    
    ▪️ Evaluation: Models are evaluated using metrics such as F1 score, precision, recall, specificity, sensitivity, misclassification rate, and ROC/AUC curve analysis.
    

#### 📌 Predictive Modeling

A total of 10 models were developed, including five tree-based models and five neural network models with specific parameter tuning.

#### Tree-Based Models:

    ▪️ A Decision Tree model was built using a significance level of 0.2, with a maximum branch of 2, maximum depth of 6, and a minimum leaf size of 5.
    
    ▪️ The first Gradient Boosting (Boost1) model was configured with 5 iterations, maximum branch of 2, maximum depth of 2, and a leaf fraction of 0.001.
    
    ▪️ The second Gradient Boosting (Boost2) model was optimized with 150 iterations, maximum branch of 4, maximum depth of 2, and a leaf fraction of 0.001. It achieved the best performance among the tree-based models.

    ▪️ The High-Performance Tree (HP Tree) was set up with a significance level of 0.2, maximum branch of 2, maximum depth of 10, and a minimum leaf size of 5.

    ▪️ The High-Performance Forest (HP Forest) model used 100 trees, a maximum depth of 50, a significance level of 0.05, and a leaf size of 5, with variable importance calculated using the Loss Reduction method.

#### Neural Network Models:

    ▪️ A Standard Neural Network model was created with an identity activation function, 1 hidden layer consisting of 3 hidden neurons, and ran for 300 iterations.

    ▪️ The first High-Performance Neural Network (HP Neural 1) model had 1 hidden layer, 3 hidden neurons, and ran for 300 iterations with an identity activation function.
    
    ▪️ The second High-Performance Neural Network (HP Neural 2) model was built with 6 hidden layers, each having 3 hidden neurons, and ran for 1000 iterations with 4 tries.
    
    ▪️ The third High-Performance Neural Network (HP Neural 3) model was more complex, utilizing 10 hidden layers, 3 hidden neurons, and ran for 1000 iterations with 15 tries.

    ▪️ The fourth High-Performance Neural Network (HP Neural 4) model had 10 hidden layers, 3 hidden neurons, and ran for 1000 iterations with 20 tries for further optimization.

#### Model Comparison:

    ▪️ The best-performing model among the tree-based models was Gradient Boosting (Boost2), with a low misclassification rate of 5.53% and high recall for identifying churned customers.
    
    ▪️ Among neural networks, the standard neural network model performed best, with a misclassification rate of 9.52% but was outperformed by Boost2 in terms of overall performance.


#### 📌  Model Interpretation 

Interpretation and Recommendations (Tree-Based Models):

    ▪️ The Gradient Boosting (Boost2) model was the best-performing tree-based model, with a low misclassification rate and minimal false negatives (27). It showed strong generalization, indicating no overfitting.
    
    ▪️ Key variables influencing churn included: "LOG_Total_Trans_Amt", "Total_Trans_Ct", "Total_Revolving_Bal", "LOG_Total_Ct_Chng_Q4_Q1", "LOG_Total_Amt_Chng_Q4_Q1"
    
    ▪️ Recommendations: Personalized rewards for high transaction customers, proactive support for declining transaction behavior, improved credit management, and relationship-building incentives.

Interpretation and Recommendations (Neural Network Models)
   
    ▪️ The Standard Neural Network model had a higher misclassification rate (0.0952) than Boost2, but it minimized false negatives (48) and generalized well.
    
    ▪️ The Neural Network model aligned with Boost2 on the top four churn predictors but differed on the fifth, prioritizing "Total_Relationship_Count" over "LOG_Total_Amt_Chng_Q4_Q1".
    
    ▪️ Recommendations: Similar to tree-based models, focusing on personalized rewards, proactive support, and enhancing customer relationships. 

---

### 3.0 Conclusion

#### 📌 Key Findings

    ▪️ The Gradient Boosting (Boost2) model performed the best among all models, with the lowest misclassification rate and a good balance between precision and recall.
    
    ▪️ Both tree-based models and neural networks identified the same top four factors influencing churn: "LOG_Total_Trans_Amt", "Total_Trans_Ct", "Total_Revolving_Bal", "LOG_Total_Ct_Chng_Q4_Q1"
    

#### 📌 Recommendations

    ▪️ Implement personalized rewards for customers with higher transaction volumes and counts to incentivize continued engagement.
    
    ▪️ Take proactive action for customers exhibiting changes in transaction behavior, potentially indicating a risk of churn.

    ▪️ Introduce credit management programs to help customers manage revolving balances and avoid excessive churn risks.
    
    ▪️ Focus on building stronger relationships with long-standing or frequent customers through tailored benefits and programs.
    

#### 📌 Areas for Future Study

Further research is recommended to investigate the differing results between models, particularly the fifth important variable:

    ▪️ Neural Networks identified "Total_Relationship_Count" as the fifth most important factor.
    
    ▪️ Tree-Based Models (Boost2) identified "LOG_Total_Amt_Chng_Q4_Q1" as the fifth most important factor.

    ▪️ This difference suggests further analysis is needed to understand the role each variable plays in predicting churn.


















