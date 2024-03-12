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
  # 1. set text values to int for plotting
    ibm$pie <- with(ibm, ifelse(Attrition == 'Yes', 0, 1))
  # 2a. calc percent of yes and no
    group_counts <- table(ibm$pie)
    total_count <- sum(group_counts)
    percentage_by_group1 <- (group_counts / total_count) * 100
    percentage_by_group2 <- round(percentage_by_group1, digits = 1)
  # 2b. put in a dataframe
    attrit1 <- data.frame(
    quit = c("Yes","No"),
    percent_quit = percentage_by_group2)
  # 3. plot percentages
  attrit2 <- ggplot(attrit1, aes(x="", y=percent_quit.Freq, fill=quit))+geom_bar(width = 1, stat = "identity")
  pie <- attrit2 + coord_polar("y", start=0)
