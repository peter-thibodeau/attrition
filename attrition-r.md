https://www.kaggle.com/code/peterthibodeau/notebook6e2b6dea64/edit

# create dataframe
attrition = read.csv('/kaggle/input/ibm-attrition-rate/IBM-A.csv')

# get column names
colnames(attrition)

# explore data
summary(attrition)
str(attrition)
head(attrition)
tail(attrition)

# count nulls
sum(is.na(attrition))

# get unique values for applicable variables
unique(attrition$BusinessTravel)
unique(attrition$Department)
unique(attrition$Education)
unique(attrition$EducationField)
unique(attrition$EmployeeCount)
unique(attrition$EnvironmentSatisfaction)
unique(attrition$Gender) 
unique(attrition$JobInvolvement)
unique(attrition$JobLevel) 
unique(attrition$JobRole) 
unique(attrition$JobSatisfaction) 
unique(attrition$MaritalStatus) 
unique(attrition$Over18) 
unique(attrition$OverTime)
unique(attrition$PerformanceRating)
unique(attrition$RelationshipSatisfaction) 
unique(attrition$StandardHours) 
unique(attrition$StockOptionLevel)
unique(attrition$TrainingTimesLastYear)
unique(attrition$WorkLifeBalance)

# look for issues that need cleaning
print(attrition)

# trim leading and trailing whitespace
trimws(attrition, "l")
trimws(attrition, "r")

# count duplicates
sum(duplicated(attrition))

coorelation <- data.frame(
    cyl= round(cor(attrition$Attrition, attrition$Gender), digits = 2),
    )
    print(coorelation)



# old
# DFs that need calc col 1st
 degree <- table(attrition$Education)
 workplace <-table(attrition$EnvironmentSatisfaction)
 attitude <- table(attrition$JobInvolvement)
 like_job <- table(attrition$JobSatisfaction)

# DFs
 attrition <- table(attrition$Attrition)
 travel <- table(attrition$BusinessTravel)
 dept <- table(attrition$Department)
 major <- table(attrition$EducationField)
 gender <- table(attrition$Gender)
 job_title <- table(attrition$JobRole)
 status <- table(attrition$MaritalStatus)
 ot <- table(attrition$OverTime)
 raise <- table(attrition$PercentSalaryHike)
 perf_review <- table(attrition$PerformanceRating)
 options <- table(attrition$StockOptionLevel)
 training <- table(attrition$TrainingTimesLastYear)
 life <- table(attrition$WorkLifeBalance)

# Numeric
age <- table(attrition$Age)
commute <- table(attrition$DistanceFromHome)
salary <- table(attrition$MonthlyIncome) x 12
experience <- table(attrition$TotalWorkingYears)
company_tenure <- table(attrition$YearsAtCompany)
job_tenure <- table(attrition$YearsInCurrentRole)
last_promotion <- table(attrition$YearsSinceLastPromotion)
years_with_manager <- table(attrition$YearsWithCurrManager)
prev_jobs <- table(attrition$NumCompaniesWorked)


attrit2 <- data.frame(attrit1)
quit = round(((attrit2[2,2]/nrow(attrition))*100), digits=1)
stay = round(((attrit2[1,2]/nrow(attrition))*100), digits=1)


attrit3 <- ggplot(attrit2, aes(x="", y=Freq, fill=Var1))+geom_bar(width = 1, stat = "identity") + coord_polar("y", start=0)
  # Freq is column name in attrit2

