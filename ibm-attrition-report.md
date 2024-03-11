# Introduction
The IBM HR Analytics Employee Attrition & Performance dataset is fictitious and widely used for data analysis practice. Still, it is helpful to understand how an analysis of it can improve the bottom line for companies and encourage them to launch programs to improve the workplace for employees.

# Data Source
The dataset can be found at Kaggle, https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset). It is provided under the Database Contents License (DbCL) v1.0 conditions.

# Data Description
- 1,470 records and 35 variables.
- 0 nulls
- 0 duplicates

|Variable name|Datatype|Values|
|:---|:---|:---|
|  Age                     | int|18 to 60|
|  Attrition               | varchar| Yes, No|
|  BusinessTravel          | varchar| 'Travel_Rarely''Travel_Frequently''Non_Travel'|
|  DailyRate               | int|$102 to $1,499|
|  Department              | varchar|'Sales''Research & Development''Human Resources'|
|  DistanceFromHome        | int|1 to 29 miles|
|  Education               | int|1 highschool, 2 bachelors, 3 masters, 4 doctorate|
|  EducationField          | varchar|'Life Sciences''Other''Medical''Marketing''Technical Degree''Human Resources'|
|  EmployeeCount           | int|all records equal one|
|  EmployeeNumber          | int|Unique identifier|
|  EnvironmentSatisfaction | int|1 poor, 2 good, 3 very good, 4 excellent|
|  Gender                  | varchar|'Female' 'Male'|
|  HourlyRate              | int|$30 to $100|
|  JobInvolvement          | int|1 little, 2 some, 3 moderate, 4 very|
|  JobLevel                | int|1 to 3|
|  JobRole                 | varchar|'Sales Executive''Research Scientist''Laboratory Technician''Manufacturing Director''Healthcare Representative''Manager''Sales Representative''Research Director''Human Resources'|
|  JobSatisfaction         | int|1 little, 2 some, 3 moderate, 4 very|
|  MaritalStatus           | varchar|'Single''Married''Divorced'|
|  MonthlyIncome           | int|$1,009 to $19,999|
|  MonthlyRate              | int|$2,094 to $26,999|
|  NumCompaniesWorked       | int|0 (never worked at another company) to 9 other jobs|
|  Over18                   | varchar|'Y', 'N', all records are 'Y'|
|  OverTime                 | varchar|'Yes','No'|
|  PercentSalaryHike        | int|11% to 25%|
|  PerformanceRating        | int|1 Needs Improvement, 2 Meets Expectations, 3 Exceeds Expectations, 4 Outstanding|
|  RelationshipSatisfaction | int|1 poor, 2 good, 3 very good, 4 excellent|
|  StandardHours            | int|all records equal eighty|
|  StockOptionLevel         | int |0 (none) to 3 (highest)|
|  TotalWorkingYears        | int |0 to 40 years|
|  TrainingTimesLastYear    | int |0 to 6 training sessions|
|  WorkLifeBalance          | int |1 poor, 2 good, 3 very good, 4 excellent|
|  YearsAtCompany           | int |0 to 40 years|
|  YearsInCurrentRole       | int |0 to 18 years|
|  YearsSinceLastPromotion  | int |0 to 15 years|
|  YearsWithCurrManager     | int |0 to 17 years|

# Data Cleaning
- Remove leading and trailing spaces
- All varchar values are chosen from a list  
&nbsp;&nbsp;&nbsp;&nbsp;no punctuation issues  
&nbsp;&nbsp;&nbsp;&nbsp;capitalization is standardized  
&nbsp;&nbsp;&nbsp;&nbsp;no other formatting problems  
&nbsp;&nbsp;&nbsp;&nbsp;no errors found  
- Integer values  
&nbsp;&nbsp;&nbsp;&nbsp;no periods or commas  
&nbsp;&nbsp;&nbsp;&nbsp;no other formatting problems  
