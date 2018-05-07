# Project

## Team members:

- Tang Weinan 1701213093
- Yu Hao 1701213138
- Zhang Yao 1701213156
- Zhang Zhenbang 1701213158

## Dataset: Lending Club Loan Data

- Source: https://www.kaggle.com/wendykan/lending-club-loan-data<br/>
> These files contain complete loan data for all loans issued through the 2007-2015, including the current loan status (Current, Late, Fully Paid, etc.) and latest payment information. The file containing loan data through the "present" contains complete loan data for all loans issued through the previous completed calendar quarter. Additional features include credit scores, number of finance inquiries, address including zip codes, and state, and collections among others. The file is a matrix of about 890 thousand observations and 75 variables. A data dictionary is provided in a separate file. 

## Project description:

The Lending Club dataset provides us detailed information on all loans through the 2007-2015 in "loan.csv". For each loan, there are 72 features, such as the number of payments on the loan (term).<br/>

Our goal is to predict the default of loans based on the given information.

### Step 1: Data Preprocess

Procedures of data preprocess

There are 887379 lines of loans in the original dataset. To make it easier to work with, we randomly pick <b>10%</b> from it as a sample set.

Dependent variable - <b>'loan_status'. </b>
    
- There are 10 types of values in this variable, but considering our goal - to tell whether a borrower would default or not - we won't take care of all of them. 
- We only care about those loans either fully paid or paid very late(>121 days), because with the information on hand we can't tell the final result of a current loan or a loan overdue jsut a little bit.
- So we create a 0-1 variable corresponding to these two possible class. Positive class are those loans paid late.

Independent variables:
- Drop out features with more than 25% missing values
- Drop out features that have no or little predictive power and irrelevant to our target
- Replace missing values with 'Unknown' or mean value for numerical features
- Convert ordinal categorical features - 'emp_length' and 'grade' - into numerical
- Performing one-hot encoding on nominal features

There are 25,555 samples left after preprocessing. We save the processed data into df_sample.csv.

### Step 2: Prediction

We applied 8 classifiers to the preprocessed samples:

#### Perceptron

First, train perceptron algorithm on our data set and run an iteration to adjust the value of hyperparameter n_iter. Then we found that when the number of epochs equals to 80, which means n_iter equals to 80, Perceptron gives the highest accuracy score of 0.816916.

#### Logistic Regression

For the Logistic Regression, we do the same way as Perceptron. After running the iteration to adjust the hyperparameter c, we found that Logistic Regression gives the highest accuracy score of 0.816962 and the corresponding c with best accuracy and relative higher value is 0.05.

#### SVM

The SVC with linear kernel gives an accuracy score of 0.8169162. For SVC with RBF kernel, we adjust the value of gamma through the iteration. The optimal gamma with best accuracy and relative higher value is 100, where the highest accuracy score is 0.817048.

#### KNN

We also ran an iteration to adjust the hyperparameter k of KNN algorithm. When k equals to 14, KNN classifier gives the highest accuracy score, 0.812582, which is lowest among all algorithm. 

#### Decision Tree

The decision tree classifier gives an accuracy score of 0.818051. The 5 most important features in decision tree model are: 'int_rate', 'dti', 'annual_inc', 'term_ 60 months', 'term_ 36 months'.

#### Bagging

The bagging classifier gives an accuracy of 0.818704, which is slightly higher than the score from decision tree classifier.

#### AdaBoost

We ran an iteration to adjust n_estimator parameter of AdaBoost classifier. We found that when iteration equals to 50, AdaBoost gives the highest accuracy score, 0.819617, which is higher than decision tree and bagging. The 5 most important features in AdaBoost model under best iteration number are: 'int_rate', 'annual_inc', 'dti', 'revol_util', 'term_ 60 months'. The first three important features are consistent with the decision tree model, proving our result to be stable.

#### Random Forest

We also ran an iteration to adjust n_estimator parameter of Random Forest classifier. We found that when iteration equals to 260, Random Forest gives the highest accuracy score, 0.817791, which is the lowest among this four ensembled classifiers. The 5 most important features in Random Forest model are: 'int_rate', 'dti', 'annual_inc', 'revol_util', 'revol_bal'. The first three important features are consistent with the other models.

### Step 3: Model Evaluation

We do model evaluation by 10-folds cross-validation. Through the evaluation of eight models, we can find logistic regression has highest CV accuracy, 0.821. AdaBoost has second highest CV accuracy, 0.820. And SVM, decision tree, bagging and random forest have third highest CV accuracy, 0.819. The six models have similar CV accuracy. We can say that they are all effective and can be used to decide whether a loan will be default. On the contrast, KNN model¡¯s accuracy is 0.796 and perceptron¡¯s accuracy is 0.776. They are less effective and not good models.