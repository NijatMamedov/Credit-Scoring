# Credit-Scoring
Pre-Processing for Logistic Regression 
Let’s prepare the data before modeling — clean data = better results! 

 1. Import Libraries We load libraries like pandas, numpy, and sklearn for data handling and transformation. 

 2. Read Data We load the dataset and take a quick look at structure and values. 

 3. Descriptive Stats Basic stats like mean, min, max, and mode help us understand the data. 

 4. Handle Missing Values We check for missing values and replace them if needed (mean, mode, etc.). 

 5. Create Target Variable From the credit_score column:

If value is 'poor', set score = 1

Else, score = 0

This new score column is our binary target. 

 6. WoE Transformation We apply WoE to both numeric and categorical features. 

 7. Check Distributions We review if features are normally distributed. 

 8. Correlation Keep:

Features with >10% correlation with target

Features with <70% correlation between each other

 This helps reduce redundancy.

 9. Final Variables Choose inputs (independent variables) and output (score) for the model. Done! 



 Modeling the Logistic Regression Model 
Time to build, train, and evaluate the model! 

 1. Train-Test Split We split the data into training and testing sets using test_size=0.3. This helps evaluate performance on unseen data. 

 2. Build Logistic Regression Model We train a logistic regression model using the training data. Simple and effective! 

 3. Evaluation Function We create a function to compute:

Confusion matrix 

AUC score 

Gini coefficient 

 4. Model Evaluation We use our function to check how well the model performs using the test set. Key metrics: Gini, AUC, and confusion matrix. 

 5. ROC Curve We plot the ROC curve for visualizing model performance and Gini score. 

 6. Precision & Recall We plot precision vs. recall to find the best balance point — very helpful in binary classification. 



 Univariate Gini Analysis
For each variable, show the Gini score on both the train and test sets. This helps identify how well each feature performs individually. 



 Selected Variables for New Model
In the Univariate analysis, we keep variables with a Gini score above 40% from the test set and build a new model based on these selected features. 



 Deployment with WOE
Deploy the model on the provided prod_data_with_woe dataset! 


 Predict Default Probability (PD) Use model.predict_proba() to show the probability of customers defaulting (PD). This helps predict the likelihood of default. 


 Deployment with Real Values
We deploy the trained model using the provided file: test_data_real_values.xlsx 



 Predicting Default Probabilities (PD)
For each customer in the test data, we calculate their probability of default (PD) using the model. 

This gives a clear view of risk levels for real-world cases! 
