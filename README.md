# Project-3 Exploratory Data Analysis and Machine Learning model of loans by the U.S. Small Business Administration
## Introduction of Analysis
This dataset is from the U.S. Small Business Administration (SBA).

The U.S. SBA was founded in 1953 on the principle of promoting and assisting small enterprises in the U.S. credit market (SBA Overview and History, US Small Business Administration (2015)). Small businesses have been a primary source of job creation in the United States; therefore, fostering small business formation and growth has social benefits by creating job opportunities and reducing unemployment. There have been many success stories of start-ups receiving SBA loan guarantees such as FedEx and Apple Computer. However, there have also been stories of small businesses and/or start-ups that have defaulted on their SBA-guaranteed loans.

Source: https://www.kaggle.com/mirbektoktogaraev/should-this-loan-be-approved-or-denied

## Project at a glance:
The purpose of this project is to find correlations to find how likely a loan will be paid in full or more likely defaulted. After the analysis, I will train a machine learning algorithm to classify loans as more likely to be paid in full or as more likely to default. This can be help businesses in assessing clients when they are applying for a loan.

## Research prior to conducting the analysis
I have found that the main factors that organizations take into consideration for assessing applicants for a loan consist of the following:
1. Capacity - Repayment or credit history
2. Collateral - Sometimes organizations require security to cover its risk
3. Capital - The company's primary fund to work with
4. Character - Company's history and reputation
5. Conditions - The economic climate of an industry
6. Age & Experience - How long the company has been working in a specific industry
7. Loan amount
8. Repayment Period - Term of the loan

I shall take these factors into account during my analysis.

Code used: Python
Libraries used: Numpy, Matplotlib, Seaborn, Pandas, Scikit Learn

## Data Cleaning
1. Removed null values from dataset
2. Removed values that were not classified correctly such as Revolving Line Credit, Lowdoc, and New or existing business.
3. Imputed null values for the state of the borrower.
4. Extracted the bank approved amount and SBA approved amount into integers.
5. Changed the format of the date columns to be uniform.
6. Simplified the sectors based on the NAICS column (sector code).
7. Added columns that stated if the state of the borrower and lender were the same. Added a column that stated if the bank loan amount is higher or the same as the SBA guaranteed amount.

## Data Exploration
The list below consists of some of the most relevant insights.
1. Majority of loans came from borrowers in Los Angeles, California
2. Majority of loans came from the Bank of America National Association.
3. Loans that were a revolving line of credit had a higher significant chance of being defaulted.

## Model Building
I split the data into 80% for training the model and 20% for testing.
Models used:
1. Logistic Regression
2. Support Vector Machine Classifier
3. Random Forest Classifier

I used cross validation score, precision, recall and f1-score to evaluate the classification models.
Results:
| Model        | Crossval score    | Precision.         | Recall             | f1-score          |
|--------------|-------------------|--------------------|--------------------|-------------------|
|Logistic Reg  |0.8517645986773695 | 0.8652328281974391 | 0.9724080685647996 | 0.9156951010491026|
|Linear SCV    |0.8186911561085098 | 0.8193528298330861 | 1.0                | 0.9007080060531815|
|Random Forest |0.9206339782706996 | 0.9417292501653761 | 0.968127768943826  | 0.9547460661081222|

The Random Forest Classifier performed the best in terms of accuracy, precision, recall and f1-score.

## Findings:
Based on the Random Forest Classifier, the top features that had the highest contribution to classifying if a loan would be paid in full or charged off consist of the term loan, loan amount, if the lender and borrower are in the same state, if it was a new or existing business, if it was a revolving line of credit loan, if it was an urban or rural business, and various business sectors. I would have liked to explore other features such as the business equity, how many years in business, and other business factors because these are also relevant features in assessing for a loan.
