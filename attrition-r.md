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

# convert varchar to integer
attrition <- transform(attrition, attrit = ifelse(Attrition == "Yes", 1, 0))
attrition <- transform(attrition, travel =
    case_when(
        BusinessTravel == "Non_Travel" ~ '1',
        BusinessTravel == "Travel_Rarely" ~ '2',
        BusinessTravel == "Travel_Frequently" ~ '3',
        TRUE ~ '0'
))
attrition <- transform(attrition, department =
    case_when(
        Department == "Sales" ~ '1',
        Department == "Research & Development" ~ '2',
        Department == "Human Resources" ~ '3',
        TRUE ~ '0'
))
attrition <- transform(attrition, major =
    case_when(
        EducationField == "Life Sciences" ~ '1',
        EducationField == "Other" ~ '2',
        EducationField == "Medical" ~ '3',
        EducationField == "Marketing" ~ '4',
        EducationField == "Technical Degree" ~ '5',
        EducationField == "Human Resources" ~ '6',
        TRUE ~ '0'
))
attrition <- transform(attrition, gender = ifelse(Gender == "Male", 1, 2))
attrition <- transform(attrition, title =
    case_when(
        JobRole == "Sales Executive" ~ '1',
        JobRole == "Research Scientist" ~ '2',
        JobRole == "Laboratory Technician" ~ '3',
        JobRole == "Manufacturing Director" ~ '4',
        JobRole == "Healthcare Representative" ~ '5',
        JobRole == "Manager" ~ '6',
        JobRole == "Research Director" ~ '7',
        JobRole == "Human Resources" ~ '8',
        TRUE ~ '0'
))
attrition <- transform(attrition, marital =
    case_when(
        MaritalStatus == "Single" ~ '1',
        MaritalStatus == "Married" ~ '2',
        MaritalStatus == "Divorced" ~ '3',
        TRUE ~ '0'
))
attrition <- transform(attrition, overtime = ifelse(OverTime == "Yes", 1, 0))




attrition <- transform( 
  attrition, attrit = ifelse(Attrition == "No", 0, 1))
attrition <- transform( 
  attrition, gender = ifelse(Gender == "Male", 0, 1))
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

