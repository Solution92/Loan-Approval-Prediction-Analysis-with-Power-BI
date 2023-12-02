# Loan-Approval-Prediction-Analysis-with-Power-BI

## Table of Content

- [Project Overview](#project-overview)
- [Data Source](#data-source)
- [Tools Used](#tools-used)
- [Data Cleaning and Preparation](#data-cleaning-and-preparation)
- [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
- [Data Analysis](#data-analysis)
- [Visualization](#visualization)
- [The Dashboard](#the-dashboard)
- [Result and Findings](#result-and-findings)
- [Recommendation](#recommendation)
- [Limitations](#limitations)
- [Reference](#reference)

### Project Overview

The goal is to develop a reliable model that can assist financial institutions in automating and optimizing their loan approval processes.

This Project, Loan Approval Prediction Analysis involves using historical data to build a model that can predict whether a loan application is likely to be approved or rejected. This predictive analysis leverages machine learning algorithms and statistical techniques to identify patterns and relationships within the dataset that contribute to the loan approval decision. 

This Project is crucial for financial institutions to streamline their decision-making processes, reduce manual effort, and make more consistent and data-driven loan approval decisions. It also contributes to minimizing the risk of approving loans that may default, ultimately improving the overall efficiency of the lending process.

### Data Source

The Dataset was in CSV file format provided by our client and for Data security it is not permitted or accessible by the public.

### Tools Used

Power BI — Data Cleaning, Transformation, Analysis, and Creating Reports.

### Data Cleaning and Preparation

Investigating the dataset to understand its structure, size, and basic characteristics was the first thing. Exploring the distribution of variables, identifying outliers, and understanding the type of data (categorical, numerical).

The dataset has 614 rows and 13 columns as Loan ID, Gender, Married, Dependent, Education, Self-employed, etc.

Here are some cleaning processes I went through to prepare the data

**Missing Values:** In the “Loan_Amount” column, there were missing values denoted by blank cells.
In the “Credit_History” column, there are missing values denoted by blank cells

**Data Types:** The “Dependents” column had a value “3+” which might be better represented as a numeric value.

**Categorical Values:** Some columns, like “Gender,” “Married,” “Education,” “Self-Employed,” and “Property_Area,” contain categorical values that need to be converted into a numerical format for analysis.

The “Dependents” column also needed to be converted to a numeric format.

**Inconsistent Data:** There was an entry where “Gender” was blank, and “Dependents” were present. I simply used the “find and replace” option to transform it to “N/A” meaning not applicable.

In a nutshell, I handled missing values in “Loan_Amount,” “Loan_Amount_Term,” and “Credit_History.”

Converted categorical variables into a suitable format for analysis (e.g., one-hot encoding or label encoding).

Addressed the inconsistency in the data, such as the entry with a blank “Gender.”

### Exploratory Data Analysis (EDA)

I have generated the following key Performance Indicators (KPIs) and insights:

- Gender = 614
- Educated = 480
- Self Employed = 82
- AVG Applicant Income = 5.40k
- Avg. Co-applicant Income = 1.62k
- AVG loan Amount = 141.17
- AVG loan Amount term 334.20
- Percentage of Approval = 0.69
- Percentage of Positive Credit History = 0.77
- % of Approval by Credit History
- Sum of Applicant Income by Property Area
- Avg. Loan Amount by Dependents
- % of Approval by Applicant Income
- % of Approval by Loan_Amount_Term

### Data Analysis

Using Power BI, here is the process of analysis with Loan Approval Prediction:

~~~
Key Performance Indicators (KPIs)
- Gender = COUNTROWS(LoanApprovalPrediction)
- Educated = CALCULATE(COUNTROWS(LoanApprovalPrediction),LoanApprovalPrediction[Education]=”Graduate”)
- Self Employed = CALCULATE(COUNTROWS(LoanApprovalPrediction), LoanApprovalPrediction[Self_Employed]=”Yes”)
- Avg. Applicant Income = AVERAGE( LoanApprovalPrediction[Applicant_Income])
- Avg. Coapplicant Income = AVERAGE(LoanApprovalPrediction[Coapplicant_Income])
- Avg. Loan Amount = AVERAGE( LoanApprovalPrediction[Loan_Amount])
- Avg. Loan Amount Term = AVERAGE(LoanApprovalPrediction[Loan_Amount_Term])
- % of Approval = DIVIDE(CALCULATE(COUNTROWS( LoanApprovalPrediction), LoanApprovalPrediction[Loan_Status]=”Y”), COUNTROWS(LoanApprovalPrediction))
- % of Positive Credit History =
- DIVIDE(CALCULATE(COUNTROWS( LoanApprovalPrediction),LoanApprovalPrediction[Credit_History]=1),COUNTROWS(LoanApprovalPrediction))
~~~

- Average Metrics: Calculated the average applicant income, coapplicant income, loan amount, and loan amount term.
  
- Percentage Metrics: Determined the percentage of approved and rejected loans (‘Loan_Status’).
- Calculated the percentage of loans with a positive credit history.

- Analytical Insights:
  - Explored the impact of credit history on loan approval.
    
  - Compared the distribution of credit history for approved and rejected loans.
    
  - Investigated the relationship between applicant income and loan amount.
 
  - Explored the distribution of applicants across different property areas.
  
  - Analyzed the influence of the number of dependents on loan approval.
    
  - Examined the distribution of loan terms.


### Visualization:

I created the following visual analyses using Power BI.

-  % of Approval by Credit History

-  Avg. Loan Amount by Dependents

-  % of Approval by Applicant Income

-  % of Approval by Loan_Amount_Term

-  Sum of Applicant Income by Property Area


### The Dashboard


![6](https://github.com/Solution92/Loan-Approval-Prediction-Analysis-with-Power-BI/assets/144762124/fd77abcd-100b-45de-97ac-88f5d099e243)


### Result and Findings

Here are my findings in the Loan Approval Prediction Analysis;

In the % of Approval by Credit History, the Approval for 1 (0.80) was higher than 0 (0.32).

Meanwhile, in the Avg. Loan Amount by Dependents, At 183.41, 3 had the highest Avg. Loan Amount was 40.32% higher than 0, which had the lowest Avg. Loan Amount at 130.71. 3 had the highest Avg. Loan Amount at 183.41, followed by 1, 2, and 0. Across all 4 Dependents, Avg. Loan_Amount ranged from 130.71 to 183.41.

At 1,233,097, Semiurban had the highest Sum of Applicant_Income and was 24.03% higher than Rural, which had the lowest Sum of Applicant_Income at 994,181. Semiurban had the highest Sum of Applicant_Income at 1,233,097, followed by Urban at 1,090,446 and Rural at 994,181. Semiurban accounted for 37.17% of Sum of Applicant_Income. Urban had 1,090,446 Sum of Applicant_Income, Rural had 994,181, and Semiurban had 1,233,097.

However, the top 3 Loan_Amount_Term all had % of Approval of 1. Across all 10 Loan_Amount_Term, % of Approval ranged from 0.40 to 1.

### Recommendation
- Credit History Influence: If positive credit history significantly impacts loan approval, consider emphasizing this factor in your risk assessment and lending policies.

- Property Area and Income Insights: Explore business opportunities or tailor marketing strategies based on the regions with higher cumulative applicant income.

- Dependents and Loan Amounts: Assess whether the number of dependents is a crucial factor in determining the loan amount. This understanding can be used to refine loan product offerings.

- Income Segmentation: If higher applicant income correlates with higher approval rates, consider creating segmented loan products or adjusting eligibility criteria based on income brackets.
- Loan Amount Term Preferences: Analyze if there’s a preferred loan term duration among approved loans. Tailoring loan products to align with these preferences could enhance customer satisfaction.
- Continuous Monitoring: Regularly update and review your analysis as new data becomes available. Markets and customer behaviors can change, and staying informed will help in adapting strategies accordingly.

### Limitations

- Limited Features: The dataset may lack certain features that could provide more context for loan approval decisions, such as employment history, debt-to-income ratio, or additional demographic information.
- Temporal Aspect: The dataset might lack a temporal dimension. Understanding when the data was collected and whether there are temporal trends is essential, especially in financial datasets.
- Contextual Information: The dataset might lack contextual information about the reasons behind certain entries or the specific criteria used for loan approval.

### Reference

- For datasets of this nature, you may refer to [kaggle](https://kaggle.com/)


#data #loan #decision #application #analysis #approval #finance #communication #teamwork #powerbi



























