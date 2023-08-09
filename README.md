# credit-risk-classification

<h2> Overview of the Analysis</h2>

The purpose of the analysis is to use various techniques to train and evaluate a model based on loan risk. Also, use mashine learning to analyze a dataset of historical lending activity from a peer-to-peer lending services company to build a model that can identify the creditworthiness of borrowers.

* The dataset contained features such as loan size, interest rate, borrower income, debt to income ratio, number of account the borrower posseses, a count of derogatory remarks, as well as their total debt while the loan status formed the label.



```
# dataset
df.head()

     loan_size  interest_rate   borrower_income   debt_to_income  num_of_accounts  derogatory_marks  total_debt  loan_status

0    10700.0	    7.672	     52800	       0.431818		5		 1		22800	      0

1    8400.0	    6.692	     43600	       0.311927		3		 0		13600	      0

2    9000.0	    6.963	     46100	       0.349241		3		 0		16100	      0

3    10700.0	    7.664	     52700	       0.430740		5		 1		22700	      0

4    10800.0	    7.698	     53000	       0.433962		5		 1		23000	      0
```


* Using mashine learning, the objective is to predict the status of the loan, either as a Healthy Loan (0) or a High-Risk Loan (1).
* The Logistic Regression Algorithm is the best tool to use for our machine learning model since it is widely used to predict the probability of a target variable in classification problems.


```
# code
y.value_counts()

# output
0    75036
1     2500
Name: loan_status, dtype: int64
```

#### Stages of the machine learning process:

1) Data Split:

   - The dataset was split into training and testing sets to evaluate the model's performance.
   - The dataset was split into training and testing sets to evaluate the model's performance.
3) Model Training:

   - Initialize `Logistic Regression Model`. The first logistic regression model was constructed using the original dataset, which consisted of 75,036 data points classified as low risk and 2,500 data points classified as high risk. The objective of this model was to predict the classification (low risk or high risk) of loans given to borrowers in the testing set.
   - Used the training data to fit the model to the data.

   * During training, the algorithm adjusts the model's weights to minimize the logistic loss between the predicted probabilities and the actual binary labels.
4) Resampling with `RandomOverSampler`:
   - To tackle the issue of class imbalance, the training data underwent resampling using the RandomOverSampler technique. This approach ensured an equal representation of both low-risk and high-risk labels by increasing the number of high-risk data points. As a result, both classes consisted of 56,277 data points each after the resampling process.
6) `Logistic Regression Model` with Resampled Data:
   - A logistic regression model was constructed using the resampled data. The objective of this model was to predict loan risk based on the training data that underwent the resampling process.
8) Model Evaluation:

   * Used the validation set to evaluate the model's performance using appropriate metrics such as accuracy, precision, recall, and F1-score.

The objective of these steps was to evaluate and compare the performance of two logistic regression models. The first model was trained on the original data, while the second model was trained on the resampled data. By conducting this comparison, the effectiveness of resampling in addressing class imbalance and enhancing the model's predictive capabilities for loan risk classification could be assessed.

## Results

* Machine Learning Model 1:

  * For the `Healthy Loans (0)`, the precision is 1.00, indicating that all the predictions for this label were correct. The recall is 1.00, meaning that all instances of this label were correctly identified.
  * The precision for `High-Risk Loan (1)` is 0.87, indicating that 87% of the predictions for this label were accurate. The recall is 0.89, indicating that 89% of the instances of this label were correctly identified.
  * The overall accuracy of the model is 0.99, indicating that it correctly predicted the loan risk for 99% of the instances.
* Machine Learning Model 2:

  * The prescision is 87% and recall is at 89%,  which indicates a high rate of correct identification of high-risk loans with a small number of false positives.
  * The overall accuracy of the model is 0.99, indicating that it correctly predicted the loan risk for 99% of the instances.

## Summary

Upon analysis, it was observed that both models exhibited commendable accuracy, precision, and recall scores. However, the logistic regression model that utilized resampling showcased a slightly superior performance, achieving an accuracy score of 0.9945 compared to 0.9924 for the initial logistic regression model.

Considering the objective of accurately identifying both healthy loans and high-risk loans, the logistic regression model with resampling emerges as the optimal choice.
