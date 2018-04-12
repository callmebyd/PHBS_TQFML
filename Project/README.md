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
- Preprocess the data

- Choose features which are close to credit rating from the data set.

>home_ownership: The home ownership status provided by the borrower during registration. Our values are: RENT, OWN, MORTGAGE, OTHER. <br/>
annual_income_joint: The combined self-reported annual income provided by the co-borrowers during registration <br/>
emp_length: Employment length in years. Possible values are between 0 and 10 where 0 means less than one year and 10 means ten or more years.  <br/>
inq_last_6mths: The number of inquiries in past 6 months (excluding auto and mortgage inquiries) <br/>
installment: The monthly payment owed by the borrower if the loan originates. <br/>
last_pymnt_amnt: Last total payment amount received <br/>
open_acc: The number of open credit lines in the borrower's credit file. <br/>
loan_amnt: The listed amount of the loan applied for by the borrower. If at some point in time, the credit department reduces the loan amount, then it will be reflected in this value. <br/>
pymnt_plan: Indicates if a payment plan has been put in place for the loan <br/>
term: The number of payments on the loan. Values are in months and can be either 36 or 60. <br/>
pub_rec: Number of derogatory public records <br/>
max_bal_bc: Maximum current balance owed on all revolving accounts <br/>
acc_now_delinq: The number of accounts on which the borrower is now delinquent.

- Predict the loan grade using classification algorithms like Logistic Regression/SVM/KNN.

- Adjust the model to get more accurate results.