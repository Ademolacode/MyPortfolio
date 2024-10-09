
# Loan Approval Prediction with Power Business Intelligence (BI)

### Dashboard Link : 
## Overview

The objective is to create a dependable model that will help financial institutions automate and improve the loan approval procedures they use. 

In this project, "Loan Approval Prediction with Power Business Intelligence (BI)," a model that predicts whether a loan application will be accepted or denied is developed using historical data. Using DAX (Data Analysis Expression) in Power BI, this analysis finds patterns and relationships in the information that influence the decision to approve a loan. 

For financial institutions to improve consistency and data-driven loan approval decisions, minimize manual labour, and streamline their decision-making processes, this project is essential. Additionally, it helps to reduce the default of granting loans that might default, which eventually boosts the lending process's general efficiency. 

## Data Source

The Dataset utilized in this study was obtained from Kaggle, a platform for data science and machine learning resources. The dataset, titled "Loan Approval Prediction Dataset" was made available in CSV (Comma-Separated Values) file format, ensuring ease of access and manipulation for research purposes. This dataset is publicly accessible. For reference and to ensure proper attribution, the dataset can be accessed via the following URL: 

https://www.kaggle.com/datasets/architsharma01/loan-approval-prediction-dataset. 

## Tool used

#### Power BI — Data Cleaning, Transformation, Analysis, and Creating Reports. 

#### Data Cleaning: The data format is a comma-separated (CSV) file converted to an Excel (xlsx) format for easy data loading into Power BI. The data was investigated, and it was discovered that categorical data has extra spaces, and the numerical data is stored as text/string. The Trim and Value function was used to clean them up  

=TRIM(text) 

=VALUE(text) 

#### Categorical Data 

Education – Graduate, Not Graduate 

Loan Status – Approved, Rejected 

Self-Employed – Yes, No 

#### Numerical Data 

Loan Amount 

Residential Asset Value 

Commercial Asset Value 

Luxury Asset Value 

Bank Asset Value 

Loan Term 

Number of Dependant 

The dataset was also formatted into an Excel table to manage and analyse new datasets. 

#### Data Transformation: Power Query was used to transform the data by importing the data through the New Source icon on the tools bar. A conditional column named Employment status was added to the data referencing the self-employed column. Below is the conditional statement 

IF Self-Employed = Yes, Then Self-Employed 

IF Self-Employed = No, Then Unemployed   

### Exploratory Data Analysis (EDA) 

The under-listed insights and key performance indicators were generated. 

Total Borrower (4,269) 

Total Loan Amount (64,604,700,000 ≈65bn) 

Percentage Approved (62.22%) 

Percentage Rejected (37.78%) 

Average Loan to Value Ratio (48.69%) 

Average CIBL score (599) 

Average Loan Term (10.9≈11) 

Average Dependants (2.5 ≈3) 

### Data Analysis 

The analysis was carried out with the aid of DAX (Data Analysis Expression) by creating different measures. These measures are the calculated values based on the imported data. These measures are dynamic and change based on the filter context or slicer. Below are the calculated measures. 

         
        
       
         % Approved = DIVIDE([Total Approved],[Total Borrower]) 
         % Rejected = DIVIDE([Total Rejected],[Total Borrower])   
         % Approved = DIVIDE([Total Approved],[Total Borrower]) 
         % Rejected = DIVIDE([Total Rejected],[Total Borrower]) 
         Average CIBIL Score = AVERAGEX(Loan_Approval_Dataset,Loan_Approval_Dataset[cibil_score]) 
         Average Dependents = AVERAGEX(Loan_Approval_Dataset,Loan_Approval_Dataset[no_of_dependents]) 
         Average Loan Term = AVERAGEX(Loan_Approval_Dataset,Loan_Approval_Dataset[loan_term]) 
         Average Loan to Value Ratio (LTV) = AVERAGEX(Loan_Approval_Dataset,Loan_Approval_Dataset[Loan to Value Ratio]) 
         Total Approved = COUNTAX(FILTER(Loan_Approval_Dataset,Loan_Approval_Dataset[loan_status]="Approved"),Loan_Approval_Dataset[loan_status]) 
         Total Borrower = COUNTX(Loan_Approval_Dataset,Loan_Approval_Dataset[loan_id]) 
         Total Commercial Asset Value = SUMX(Loan_Approval_Dataset,Loan_Approval_Dataset[commercial_assets_value]) 
         Total Income_Annum = SUMX(Loan_Approval_Dataset,Loan_Approval_Dataset[income_annum]) 
         Total Loan Amount = SUMX(Loan_Approval_Dataset,Loan_Approval_Dataset[loan_amount]) 
         Total Luxury Asset Value = SUMX(Loan_Approval_Dataset,Loan_Approval_Dataset[luxury_assets_value]) 
         Total Rejected = COUNTAX(FILTER(Loan_Approval_Dataset,Loan_Approval_Dataset[loan_status]="Rejected"),Loan_Approval_Dataset[loan_status]) 
         Total Residential Asset Value = SUMX(Loan_Approval_Dataset,Loan_Approval_Dataset[residential_assets_value]) 
         Loan to Value Ratio = Loan_Approval_Dataset[loan_amount]/(Loan_Approval_Dataset[residential_assets_value]+Loan_Approval_Dataset[commercial_assets_value]+Loan_Approval_Dataset[luxury_assets_value]+Loan_Approval_Dataset[bank_asset_value]) 

Based on the dataset, the entire borrower is 4,269 with a total Loan Amount of 64,604,700,000. 62% of these borrowers were approved and 38% were rejected. The loan amount and the income per annum are 93% positively correlated. 
The borrowers were analysed and categorized based on their employment (self-employed and unemployed) and education (graduate and not graduate) status. 

The under-listed metrics were also considered in the analysis process. 

#### Loan-to-Value Ratio: This metric assesses the risk associated with issuing a loan. It specifically focuses on secured loans, where the borrower pledges an asset (collateral). 

![Formular](https://github.com/user-attachments/assets/47976a9b-d6d3-40bb-9419-71d36d946798)

According to Financeband.com (2024), we can determine a good loan-to-value ratio should be no greater than 80%. Anything above 80% is considered to be a high LTV, which means that borrowers may face higher borrowing costs, require private mortgage insurance, or be denied a loan. LTVs above 95% are often considered unacceptable. Using the above metric, the LTV is 48.69% which falls under the acceptable range.  

CIBIL Score: Also known as the Credit Information Bureau (India) Limited score (CIBIL), is a three-digit number used by lenders in India to assess your creditworthiness. It essentially helps them understand how likely you are to repay a loan on time. On average, most of the borrowers who fall under the approved loan status have a 703 score and the rejected status has a 429. Overall, the company has an average CIBIL score of 599.

Everything all about CIBIL: ( https://www.bajajfinserv.in/insights/everything-you-need-to-know-about-your-credit-score#:~:text=CIBIL%20scores%20can%20range%20anywhere,personal%20loans%20and%20credit%20cards ).

#### Status Combination 

The table below is a combination of the categorized fields and their respective LTV and CIBL score. This can be drilled down with the aid of the slicers in the report.

![Table](https://github.com/user-attachments/assets/f0867ee4-78c9-487e-8bf4-d117c9adc5e5)


##  Visualization 

The visuals in the report were created and formatted using the power bi visuals. 


####  Figure 1. Loan Performance Dashboard Overview Screen 
![Overview](https://github.com/user-attachments/assets/671b26e9-44c4-4637-a469-d575403dfe1d)
#### 
#### 


####  Figure 2. Loan Performance Dashboard Request Screen 
![Request](https://github.com/user-attachments/assets/0d824e0a-582a-48ba-927e-3eff53d42838)
#### 
#### 

####  Figure 3. Loan Performance Dashboard Breakdown by Top 10 ID Screen 
![Breakdown by  Top 10 ID](https://github.com/user-attachments/assets/bf947a2d-d79b-4522-8ef3-7076218311ab)
#### 
#### 


####  Figure 4. Loan Performance Dashboard Approved Screen 
![Approved](https://github.com/user-attachments/assets/4139091b-3e0d-4236-a64f-c4b6c8127189)
####   
#### 

####  Figure 5. Loan Performance Dashboard Rejected Screen 
![Rejected](https://github.com/user-attachments/assets/5c2792a4-37db-478b-9700-e71fa8a0d393)
####   
#### 

####  Figure 6. Total Loan Amount and Total Income by Loan Status
![Total Loan Amount](https://github.com/user-attachments/assets/c1eed290-19e6-4093-8cc9-62bb4ffb3a46)
####   
#### 

####  Figure 7. Average CIBIL by Loan Status
![Average cibil_score](https://github.com/user-attachments/assets/68a17196-8e29-4dd6-988b-8ba2e21b7fe3)
####   
#### 

####  Figure 8. Total Approved by Education.
![Total Approved by Education](https://github.com/user-attachments/assets/f82381d3-9f44-4812-a291-caad21a44e58)
####   
#### 


####  Figure 9. Total Approved, Total Rejected and Average Dependant by Employment Status
![Total Approved, Total Rejected and Average Dependant by Employment Status](https://github.com/user-attachments/assets/5c90e862-64be-49b1-8715-1b8a908c0bb6)
####   
#### 

#### Figure 10. Total Approved by Employment Status.
![Total Approved by Employment Status](https://github.com/user-attachments/assets/e9f4a235-e346-4946-bfdc-a27d76303b2e)
####   
#### 



#### Figure 11. Total Rejected by Employment Status.
![Total Rejected by Employment Status](https://github.com/user-attachments/assets/1eee1244-054f-48f6-aed4-c702aeff65de)
####   
#### 


## Findings 

1. Total Approved and total Total Rejected are positively correlated with each other.

2. Unemployed had 1318 Total Approved, 801 Total Rejected, and 2.50 Average Dependents. Self Employed had 1338 Total Approved, 812 Total Rejected, and 2.50 Average Dependents. 

3. Approved accounted for 62.68% of the Total Loan Amount. 

4. Total Loan Amount and Total Income_Annum diverged the most when the loan_status was Approved when Total Loan Amount was 27,147,900,000 higher than Total Income_Annum.T 

5. Average of CIBL score for Approved (703.46) was higher than Rejected (429.47).

## Finding by Borrower ID (Loan ID) 

1. At 39,500,000, 510 had the highest Total Loan Amount and was 3.95% higher than 1216, which had the lowest Total Loan Amount at 38,000,000.

2. Total Loan Amount and total Total Income_Annum are positively correlated with each other.

3. 510 accounted for 10.25% of the Total Loan Amount.
4. Across all Top 10 loan_id, Total Loan Amount ranged from 38,000,000 to 39,500,000, Total Income_Annum ranged from 9600000 to 9900000, and Average Loan to Value Ratio (LTV) ranged from 50.19% to 78.25%.
5. 3902 had the highest Average Loan to Value Ratio (LTV) at 23.00%, followed by 4008 and 3107. 2753 had the lowest Average Loan to loan-to-value ratio (LTV) at 17.65%.
## Recommendations 

1. Implement a regular monitoring and review process. Regular check-ins on the applicant’s financial situation and adherence to repayment schedules can provide early warning signs if the applicant starts to struggle financially. 

2. Encourage the applicant to engage in a credit improvement plan. This could involve financial counseling or structured repayment plans for existing debts to improve their credit score over time. The applicant can then reapply for a larger loan or better terms after improving their credit score. 

3. Additional collateral or guarantees could be requested to further secure the loan. This can include additional property, investments, or a co-signer with a stronger credit profile. 

4. Offer a smaller loan amount or a shorter repayment term. This reduces the exposure and ensures quicker repayment, further reducing the risk for the lender. 

5. To compensate for the lower CIBIL score, consider offering the loan at a higher interest rate. This would provide additional revenue to offset the perceived risk. 

6. Given the low LTV ratio, the applicant has a strong position regarding the value of the collateral. This significantly mitigates the risk associated with their lower CIBIL score. The loan can be approved but with additional safeguards to protect the lending institution. 


### Steps followed 
The following step-by-step guide outlines the process:

 #### 1. Data Collection and Preparation: 

a) Obtain the dataset in CSV format from Kaggle, ensuring all necessary permissions and data usage agreements are in place. Load data into Power BI Desktop, dataset is a csv file.

   b) Perform an initial assessment of the data to understand its structure, variables, and potential quality issues. 

   c) Convert the CSV file to Excel (xlsx) format for easier data loading into Power BI. This step also allows for any initial manual cleaning or formatting if required. 

   d) Document the data source, its characteristics, and any transformations performed during this initial stage. 

 #### 2. Data Cleaning and Transformation: 

   a) Use Power Query to import the data into Power BI, leveraging its ETL (Extract, Transform, Load) capabilities. 

   b) Apply the Trim function to remove extra spaces from categorical data, ensuring consistency in text-based fields. 

   c) Use the Value function to convert numerical data stored as text/string to proper numerical format, enabling accurate calculations. 

   d) Create a conditional column for Employment status based on the Self-Employed column, enhancing the granularity of the analysis. 

   e) Identify and handle missing values, outliers, and any inconsistencies in the data. 

   f) Document all data cleaning and transformation steps for reproducibility and audit purposes. 

 #### 3. Exploratory Data Analysis (EDA): 

   a) Generate key performance indicators (KPIs) such as Total Borrower, Total Loan Amount, Percentage Approved/Rejected. 

   b) Create visualizations to explore relationships and patterns in the data, including histograms, scatter plots, and correlation matrices. 

   c) Analyze the distribution of key variables and their relationships with loan approval outcomes. 

   d) Identify potential predictive factors and their relative importance in the loan approval process. 

   e) Document insights gained from the EDA process, which will inform subsequent modeling steps. 

 #### 4. Data Analysis using DAX: 

   a) Develop DAX measures for calculated values, including: 

      - Approval and rejection percentages. 

      - Average CIBIL Score, Dependents, Loan Term, and Loan to Value Ratio.

      - Total Approved and Rejected loans.

      - Total asset values and income.

   b) Create a Loan to Value Ratio calculation using DAX, incorporating various asset types. 

   c) Implement time-based calculations to analyze trends and seasonality in loan approvals. 

   d) Develop complex measures that capture the interactions between multiple factors affecting loan approval. 

   e) Document all DAX formulas with clear explanations of their purpose and logic. 

 #### 5. Feature Engineering: 

   a) Categorize borrowers based on employment and education status, creating meaningful segments for analysis. 

   b) Calculate the Loan-to-Value Ratio for risk assessment, incorporating it as a key feature in the predictive model. 

   c) Create derived features that capture important aspects of the loan application process, such as debt-to-income ratios or credit utilization rates. 

   d) Bin continuous variables where appropriate to capture non-linear relationships. 

   e) Document the rationale behind each engineered feature and its expected impact on the model  

 #### 6. Model Development: 

   a) Use DAX to create predictive measures based on historical data patterns, incorporating key features identified in the EDA and feature engineering stages. 

   b) Develop a scoring system incorporating CIBIL Score, LTV, and other relevant factors, assigning weights based on their predictive power. 

   c) Implement logistic regression-like functionality using DAX to predict the probability of loan approval. 

   d) Create conditional statements to classify loan applications into approval categories based on the calculated probabilities. 

   e) Document the model's structure, assumptions, and limitations. 

 #### 7. Visualization and Reporting: 

   a) Create interactive dashboards and reports using Power BI visuals, ensuring they are intuitive and user-friendly. 

   b) Design visualizations for key metrics, approval/rejection rates, and borrower characteristics. 

   c) Implement slicers and filters to allow users to drill down into specific segments or time periods. 

   d) Create a scorecard visual that displays the key factors influencing the loan approval decision for individual applications. 

   e) Develop a summary report that provides an overview of the model's performance and key insights. 

   f) Document the design choices and user instructions for each visualization. 

 #### 8. Model Evaluation and Refinement: 

   a) Analyze the model's performance using historical data, calculating metrics such as accuracy, precision, recall, and F1 score. 

   b) Implement cross-validation techniques to assess the model's generalizability. 

   c) Conduct sensitivity analysis to understand the impact of different factors on loan approval predictions. 

   d) Refine the model based on findings and feedback, iterating on feature selection and weighting. 

   e) Document the evaluation process, results, and any refinements made to the model. 

 #### 9. Implementation and Monitoring: 

   a) Deploy the Power BI report for use in loan approval processes, ensuring proper access controls and data security measures are in place. 

   b) Set up regular data refreshes to keep the model up-to-date, automating the process where possible. 

   c) Establish a monitoring system to track the model's performance over time, including key metrics and any drift in predictions. 

   d) Implement a feedback loop to capture actual loan outcomes and incorporate them into future model refinements. 

   e) Develop a maintenance plan for regular updates and recalibration of the model. 

   f) Document the implementation process, monitoring procedures, and guidelines for ongoing maintenance. 
