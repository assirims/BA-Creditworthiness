# Project: Creditworthiness

# Step 1: Business and Data Understanding

## 1. What decisions needs to be made?

 The decision that needs to be made is whether the new load applicants are creditworthy or not, and accordingly should they be granted a loan.

## 2. What data is needed to inform those decisions?
 Some data that is needed to inform such decisions include, annual income, credit score, age, account balance, and loan amount.

## 3. What kind of model (Continuous, Binary, Non-Binary, Time-Series) do we need to use to help make these decisions?

 A Binary Classification model should be used since predicting the results of new customers (as creditworthy or not) are based on available data.

# Step 2: Building the Training Set

- In your cleanup process, which fields did you remove or impute? Please justify why you

## removed or imputed these fields. Visualizations are encouraged.

## One variable was imputed and seven other variables were deleted, as follows:

- First, the Age-Years field was imputed, which is one of the data we depend on in our

## decisions, as only about 2% is missing. Therefore, as instructed, the average value was

```
used when null value is encountered.
```
- The deleted variables are due to missing data, such as:
    Ø Duration-in-Current-address (69% missing data).
- Or also variables were deleted due to valuelessness to our desired model as their values
    are distinct, such as:
       Ø Concurrent-Credits
       Ø Occupation
       Ø Guarantors
       Ø No-of-dependents
       Ø Foreign-Worker
- Finally, one variable was deleted as its irrelevant to our desired model, which is:
    Ø telephone


# Step 3: Train your Classification Models

```
Ø Logistic Regression: using the Stepwise tool, the selected predictor variables are Credit Amount,
Account Balance, Installment per cent, Purpose, Payment status of previous, and Length of current
employment. The accuracy of this model reaches 78% even though the R-squared value is under
0.1936. Finally, the model has a slight bias in predicting the statuses for some clients who are
creditworthy as non-creditworthy.
```
## Confusion matrix of Logistic Regression:

```
Ø Decision Tree: some of the important predictor variables include Account Blanca, Value Saving
Stocks, Duration of Credit Month, and Credit Amount. This model reaches an accuracy rate of
74.67% with false prediction for forty-nine creditworthy clients as non-creditworthy.
```

Confusion matrix of Decision Tree:

```
Ø Forest Model: some of the important variables include Credit Amount, Age Years, Duration of
Credit Month, and Account Balance. The model reaches an accuracy rate of 82% with slight
improvement in predicting non-creditworthy clients.
```

Confusion matrix of Forest Model:

```
Ø Boosted Model: some of the important predictor variables include Credit Amount, Account Balance,
and Duration of Credit Month (among others). The accuracy rate of this model reaches 79.33%
with no bias in prediction.
```

Confusion matrix of Boosted Model:

# Step 4 : Writeup

By comparing the four models using the Union tool, it can be concluded that the Forest model has the
highest rate of accuracy (i.e. 82%), and also the rates of creditworthy and non-creditworthy clients are
higher than other models in term of accuracy, which can be examined though the confusion matrix.

The most important reason is due to the shape of ROC curve where the ROC curve of the Forest model
has raised true positive rate and unchanged false positive rate. In contrast to the ROC curves of other
models, the ROC curve of Forest model remains its trend throughout.

Finally, by using the Score tool, the prediction of creditworthy clients is 408 while the other 92 clients
would be considered non-creditworthy, otherwise.



