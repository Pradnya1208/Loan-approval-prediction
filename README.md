<div align="center">
  
[1]: https://github.com/Pradnya1208
[2]: https://www.linkedin.com/in/pradnya-patil-b049161ba/
[3]: https://public.tableau.com/app/profile/pradnya.patil3254#!/
[4]: https://twitter.com/Pradnya1208


[![github](https://raw.githubusercontent.com/Pradnya1208/Telecom-Customer-Churn-prediction/c292abd3f9cc647a7edc0061193f1523e9c05e1f/icons/git.svg)][1]
[![linkedin](https://raw.githubusercontent.com/Pradnya1208/Telecom-Customer-Churn-prediction/9f5c4a255972275ced549ea6e34ef35019166944/icons/iconmonstr-linkedin-5.svg)][2]
[![tableau](https://raw.githubusercontent.com/Pradnya1208/Telecom-Customer-Churn-prediction/e257c5d6cf02f13072429935b0828525c601414f/icons/icons8-tableau-software%20(1).svg)][3]
[![twitter](https://raw.githubusercontent.com/Pradnya1208/Telecom-Customer-Churn-prediction/c9f9c5dc4e24eff0143b3056708d24650cbccdde/icons/iconmonstr-twitter-5.svg)][4]

</div>

# <div align="center">Loan Approval Prediction</div>
<div align="center">
<img src = "https://github.com/Pradnya1208/Loan-approval-prediction/blob/main/output/loan-approved.png?raw=true>
</div>


Loan Prediction ia a very common in real-life problem that each retail bank faces atleast once in its lifetime. I done Correctly, it can save a lot of man hours at the end of a retail bank.
## Objectives:
It is a classification Problem where we have to predict whether a loan would be approved or not.

## Hypothesis Generation:
#### Dependent Variables:
- **Salary**: Applicants with high income should have more chances of loan approval
- **Previous history**: Applicants who have repayed their previous debts should have higher chances of loan approval.
- **Loan amount**: Loan approval should also depend on the loan amount. If the loan amount is less, chances of loan approval should be high.
- **Loan term**: Loan for less time period and less amount should have higher chances of approval.
- **EMI**: Lesser the amount to be paid monthly to repay the loan, higher the chances of lean approval.


## Dataset:
[Loan Prediction](https://datahack.analyticsvidhya.com/contest/practice-problem-loan-prediction-iii/)

**Predict Loan Eligibility for Dream Housing Finance company**
Dream Housing Finance company deals in all kinds of home loans. They have presence across all urban, semi urban and rural areas. Customer first applies for home loan and after that company validates the customer eligibility for loan.

Company wants to automate the loan eligibility process (real time) based on customer detail provided while filling online application form. These details are Gender, Marital Status, Education, Number of Dependents, Income, Loan Amount, Credit History and others. To automate this process, they have provided a dataset to identify the customers segments that are eligible for loan amount so that they can specifically target these customers.

#### Data Fields:
![data](https://github.com/Pradnya1208/Loan-approval-prediction/blob/main/output/train.PNG?raw=true)

## Implementation:

**Libraries:** `sklearn` `Matplotlib` `pandas` `seaborn` `NumPy` 
## Understanding the data:
#### Loan approval status:
![Loan status](https://github.com/Pradnya1208/Loan-approval-prediction/blob/main/output/loan_status.PNG?raw=true)
#### Numerical Variables:
![Numerical](https://github.com/Pradnya1208/Loan-approval-prediction/blob/main/output/numerical.PNG?raw=true)


#### Categorical Variables:
![categorical](https://github.com/Pradnya1208/Loan-approval-prediction/blob/main/output/categorical.PNG?raw=true)

#### Ordinal Variables:
![ordinal](https://github.com/Pradnya1208/Loan-approval-prediction/blob/main/output/ordinal.PNG?raw=true)



### Misiing value imputation:
```
train["Gender"].fillna(train["Gender"].mode()[0], inplace=True)
train["Married"].fillna(train["Married"].mode()[0], inplace=True)
train["Dependents"].fillna(train["Dependents"].mode()[0], inplace=True)
train["Self_Employed"].fillna(train["Self_Employed"].mode()[0], inplace=True)
train["Credit_History"].fillna(train["Credit_History"].mode()[0], inplace=True)
```

![dist](https://github.com/Pradnya1208/Loan-approval-prediction/blob/main/output/dist.PNG?raw=true)
Due to the presence of Outliers bulk of data in the Loan amount is at the left and the tail at the right is longer i.e. the data has Right skewness. we can use Log tranformation to remove the skewness of the data, it does not affect the small values much but reduces the larger values.

```
# Log transformation
train["LoanAmount_log"] = np.log(train["LoanAmount"])
test_data["LoanAmount_log"] = np.log(test_data["LoanAmount"])
```
![transformed](https://github.com/Pradnya1208/Loan-approval-prediction/blob/main/output/transformed.PNG?raw=true)
