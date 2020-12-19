# Covid-19 Positive Cases and California
<p align=“center”>
  <img src="https://github.com/nguyenbel/CA-Age-Groups-and-Covid-19/blob/master/img/people_wearing_masks.jpg">
</p>

### Insight into which age group tests positive more often for Covid-19 in California.

## Belinda Nguyen
[Linkedin](https://www.linkedin.com/in/bnguyen05/) * [Github](https://github.com/nguyenbel) * [Slides](https://github.com/nguyenbel/)

## Background and Motivation
Due to the Coronavirus (Covid-19), 2020 has been a strange year for everyone. Covid-19 is a new illness that can affect one's respiratory system and has similar symptoms to the flu. Many health experts advised people to wear a mask when they went out and to wash their hands for 20 seconds or to sanitize their hands frequently. The United States of America has had a hard time handling the pandemic due to poor leadership and the state governors are told that they are responsible to mitigate the spread of Covd-19 with little to no help from the Federal Government. On March 16, 2020, stay-at-home orders were put into place in California to slow the spread of Covid-19. California was often used as one of the examples of what a state should do to handle the pandemic.

This study analyzes the positive cases of Covid-19 in California between age groups. Which age group has the most daily new cases in California? What proportion of people in each age group tests positive with respect to the total population of their age group? Is the positive cases for each age group in California a sample of the positive cases for each age group in the United States?

## Data
#### Description: 
Californiia Department of Public Health compiled a [data set](https://data.ca.gov/dataset/covid-19-cases) of Covid-19 cases in California and broke down the data into several categories: total cases, age demographic, sex demographics, and ethnicity demographics. I took the data for the total cases and the age demographic, then found data on the population of California based on the age groups and sex, and, finally, demographic trends of Covid-19 in the United States from the Centers for Disease Control and Prevention.

#### Refinement: 
I grouped the total Covid-19 Cases in California by dates since they were separated by counties and summed the total positive and new cases columns. Next, I grouped the total Covid-19 Cases - Age Demographics in California by dates and age group and summed the total positive cases columns. In this DataFrame, I found that some of the age groups were recorded (65 and older changed to 65+ and Unknown changed to Missing), so I recorded those rows to ensure they had the same names. I merged the two DataFrames together based on the dates. I created a new column which showed the proportion of cases in each age group over the total number of cases in California.

Next, I worked with the data on the population of Callifornia based on age groups and sex. I renamed the columns to make it more readable, then I went through the columns: Total Estimate, Male Estimate, and Female Estimate in the DataFrame to change the column type from *string* to *int64*. Afterwards, I merged the rows to match the age groups found in the California Covid-19 Cases - Age Demographic dataset. After merging the rows by summing them, I found that the population dataset I found went from ages 0-19, 20-49, 50-64, 64 and Older, whereas the Covid-19 - Age Demographic dataset went from 0-17, 18-49, 50-64, 65 and Older, and Missing. This led me to find data for the population of those under the age of 17 years old in California. I added this information by subtracting the data found by the sum of people from 0-19 year old age group, then added the difference to the 20-49 year old age group. From here, I created three new columns: one showed a proportion of cases in each group over the population of that age group in California, another was the new daily confirmed cases for each age group, and the last was the proportion of the new confirmed cases over the total number of new cases for that date.

## Exploratory Data Analysis:
The time series line graph shows the daily new confirmed cases for each age group. Aside from the missing age group, each age group has similar trends as to where there are spikes and dips in the graph. The missing age group dips into the negatives on certain days, possible due to the fact that for some of these cases, the age group they belonged to was found; however, after some careful analysis, it was hard to determine where the missing data went to since the case numbers of each age group were around the same amount as they were prior, so I assumed it was distributed equally between the four other age groups.
The dashed gray vertical lines in the graph represent important dates in California (e.g. mandates enacted, public spaces opening/closing, etc.) and the dark red dotted vertical lines represent 2 weeks afterwards.
<p align=“center”>
  <img src="https://github.com/nguyenbel/CA-Age-Groups-and-Covid-19/blob/master/img/DailyNewConfirmedCasesinCalifornia.png">

  <img src="https://github.com/nguyenbel/CA-Age-Groups-and-Covid-19/blob/master/img/CA_important_dates_updated.png">
</p>

### Identifying New Confirmed Cases for each Age Group
As shown in the table below, cases for each age group rose significantly from when the data was recorded for each age group on April 2, 2020 to the current date, December 17th, 2020. The number of daily new confirmed positive cases rose for each age group rose significantly, with notable mentions to the 18-49 age group having approximately 30 times the amount of cases it had back in April. Of course, due to better testing efforts implemented within the state, the numbers that we have seen after the end of May might be more accurate compared to the numbers given at the beginning of the pandemic since these may be lower than they actually are. 

| Date          | Age Group    | Total Positive Cases| New Confirmed Cases |
| ------------- |--------------| :------------------:| :------------------:|
| 2020-04-02    | 0-17         | 120                 | 17                  |
| 2020-04-02    | 18-49        | 5302                | 748                 |
| 2020-04-02    | 50-64        | 2879                | 406                 |
| 2020-04-02    | 65 and Older | 2342                | 330                 |
| 2020-04-02    | Missing      | 58                  | 8                   |

| Date          | Age Group    | Total Positive Cases| New Confirmed Cases |
| ------------- |--------------| :------------------:| :------------------:|
| 2020-12-16    | 0-17         | 208045              | 5221                |
| 2020-12-16    | 18-49        | 1043558             | 23502               |
| 2020-12-16    | 50-64        | 331246              | 8031                |
| 2020-12-16    | 65 and Older | 180273              | 4243                |
| 2020-12-16    | Missing      | 1252                | 15                  |


### Proportions of Positive Cases with respect to Age Group Population and New Cases for each Age Group with respect to Total New Cases in California
Although the numbers may be skewed, one fact still remained true: Californians from the ages of 18-49 years old had the most daily new cases of Covid-19 out of all of the age groups. This can be attributed to one main factor: this age group is, by far, the largest age group (spanning 31 years of different ages). However, when looking at the age group proportion (number of positive cases in the age group over the age group population), approximately 6% of people from 18-49 years old still tested positive for Covid-19. The proportions are shown below.

| Date          | Age Group    | (Positive Cases) / <br /> (Age Group Population) | (New Cases by Age) / <br /> (Total New Cases) |
| ------------- |--------------| :------------------:| :-------------------:|
| 2020-04-02    | 0-17         | 0.00001             | 0.011258            |
| 2020-04-02    | 18-49        | 0.00030             | ***0.495364***      |
| 2020-04-02    | 50-64        | ***0.00040***       | 0.268874            |
| 2020-04-02    | 65 and Older | ***0.00040***       | 0.218543            |
| 2020-04-02    | Missing      | N/A.                | 0.005298            |


| Date          | Age Group    | (Positive Cases) / <br /> (Age Group Population) | (New Cases by Age) / <br /> (Total New Cases) |
| ------------- |--------------| :------------------:| :-------------------:|
| 2020-12-16    | 0-17         | 0.02305             | 0.127304            |
| 2020-12-16    | 18-49        | ***0.05999***       | ***0.573052***      |
| 2020-12-16    | 50-64        | 0.04566             | 0.195821            |
| 2020-12-16    | 65 and Older | 0.03090             | 0.103458            |
| 2020-12-16    | Missing      | N/A                 | 0.000366            |
  

## Chi-Square Goodness of Fit Test:
*Question*: Is the positive cases for each age group in California a sample of the positive cases for each age group in the United States?

To answer this question, I ran a Chi-Square Goodness of Fit Test. Using the most recent observed positive cases from California and multiplying the percentages of positive cases for each age group in the United States and the total positive cases in California, I created the following table:

| Age Group    | Observed Cases in California | Expected Cases in California |
| ------------ |------------------------------| -----------------------------|
| 0-17         | 208045                       | 181748                       |
| 18-49        | 1043558                      | 960402                       |
| 50-64        | 331246                       | 359721                       |
| 65 and Older | 180273                       | 252994                       |
| Missing      | 1252                         | 9528                         |

_Result_: After running the Chi-Square Goodness of Fit Test, I found that the positive cases for each group in California is not a sample of the positive cases for each age group in the United States.

## Conclusions
<p align=“center”>
  <img src="https://github.com/nguyenbel/CA-Age-Groups-and-Covid-19/blob/master/img/slow_spread.jpeg">
</p>
Although efforts to mitigate the spread of Covid-19 have had some effect on slowing down the spread of Covid-19 have been somewhat successful (e.g. stay-at-home orders, slowly reopening the public and closing it down when things got worse), there still needs to be some effort in enforcing the stay-at-home orders and something in affect to help those who were impacted by Covid-19 financially (e.g. laid off, hours cut, etc.), especially people of the ages 18-49. Additionally, there was no indication that the positive cases for each group in California is not a sample of the positive cases for each age group in the United States.

## Future Analysis
- Figuring out where the missing age group data went (is it equally distributed?)

## References
California Department of Public Health. 2020. California Total Covid-19 Cases. Retrieved from <https://data.ca.gov/dataset/covid-19-cases/resource/926fd08f-cc91-4828-af38-bd45de97f8c3>

California Department of Public Health. 2020. California Total Covid-19 Cases - Age Demographics. Retrieved from <https://data.ca.gov/dataset/covid-19-cases/resource/339d1c4d-77ab-44a2-9b40-745e64e335f2>

Centers for Disease Control and Prevention. 2020. Demographic Trends of COVID-19 cases and deaths in the US reported to CDC. Retrieved from <https://covid.cdc.gov/covid-data-tracker/#demographics>

U.S. Census Bureau (2019). Sex by Age American Community Survey 1-year estimates. Retrieved from <https://censusreporter.org/data/table/?table=B01001&geo_ids=04000US06,01000US&primary_geo_id=04000US06#valueType|estimate>

California Dept. of Finance, Population Estimates and Projections. 2020. U.S. Census Bureau, Population and Housing Unit Estimates. Retrieved from <https://www.kidsdata.org/topic/34/child-population-age-gender/table#fmt=141&loc=2&tf=110&ch=1433,926,927,1434,1435,372,78,77,79&sortColumnId=0&sortType=asc>

Cal Matters. Timeline: California reacts to coronavirus. Retrieved from <https://calmatters.org/health/coronavirus/2020/04/gavin-newsom-coronavirus-updates-timeline/>