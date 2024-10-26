WiDS Datathon 2024 Challenge #2 - Regression of Metastatic Diagnosis Period
# Introduction
This project presents an exploratory data analysis (EDA) and regression modeling approach for the WiDS Datathon 2024 Challenge. The objective was to predict the metastatic diagnosis period based on various patient demographic and socio-economic characteristics. The analysis highlights the steps taken to clean, preprocess, and model the data, while optimizing feature selection and modeling parameters to improve predictive performance.

# Data Exploration
EDA was conducted to inspect initial data distributions, identify key variables, and examine relationships between features. This includes:

- Initial data inspection and analysis of categorical/numerical variables
- Mutual information and pairwise correlation to assess feature relevance
- Investigation of inconsistencies and missing values
  
# Data Cleaning and Imputation
To handle missing values, several imputation strategies were applied, including standard and group-based methods. Grouped imputations, such as mean and mode imputation by patient demographics, helped retain feature relationships while filling gaps in the dataset. Various imputation techniques were tested to identify the most effective approach based on model performance.

# Feature Engineering
Additional features were created based on domain knowledge to enhance model prediction. New features were generated by grouping variables such as bmi and density into clusters, resulting in improved feature representation. Prior to imputation, redundant and noisy features were removed, facilitating the identification of the most effective imputation methods.

# Modelling Approach
Several regression models were evaluated, with key models fine-tuned using cross-validation and hyperparameter optimization. Steps included:

- Establishing baseline scores and SHAP values for feature importance
- Conducting backward feature selection for optimal feature sets
- Fine-tuning model parameters
- Implementing a stacking meta-model approach with ensemble techniques
  
Results
The modeling results highlighted the effectiveness of using CatBoost with tailored imputation techniques and StratifiedKFold validation. 
Group-based imputations combined with specific models yielded the best performance. Notably, CatBoost, with Constant Categorical imputation for categorical features and KNN for numerical features, produced the lowest RMSE scores. Additionally, the use of 9-fold StratifiedKFold, grouped by breast_cancer_diagnosis_desc, enhanced the model’s ability to capture categorical group structures, resulting in the best public and private RMSE scores. 
Feature selection based on SHAP values further improved modeling performance, helping CatBoost identify the most predictive variables.
Detailed RMSE scores for each model and imputation combination are presented in the table within the notebook, with GradientBoosting also showing promising results using group-based imputation strategies.

Conclusion
This study underscores the significance of selecting appropriate imputation techniques and modeling approaches for predicting metastatic diagnosis periods. The combination of standard and group-based imputations was particularly effective for handling datasets with diverse missing value patterns. CatBoost emerged as the top-performing model, particularly due to its compatibility with categorical data and its ability to work well with features selected through SHAP values. By capturing meaningful relationships within the data, especially for tree-based models, the findings demonstrate that structured feature selection and stratified grouping improve predictive accuracy in healthcare-related regression tasks.
