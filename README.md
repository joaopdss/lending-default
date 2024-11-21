# Not a Black Box: How Explainable Machine Learning Transforms Lending and Saves Millions
## Using AI to Reduce Risk, Save Millions, and Build Trust in Lending
[img]

Loan defaults result in millions of dollars in losses for banks every year, a figure that continues to grow as purchasing power declines in various parts of the world. To more accurately predict when an individual is likely to default on a loan, financial institutions increasingly turn to machine learning models. These models aim to classify whether a person will repay the loan, either before it is approved or during the repayment period.

However, many lending institutions rely on black-box models, which, while highly predictive, are difficult to interpret. This lack of interpretability creates challenges, as institutions cannot easily explain why a loan was approved or denied. Trust is a cornerstone of this sector, and regulations in places like the US and Europe require lending institutions to ensure their decisions are explainable, fair, and non-discriminatory. This makes black-box models problematic in many scenarios.

## Our Approach: Explainable Machine Learning
To address these challenges, we developed an XGBoost model—a popular but inherently black-box algorithm. By applying SHAP (SHapley Additive Explanations), we made the model interpretable while maintaining its predictive power. This approach strikes a balance between accuracy and transparency, enabling lending institutions to explain their decisions and build trust with customers and regulators.

## Interpretability in Action
We used SHAP to identify the top contributing variables for each prediction, providing insights into why the model classified loans as charged off (defaulted) or fully paid. Below are two examples:

### Example 1: Customer Who Defaulted
Key Features:
- Loan Grade: Received the worst possible grade, indicating high risk.
- Loan Term: Had the maximum repayment period of 60 months.
  
SHAP Insights:
- Features with red bars indicate positive contributions toward predicting the loan as "charged off" (higher risk of default).
- Features with blue bars indicate negative contributions that reduce the risk of default.

[img]

### Example 2: Customer Who Fully Repaid
Key Features:
- FICO Credit Score: High score indicating strong creditworthiness.
- Loan Grade: Received the best possible loan grade, signifying low risk.

[img]

## Addressing Class Imbalance and Improving the Model
One major challenge was the class imbalance in the dataset. Defaults were approximately five times less frequent than fully paid loans, making the model biased toward predicting the majority class.

To mitigate this, we implemented the following techniques:

1. SMOTE (Synthetic Minority Over-sampling Technique):
- Used to upsample the minority class (defaults) by generating synthetic examples, helping the model learn patterns associated with defaults more effectively.

2. Class Weights:
- Adjusted the class weights to emphasize the minority class. Misclassifying defaults was penalized more heavily than misclassifying fully paid loans.

### Model Performance After Improvements:
- Recall for Defaults: Increased threefold, reaching 28% compared to the initial results. While still modest, this was a significant improvement given the dataset limitations.
- F1 Score: Improved by 20%, achieving a better balance between precision and recall.

## Quantifying the Model's Impact
Our model, trained on the Lending Club dataset, achieved:

- 28% Recall for Defaults: Identifying over a quarter of individuals who would default on their loans before approval.
- 90% Recall for Fully Paid Loans: Correctly identifying the majority of customers who fully repaid their loans.

### Business Implications:
Even with limited data, these results could help financial institutions:

- Mitigate Risks: By identifying higher-risk customers, institutions can adjust interest rates or require additional collateral.
- Save Millions Annually: Small improvements in risk prediction can lead to substantial cost savings over time.

## Conclusion
By combining machine learning with interpretability, we demonstrated how financial institutions can improve their decision-making processes while building trust and meeting regulatory requirements. Our project highlights the importance of addressing challenges like class imbalance and the value of tools like SHAP in making complex models transparent.
