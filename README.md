# Credit_Risk_Analysis
Objective:
The goal of this project is to predict whether a loan applicant will default on their loan based on several financial and demographic features.

Dataset Overview:
•	Total Entries: 255,347
•	Key Features: Age, Income, Loan Amount, Credit Score, Employment Type, Marital Status, Loan Purpose, Has Mortgage, Education, Loan Term, DTI Ratio, etc.
•	Target Variable: Default (0 = No Default, 1 = Default)

Exploratory Data Analysis (EDA) Insights:

1.Loan Purpose Distribution:
•	Most common loan purposes: "Other" and "Auto."
•	Visualization: Bar chart shows distribution across various loan purposes.

2.Income Trends by Age:
•	Higher income levels are observed in older age groups (40-60).
•	Default rates appear slightly higher in younger applicants (below 30).
•	Visualization: Line chart of income trends by age.

 3.Loan Default Rate:
•	No Default: 85.7%
•	Default: 14.3%
•	Visualization: Pie chart of loan default distribution.

4.Distribution of Loan Amount by Education:
•	Average loan amounts vary significantly across education levels.
•	Visualization: Box plot shows loan amount distribution by education level.

5.Distribution of Interest Rates by Employment Type:
•	Self-employed individuals face higher average interest rates compared to full-time employees.
•	Visualization: Violin plot shows interest rates distribution by employment type.

6.Density of Loan Amount by Loan Purpose:
•	Different loan purposes have distinct loan amount distributions.
•	Visualization: Density plot illustrates loan amounts for each loan purpose.

7.Loan Status by Marital Status:
•	Visualization reveals default rates by marital status.
•	Visualization: Stacked bar graph of loan status by marital status.

8. Distribution of Credit Scores:
•	Majority of applicants have credit scores between 600-700.
•	Visualization: Histogram shows the distribution of credit scores.

9.Count of Loan Applicants by Education Level:
•	Shows the number of applicants across different education levels.
•	Visualization: Count plot for education levels.

10.Loan Default Rates by Credit Score Range:
•	Default rates decrease with higher credit scores.
•	Visualization: Bar plot displays default rates by credit score range.

Feature Engineering:
•	Income-to-Loan Amount Ratio (ILR):
o	A new feature created by dividing an applicant’s income by the loan amount.
o	ILR has proven to be a significant feature in predicting defaults.

Model Building:
Logistic Regression Model:
•	Features: Age, Income, Loan Amount, Credit Score, Employment Type, ILR, etc.
•	Target: Default (binary classification)

Train-Test Split:
•	Train Data: 80% (204,277 records)
•	Test Data: 20% (51,070 records)

Model Performance (Before Optimization):
•	Accuracy: 87.3%
•	Recall (Defaulters): 56%
•	Precision (Defaulters): 69%
•	F1-Score (Defaulters): 62%

Model Evaluation:
1.	Confusion Matrix:
o	True Positives: 2,432
o	True Negatives: 43,617
o	False Positives: 6,211
o	False Negatives: 2,810

3.	Classification Report:
o	Precision (Defaulters): 69%
o	Recall (Defaulters): 56%
o	F1-Score (Defaulters): 62%

5.	ROC-AUC Score:
o	AUC: 0.82
o	Indicates a good balance between sensitivity and specificity.

Model Optimization:
Grid Search Hyperparameter Tuning:
•	Best Parameters:
o	C: 10
o	solver: liblinear
o	max_iter: 300

Final Model Performance (After Optimization):
•	Accuracy: 88.1%
•	Recall (Defaulters): 61%
•	Precision (Defaulters): 71%
•	F1-Score (Defaulters): 66%
•	AUC: 0.84

Key Insights:
1.	Income-to-Loan Ratio (ILR): Strong predictor of default. Lower ILR increases default probability.
2.	Credit Score: Defaulters typically have lower credit scores. A score below 600 shows a significant risk of default.
3.	Employment Type: Self-employed individuals tend to default more frequently due to higher interest rates and lower income stability.
4.	Default Rates: Approximately 14.3% of the applicants defaulted, indicating a manageable but significant risk for lenders.

Future Scope:
1.	Advanced Models: Exploring tree-based models like Random Forest, XGBoost, or Gradient Boosting can potentially improve accuracy and recall.
2.	Class Imbalance: Applying SMOTE or adjusting class weights can further improve recall for defaulters.
3.	Additional Features: Incorporating features like loan history or external financial behavior (if available) can enhance prediction accuracy.

Recommendations:
1.	Tighten Credit Policies: Applicants with ILR below 0.5 and credit scores below 600 should be carefully assessed or offered higher interest rates to mitigate risk.
2.	Focus on Younger Borrowers: Younger applicants, especially below 30, show a higher likelihood of default. Targeted strategies for this group are recommended.
3.	Monitor Self-Employed Borrowers: Implement stricter conditions or additional financial checks for self-employed borrowers due to higher default rates.

Conclusion:
In this project, we analysed the factors that affect loan defaults and built a model to predict them. Here are the main takeaways:

1.	Key Factors:
o	Age and Income: Older borrowers tend to have higher incomes and lower default rates.
o	Income-to-Loan Ratio (ILR): Borrowers with a low ILR are more likely to default. This means if someone’s income is much lower than their loan amount, they are at higher risk.
o	Credit Scores: Lower credit scores (below 600) are associated with higher default rates.

2.	Model Performance:
o	Our logistic regression model achieved an accuracy of 88.1% after optimization.
o	The model is better at identifying borrowers who are likely to default, with a recall rate of 61%.

3.	Recommendations:
o	Lenders should pay close attention to the ILR and credit scores when assessing loan applications.
o	Special care should be taken when lending to younger applicants and self-employed individuals, as they have higher default risks.

4.	Future Work:
o	There is room to improve the model further by trying advanced machine learning techniques and adding more data to make predictions even better.

Overall, this project helps lenders understand the risks of loan defaults better and suggests ways to make more informed lending decisions.
