# Introduction

# Data Source
The sightings are from the National UFO Reporting Center (NUFORC) which was acquired by Sigmond Axel and can be found at https://github.com/planetsig/ufo-reports. I downloaded it as a .csv file.  

NUFORC allows the use of the data for non-commericial uses. There is a caveat on the website that states: "The National UFO Reporting Center makes no claims as to the validity of the information in any of these reports. Obvious hoaxes have been omitted, however most reports have been posted exactly as received in the author’s own words." The NUFORC website address is https://nuforc.org/.

# Data Exploration
- There are 1,470 records and 35 variables.
- There are 0 nulls.

|Variable name|Datatype|Values|
|:---|:---|:---|
|  Age                     | int| min 18, max 60|
|  Attrition               | chr| Yes, No|
|  BusinessTravel          | chr| 'Travel_Rarely''Travel_Frequently''Non-Travel'|
|  DailyRate               | int|$102 to $1,499|
|  Department              | chr|'Sales''Research & Development''Human Resources'|
|  DistanceFromHome        | int|1 to 29 miles|
|  Education               | int|1 highschool, 2 bachelors, 3 masters, 4 doctorate|
|  EducationField          | chr|'Life Sciences''Other''Medical''Marketing''Technical Degree''Human Resources'|
|  EmployeeCount           | int|all records equal one|
|  EmployeeNumber          | int|Unique identifier|
|  EnvironmentSatisfaction | int|1 poor, 2 good, 3 very good, 4 excellent|
|  Gender                  | chr|'Female' 'Male'|
|  HourlyRate              | int|$30 to $100|
|  JobInvolvement          | int|1 little, 2 some, 3 moderate, 4 very|
|  JobLevel                | int|1 to 3|
|  JobRole                 | chr|'Sales Executive''Research Scientist''Laboratory Technician''Manufacturing Director''Healthcare Representative''Manager''Sales Representative''Research Director''Human Resources'|
|  JobSatisfaction         | int|1 little, 2 some, 3 moderate, 4 very|
|  MaritalStatus           | chr|'Single''Married''Divorced'|
|  MonthlyIncome           | int|$1,009 to $19,999|
|  MonthlyRate              | int|$2,094 to $26,999|
|  NumCompaniesWorked       | int|0 (IBM is only job) to 9 other jobs|
|  Over18                   | chr|'Y', 'N'|
|  OverTime                 | chr|'Yes','No'|
|  PercentSalaryHike        | int|11% to 25%|
|  PerformanceRating        | int|1 Needs Improvement,2 Meets Expectations, 3 Exceeds Expectations, 4 Outstanding|
|  RelationshipSatisfaction | int|1 poor, 2 good, 3 very good, 4 excellent|
|  StandardHours            | int|all records equal eighty|
|  StockOptionLevel         | int |0 none to 3 highest|
|  TotalWorkingYears        | int |0 to 40 years|
|  TrainingTimesLastYear    | int |0 to 6 number of training sessions|
|  WorkLifeBalance          | int |1 poor, 2 good, 3 very good, 4 excellent|
|  YearsAtCompany           | int |0 to 40 years|
|  YearsInCurrentRole       | int |0 to 18 years|
|  YearsSinceLastPromotion  | int |0 to 15 years|
|  YearsWithCurrManager     | int |0 to 17 years|

## Variable Descriptions
|Variable|Datatype|Description|Nulls|Notes|
|:---|:---|:---|:---|:--|
|Age|datetime|time of sighting, entered by user|0|1,207 have less than 10 chars which is NG|
|Attrition|varchar|entered by the user|0|22,017 unique cities|
||varchar|entered by the user|7,409||
|country|varchar|entered by the user|12,365|6 unique countries|
|shape|varchar|entered by the user|2,922|29 unique shapes|
|duration (seconds)|integer|entered by the user|2||
|duration (hours/min)|varchar|entered by the user|3,017||
|comments|varchar|entered by the user|35||
|date posted|datetime|entered by the user|0||
|latitude|datetime|decimal|0|note 1|
|longitude|datetime|decimal|0|note 1|

Note 1: There are 1,494 records where latitude and longitude both equal zero, which is in the middle of the Indian Ocean; they will be removed.

# Data Cleaning
Several variable names are unrecognizable by SQL and have to be changed as shown in the following table:

|Variable|New name|
|:---|:---|
|duration (seconds|duration_sec|
|duration (hours/min)|duration_hour_min|
|date posted|date_posted|

- Remove leading and trailing spaces.
- Change strings to upper case to simplify SQL queries.
- Remove duplicate records.
- Remove punctuation marks in city.
- Revove datetime strings that are less that 10 characters in length.
- Extract date from datetime.
- Extract time from datetime.

## Filtering
  
## New Variables

