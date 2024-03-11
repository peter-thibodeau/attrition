# Introduction

# Data Source
The sightings are from the National UFO Reporting Center (NUFORC) which was acquired by Sigmond Axel and can be found at https://github.com/planetsig/ufo-reports. I downloaded it as a .csv file.  

NUFORC allows the use of the data for non-commericial uses. There is a caveat on the website that states: "The National UFO Reporting Center makes no claims as to the validity of the information in any of these reports. Obvious hoaxes have been omitted, however most reports have been posted exactly as received in the author’s own words." The NUFORC website address is https://nuforc.org/.

# Data Exploration
- There are 88,876 records and 11 variables.
- There are 9 duplicate records.

## Variable Descriptions
|Variable|Datatype|Description|Nulls|Notes|
|:---|:---|:---|:---|:--|
|datetime|datetime|time of sighting, entered by user|0|1,207 have less than 10 chars which is NG|
|city|varchar|entered by the user|0|22,017 unique cities|
|state|varchar|entered by the user|7,409||
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
