%%writefile README.md
## Problem Set 2 
Bank Marketing Prediction

## Approach
The goal of this project was to develop a predictive model to determine if a banking customer would subscribe to a term deposit based on their demographic and behavioral data. The project followed a standard data science pipeline: data loading, exploratory analysis, categorical encoding, feature scaling, and binary classification using Logistic Regression.

## Methodology
- Data Preprocessing: The target variable 'y' was mapped to binary values (1 for 'yes', 0 for 'no'). Categorical features such as 'job', 'education', and 'contact' were transformed using One-Hot Encoding to expand them into machine-readable numerical formats.
- Data Splitting: The dataset was split into an 80% training set and a 20% testing set to ensure unbiased evaluation.
- Feature Scaling: Since Logistic Regression is sensitive to the magnitude of input variables, `StandardScaler` was applied to normalize all features to a mean of 0 and a standard deviation of 1.
- Model Training: A Logistic Regression model was trained using the Scikit-learn library, with the maximum iterations increased to 1000 to ensure the solver reached convergence.
- Evaluation: The model performance was assessed using a Confusion Matrix, Accuracy Score, and a detailed Classification Report (Precision, Recall, and F1-Score).

## Findings
Overall Accuracy: The model achieved an accuracy of approximately 89.88%, indicating strong predictive power for the majority of cases.
- Confusion Matrix:
    - True Negatives (Correctly predicted 'no'): 7755
    - True Positives (Correctly predicted 'yes'): 373
    - False Positives: 197
    - False Negatives: 718
- Class Performance:
    - The model is highly effective at identifying customers who will not subscribe (Recall for '0' = 0.98).
    - The recall for the 'yes' class (0.34) suggests that the model is conservative in its predictions, likely due to the inherent class imbalance in the banking dataset where 'no' responses significantly outnumber 'yes' responses.
- Conclusion: The Logistic Regression model provides a reliable baseline for the bank to filter out unlikely subscribers, though further tuning or class-weight adjustments could be explored to improve the detection of potential subscribers.