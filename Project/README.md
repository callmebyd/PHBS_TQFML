# Project

### Team members:
- Tang Weinan 1701213093
- Yu Hao 1701213138
- Zhang Yao 1701213156
- Zhang Zhenbang 1701213158

### Dataset: Lending Club Loan Data
- Source: https://www.kaggle.com/wendykan/lending-club-loan-data<br/>
> These files contain complete loan data for all loans issued through the 2007-2015, including the current loan status (Current, Late, Fully Paid, etc.) and latest payment information. The file containing loan data through the "present" contains complete loan data for all loans issued through the previous completed calendar quarter. Additional features include credit scores, number of finance inquiries, address including zip codes, and state, and collections among others. The file is a matrix of about 890 thousand observations and 75 variables. A data dictionary is provided in a separate file. 

### Project description:
The Lending Club dataset provides us detailed information on all loans through the 2007-2015 in "data.csv". For each loan, there are 72 features, such as the number of payments on the loan (term), the number of accounts on which the borrower is now delinquent (acc_now_delinq).<br/>
The goal of our project is to predict the LC assigned loan grade using features of the borrower. <br/>

### Plan
- Choose features which are close to credit rating from the data set:

>home_ownership <br/>
annual_income_joint <br/>
emp_length <br/>
inq_last_6mths <br/>
installment <br/>
last_pymnt_amnt <br/>
open_acc <br/>
loan_amnt <br/>
pymnt_plan <br/>
term <br/>
pub_rec <br/>
max_bal_bc <br/>
acc_now_delinq <br/>

- Predict the interest rate on the loan using linear regression and get the predicted loan grade.

- Adjust the model to get more accurate results.