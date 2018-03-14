# 432 Homework 6 for Spring 2018

Submit your response via [canvas.case.edu](https://canvas.case.edu/) no later than **1 PM on Friday 2018-04-06**. Your response should include an R Markdown file and an HTML document that is the result of applying your R Markdown file. 

- Remember to **ask for help** if you are stuck, first by Googling, or visiting the wonderful cheatsheets under the Help menu on the top bar of R Studio, and then by contacting `431-help at case dot edu` or visiting TA office hours.
- Start a separate R Project for Homework 6 as your first step, and place all of your work in that project's directory.

## Data Set for this Assignment

The `oh_counties_2017.csv` data set I have provided describes a series of variables, pulled from the data for the 88 counties of the the State of Ohio from the [County Health Rankings](http://www.countyhealthrankings.org/rankings/data/oh) report for 2017. 

- You may also be interested in looking at the details of the [2017 Ohio Summary report (pdf)](http://www.countyhealthrankings.org/sites/default/files/state/downloads/CHR2017_OH.pdf), or at the [Excel data file](http://www.countyhealthrankings.org/sites/default/files/state/downloads/2017%20County%20Health%20Rankings%20Ohio%20Data%20-%20v2.xls) from which I created the `oh_counties_2017.csv` file. 
- Note that the 2018 data and report were released recently, but we will concentrate in this assignment on the 2017 results.

The available variables are listed below.  Each variable describes data at the **COUNTY** level.

Variable | Description
-----------: | ------------------------------------------------------------------------------
fips | Federal Information Processing Standard code
county | name of County
years_lost_rate | age-adjusted years of potential life lost rate (per 100,000 population)
sroh_fairpoor | % of adults reporting fair or poor health (via BRFSS)
phys_days | mean number of reported physically unhealthy days per month
ment_days | mean number of reported mentally unhealthy days per mo
lbw_pct | % of births with low birth weight (< 2500 grams)
smoker_pct | % of adults that report currently smoking
obese_pct | % of adults that report body mass index of 30 or higher
food_env | indicator of access to healthy foods (0 is worst, 10 is best)
inactive_pct | % of adults that report no leisure-time physical activity
exer_access | % of the population with access to places for physical activity
exc_drink | % of adults that report excessive drinking
alc_drive | % of driving deaths with alcohol involvement
sti_rate | Chlamydia cases / Population x 100,000
teen_births | Teen births / females ages 15-19 x 1,000
uninsured | % of people under age 65 without insurance
pcp_ratio | Population to Primary Care Physicians ratio
prev_hosp | Discharges for Ambulatory Care Sensitive Conditions/Medicare Enrollees x 1,000
hsgrads | High School graduation rate
unemployed | % of population age 16+ who are unemployed and looking for work
poor_kids | % of children (under age 18) living in poverty
income_ratio | Ratio of household income at the 80th percentile to income at the 20th percentile
associations | # of social associations / population x 10,000
pm2.5 | Average daily amount of fine particulate matter in micrograms per cubic meter
h2oviol | Presence of a water violation: Yes or No
sev_housing | % of households with at least 1 of 4 housing problems: overcrowding, high housing costs, or lack of kitchen or plumbing facilities
drive_alone | % of workers who drive alone to work
age-adj-mortality | premature age-adjusted mortality
dm_prev | % with a diabetes diagnosis
freq_phys_distress | % in frequent physical distress
freq_mental_distress | % in frequent mental distress
food_insecure | % who are food insecure
insuff_sleep | % who get insufficient sleep
health_costs | mean health care costs
median_income | median income
population | population size 
age65plus | % of population who are 65 and over
african-am | % African-American
hispanic | % of Hispanic/Latino ethnicity
white | % White
female | % Female
rural | % of people in the county who live in rural areas 

# Question 1 (20 points)

Create a visualization (using R) based on some part of the `oh_counties_2017.csv` data set, and share it (the visualization and the R code you used to build it) with us. The visualization should be of a professional quality, describe information from at least three different variables listed above, include proper labels and a title, as well as a caption of no more than 50 words that highlights the key result. Although you may fit a model to help show patterns, your primary task is to show **the data** in a meaningful way, rather than to simply highlight the results of a model.

- You are welcome to find useful tools for visualizing data in R that we have yet to see in the slides in class.
- We will grade Question 1 strictly based on the quality of the visualization, its title and caption, in terms of being attractive, well-labeled and useful for representing the County Health Rankings data for Ohio, and how well it adheres to general principles for good visualizations we've seen in 431 and 432.

# Question 2 (20 points)

Write an essay (between 100 and 200 words) describing the creation and meaning of the visualization you created in Question 1, providing us with the context we need to understand why this is a useful visualization.  In your short description, be sure to address:

- How does this visualization help its audience understand the data better? 
- Why is this particular visualization effective, and what are the design features it uses that we can learn from to help us make more effective visualizations?
 
## Note - for Questions 3-5

For Questions 3-5, you're going to develop a series of models using **86** of the counties (every county other than Cuyahoga County and Monroe County). In each case, you will fit and select a model using that sample of 86 counties, and then be asked to use that model to make predictions of the outcome of interest for Cuyahoga County and for Monroe County and to assess the quality of those predictions.
 
# Question 3 (20 points)

Build a reasonable generalized linear model in your development sample (86 counties) to predict one of the outcomes in the `oh_counties_2017.csv` data set that describes a percentage (that must fall between 0 and 100) effectively using at least three and no more than 6 other variables from the list above. Demonstrate how well the model fits as well as the conclusions you draw from the model carefully. Be sure to discuss model assumptions. Then use the model to predict Cuyahoga County and Monroe County results, and assess the quality of those predictions.

# Question 4 (20 points)

Divide the 86 counties in your development sample into three groups (low, middle and high) in a rational way in terms of the `years_lost_rate` outcome. Make that new grouping your outcome for an ordinal logistic regression model. Fit a model (using a carefully selected group of no more than 5 predictor variables) and assess its performance carefully. Do not include the `age65plus` variable as a predictor, as the `years_lost_rate` data are age-adjusted already. Demonstrate how well the model fits as well as the conclusions you draw from the model carefully. Be sure to discuss model assumptions. Then use the model to predict Cuyahoga County and Monroe County results, and assess the quality of those predictions.

# Question 5 (20 points)

Build a new outcome variable that is a count (possible values = 0-4) of whether the county meets each of the following standards:

- the county has a `smoker_pct` value **below** the Ohio-wide average of 22
- the county has an `obese_pct` value **below** the Ohio-wide average of 31
- the county has an `exer_access` value **above** the Ohio-wide average of 83
- the county has **NOT** had a water violation in the past year (as shown by `h2oviol` = No)

To illustrate, consider these five counties:

County | `smoker_pct` | `obese_pct` | `exer_access` | `h2oviol` | Standards Met
-------------: | --------: | --------: | --------: | --------: | --------:
*Standard* | < 22 | < 31 | > 83 | No | --
Highland | 23.73 | 32.1 | 57.66 | Yes | 0
Erie | **18.99** | 35.4 | 80.04 | Yes | 1
Ashland | **19.79** | **27.9** | 64.65 | Yes | 2
Athens | 23.34 | **28.3** | **85.00** | **No** | 3
Cuyahoga | **18.70** | **30.0** | **95.55** | **No** | 4


Fit a Poisson regression model in your development sample to predict this count, using at least 3 and no more than 6 other predictors available in the data set. Note that a Poisson model isn't a great choice here, because it's difficult to believe that the four standards being described here are independent of each other, but we'll fit it anyway. Demonstrate how well the model fits as well as the conclusions you draw from the model carefully. Be sure to discuss model assumptions. Then use the model to predict Cuyahoga County and Monroe County results, and assess the quality of those predictions.
