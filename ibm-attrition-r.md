https://www.kaggle.com/code/peterthibodeau/notebook6e2b6dea64/edit

# create dataframe
ibm = read.csv('/kaggle/input/ibm-attrition-rate/IBM-A.csv')

# get column names
colnames(ibm)

# explore data
summary(ibm)
str(ibm)
head(ibm)
tail(ibm)

# count nulls
sum(is.na(ibm))

# get unique values for applicable variables
unique(ibm$BusinessTravel)
unique(ibm$Department)
unique(ibm$Education)
unique(ibm$EducationField)
unique(ibm$EmployeeCount)
unique(ibm$EnvironmentSatisfaction)
unique(ibm$Gender) 
unique(ibm$JobInvolvement)
unique(ibm$JobLevel) 
unique(ibm$JobRole) 
unique(ibm$JobSatisfaction) 
unique(ibm$MaritalStatus) 
unique(ibm$Over18) 
unique(ibm$OverTime)
unique(ibm$PerformanceRating)
unique(ibm$RelationshipSatisfaction) 
unique(ibm$StandardHours) 
unique(ibm$StockOptionLevel)
unique(ibm$TrainingTimesLastYear)
unique(ibm$WorkLifeBalance)

# look for issues that need cleaning
print(ibm)

# trim leading and trailing whitespace
trimws(ibm, "l")
trimws(ibm, "r")

# count duplicates
sum(duplicated(ibm))

# DFs that need calc col 1st
 degree <- table(ibm$Education)
 workplace <-table(ibm$EnvironmentSatisfaction)
 attitude <- table(ibm$JobInvolvement)
 like_job <- table(ibm$JobSatisfaction)

# DFs
 attrition <- table(ibm$Attrition)
 travel <- table(ibm$BusinessTravel)
 dept <- table(ibm$Department)
 major <- table(ibm$EducationField)
 gender <- table(ibm$Gender)
 job_title <- table(ibm$JobRole)
 status <- table(ibm$MaritalStatus)
 ot <- table(ibm$OverTime)
 raise <- table(ibm$PercentSalaryHike)
 perf_review <- table(ibm$PerformanceRating)
 options <- table(ibm$StockOptionLevel)
 training <- table(ibm$TrainingTimesLastYear)
 life <- table(ibm$WorkLifeBalance)

# Numeric
age <- table(ibm$Age)
commute <- table(ibm$DistanceFromHome)
salary <- table(ibm$MonthlyIncome) x 12
experience <- table(ibm$TotalWorkingYears)
company_tenure <- table(ibm$YearsAtCompany)
job_tenure <- table(ibm$YearsInCurrentRole)
last_promotion <- table(ibm$YearsSinceLastPromotion)
years_with_manager <- table(ibm$YearsWithCurrManager)
prev_jobs <- table(ibm$NumCompaniesWorked)


# old
attrit2 <- data.frame(attrit1)
quit = round(((attrit2[2,2]/nrow(ibm))*100), digits=1)
stay = round(((attrit2[1,2]/nrow(ibm))*100), digits=1)


attrit3 <- ggplot(attrit2, aes(x="", y=Freq, fill=Var1))+geom_bar(width = 1, stat = "identity") + coord_polar("y", start=0)
  # Freq is column name in attrit2

