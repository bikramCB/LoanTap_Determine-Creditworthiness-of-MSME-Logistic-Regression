# LoanTap:Determine-Creditworthiness-of-MSME using Logistic-Regression

## Context
When applying for a bank loan, there is a lengthy process involving the submission of various documents 
and details such as a good credit score, a no dues certificate, and sometimes even a no crime certificate. 
However, not everyone is eligible for these loans and able to meet all the documentation requirements 
and profile evaluations.
Loan Tap, as a company, aims to provide loans to individuals and small-sized firms (MSMEs) who may 
not be able to fulfill all the necessary requirements. They specifically target high-risk profiles as their 
potential customers, but within this category, there are three sub-profiles that loan applicants can fall into.
The first category is the "White Collar" customers, who are considered high risk but are expected to 
repay their loans. The second category is the "Grey Collar" customers, who have a mixed likelihood of 
repaying the loan. Lastly, the "Black Collar" customers are those who are unlikely to be able to repay the 
loan.
Loan Tap focuses on the White Collar and Grey Collar customers only. However, they cannot approve 
loans for all Grey Collar customers. This is where data scientists come in. They are needed to properly 
profile the Grey Collar customers so that Loan Tap can have a balanced mix of high-risk and low-risk 
customers, allowing them to potentially make a profit even if a few customers default on their loans. 

## Problem Statement
LoanTap deploys formal credit to salaried individuals and businesses 4 main financial instruments:
Personal Loan
EMI Free Loan
Personal Overdraft
Advance Salary Loan
Given a set of attributes for an Individual, determine if a credit line should be extended to them. If so, what should the repayment terms be in business recommendations?

## Data :
loan_amnt : The listed amount of the loan applied for by the borrower. If at some point in time, the credit department reduces the loan amount, then it will be reflected in this value.
term : The number of payments on the loan. Values are in months and can be either 36 or 60.
int_rate : Interest Rate on the loan
installment : The monthly payment owed by the borrower if the loan originates.
grade : LoanTap assigned loan grade
sub_grade : LoanTap assigned loan subgrade
emp_title :The job title supplied by the Borrower when applying for the loan.*
emp_length : Employment length in years. Possible values are between 0 and 10 where 0 means less than one year and 10 means ten or more years.
home_ownership : The home ownership status provided by the borrower during registration or obtained from the credit report.
annual_inc : The self-reported annual income provided by the borrower during registration.
verification_status : Indicates if income was verified by LoanTap, not verified, or if the income source was verified
issue_d : The month which the loan was funded
loan_status : Current status of the loan - Target Variable
purpose : A category provided by the borrower for the loan request.
title : The loan title provided by the borrower
dti : A ratio calculated using the borrower’s total monthly debt payments on the total debt obligations, excluding mortgage and the requested LoanTap loan, divided by the borrower’s self-reported monthly income.
earliest_cr_line :The month the borrower's earliest reported credit line was opened
open_acc : The number of open credit lines in the borrower's credit file.
pub_rec : Number of derogatory public records
revol_bal : Total credit revolving balance
revol_util : Revolving line utilization rate, or the amount of credit the borrower is using relative to all available revolving credit.
total_acc : The total number of credit lines currently in the borrower's credit file
initial_list_status : The initial listing status of the loan. Possible values are – W, F
application_type : Indicates whether the loan is an individual application or a joint application with two co-borrowers
mort_acc : Number of mortgage accounts.
pub_rec_bankruptcies : Number of public record bankruptcies
Address: Address of the individual

## Tech Used:
Logistic Regression

## Tool used:
Scikit-Learn,Numpy, Pandas, Matplotlib,Seaborn

## Feature Engineering And Encoding:
1.Pub_rec,mortgage_acc,pub_rec_bankruptcy people who are having more than 1 count are treated as 1 value and rest are put 0 value. Because If there is some outlier with large vale of pub_rec may be person is very 
  much informative high risk customer for LoanTap that's why we should consider him.

2.fill missing mort_acc value with corresponding to total account median value cause both volumn are corelated to each other.

## Findings
1. The no of people those who have fully paid are 318357 and that of Charged Off are 77673.
2. B, C grade people are more prone to repay the loan
3. G grade people are 50:50 chances to repay . so put more interest on them - business insights
4. Managers and teacher are more affordable job loan title.
5. 10 yrs+ emp_length are likely to pay the loan.
6. No pub_rec is likely to repay loan back
7. No pub_rec_bankruptcy is likely to repay back loan
8. mort_acc 1 is likely to repay back loan
9. people take loan as fractional amount are more likely to repay it back.

## Solutions :
Almost 3.5 Lakh historic financial data were collected from LoanTap websites.
1. Applied Logistic Regression to find loan defaulter among the customer. We got high precision value outstanding 0.95 value makes LoanTap to correctly predict all loan defaulter out of predicted loan defaulter.
   They basically want to keep Precision higher.
2. (Optional) : In future if we want Recall matrix is a dominant matrix ,so we fix the imbalance data to balanced one and drop some columns then got ).81 score of Recall.

## Business impact:
After applying this model.LoanTap was able to minimize 4-5% financial loss by aviding loans to loan defaulter.

