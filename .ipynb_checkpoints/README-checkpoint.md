<p align=“center”>
  <img src="https://github.com/nguyenbel/CA-Age-Groups-and-Covid-19/blob/master/img/people_wearing_masks.jpg">
</p>

# Covid-19 Positive Cases and California
Insight into which age group tests positive more often for Covid-19 in California. Is the positive cases for each age group in California a sample of the positive cases for each age group in the United States?

## Belinda Nguyen
[Linkedin](https://www.linkedin.com/in/bnguyen05/) * [Github](https://github.com/nguyenbel) * [Slides](https://github.com/nguyenbel/)

## Background and Motivation
Due to the Coranvirus (Covid-19), 2020 has been a strange year for everyone. Covid-19 is a new illness that can affect one's respiratory system and has similar symptoms to the flu. Many health experts advised people to wear a mask when they went out and to wash their hands for 20 seconds or to sanitize their hands frequently. The United States of America has had a hard time handling the pandemic due to poor leadership and the state governors are told that they are responsible to mitigate the spread of Covd-19 with little to no help from the Federal Government. On March 16, 2020, stay-at-home orders were put into place in California to slow the spread of Covid-19. California was often used as one of the examples of what a state should do to handle the pandemic.

This study analyzes the positive cases of Covid-19 in California between age groups. Which age group has the most daily new cases in California? What proportion of people in each age group tests positive with respect to the total population of their age group? Is the positive cases for each age group in California a sample of the positive cases for each age group in the United States?

## Data
### Description: 
Californiia Department of Public Health compiled a [data set](https://data.ca.gov/dataset/covid-19-cases) of Covid-19 cases in California and broke down the data into several categories: total cases, age demographic, sex demographics, and ethnicity demographics. I took the data for the total cases and the age demographic, then found data on the population of Californiia based on the age groups, and, finally, demographic trends of Covid-19 in the United States from the Centers for Disease Control and Prevention.

## Exploratory Data Analysis:

## Chi-Square Goodness of Fit Test:
*Question*: Is the positive cases for each age group in California a sample of the positive cases for each age group in the United States?

To answer this question, I ran a Chi-Square Goodness of Fit Test. Using the most recent observed positive cases from California and multiplying the percentages of positive cases for each age group in the United States and the total positive cases in California, I created the following table:
<p align=“center”>
  <img src="https://github.com/nguyenbel/CA-Age-Groups-and-Covid-19/blob/master/img/observed_vs_expected.png">
</p>
After running the Chi-Square Goodness of Fit Test, I found that the positive cases for each group in California is not a sample of the positive cases for each age group in the United States.

## Conclusions


## References
California Department of Public Health. 2020. California Total Covid-19 Cases. Retrieved from <https://data.ca.gov/dataset/covid-19-cases/resource/926fd08f-cc91-4828-af38-bd45de97f8c3>

California Department of Public Health. 2020. California Total Covid-19 Cases - Age Demographics. Retrieved from <https://data.ca.gov/dataset/covid-19-cases/resource/339d1c4d-77ab-44a2-9b40-745e64e335f2>

Centers for Disease Control and Prevention. 2020. Demographic Trends of COVID-19 cases and deaths in the US reported to CDC. Retrieved from <https://covid.cdc.gov/covid-data-tracker/#demographics>

U.S. Census Bureau (2019). Sex by Age American Community Survey 1-year estimates. Retrieved from <https://censusreporter.org/data/table/?table=B01001&geo_ids=04000US06,01000US&primary_geo_id=04000US06#valueType|estimate>

California Dept. of Finance, Population Estimates and Projections (May 2020); U.S. Census Bureau, Population and Housing Unit Estimates (Jul. 2020). Retrieved from <https://www.kidsdata.org/topic/34/child-population-age-gender/table#fmt=141&loc=2&tf=110&ch=1433,926,927,1434,1435,372,78,77,79&sortColumnId=0&sortType=asc>