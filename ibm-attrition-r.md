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

# attrition
attrit1 <- table(ibm$Attrition)
attrit2 <- data.frame(d)
quit = round(((attrit2[2,2]/nrow(ibm))*100), digits=1)
stay = round(((attrit2[1,2]/nrow(ibm))*100), digits=1)
attrit3 <- ggplot(attrit2, aes(x="", y=Freq, fill=Var1))+geom_bar(width = 1, stat = "identity") + coord_polar("y", start=0)
  # Freq is column name in attrit2

