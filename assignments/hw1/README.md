# 432 Homework 1 for Spring 2018

Submit your response **via canvas.case.edu no later than **noon on Friday 2018-01-26**. Your response should include an R Markdown file and an HTML document that is the result of applying your R Markdown file to the `hbp330.csv` data. Start a separate R Project for this assignment, as your first step.

This assignment involves the `hbp330.csv` data set, available on the Data and Code page, and also above. The data describe 330 patients with hypertension (high blood pressure) diagnoses who receive care in one of two practices. The data are based on real clinical information, but with a small amount of noise included in all data.

The available information includes:

Variable    | Description
----------: | --------------------------------------------------------------------------------------------------------
`subject`   | separate code for each subject (A001 = first patient in practice A)
`practice`  | primary care practice, labels are A and B
`provider`  | primary care provider (14 levels, each practice has 7 providers in these data)
`age`       | subject's age as of 2018-01-01
`race`      | subject's race (4 levels: Asian/P[acific] I[slander], Black / A[frican]-A[merican], White, Multi-Racial)
`eth_hisp`  | is subject of Hispanic/Latino ethnicity? Yes or No
`sex`       | subject's sex (F or M)
`insurance` | subject's primary insurance (Medicare, Commercial, Medicaid, Uninsured)
`income`    | estimated median income of subject's home neighborhood (via American Community Survey, to nearest $100)
`hsgrad`    | estimated % of adults who are high school graduates in subject's home neighborhood (ACS, to nearest %)
`tobacco`   | tobacco use status (current, former, never)
`depdiag`   | does subject have depression diagnosis? Yes or No
`height`    | subject's height in meters, rounded to two decimal places
`weight`    | subject's weight in kilograms, rounded to one decimal place
`ldl`       | subject's LDL cholesterol level, in mg/dl
`statin`    | does subject have a current prescription for a statin medication? 1 = Yes or 0 = No
`bpmed`     | does subject have a current prescription for a blood pressure control medication? 1 = Yes or 0 = No
`sbp`       | subject's most recently obtained systolic blood pressure, in mm Hg
`dbp`       | subject's most recently obtained diastolic blood pressure, in mm Hg

## Question 1. 

Build a Table 1 to compare the subjects in practice A to the subjects in practice B on the following nine variables: age, race, Hispanic ethnicity, sex, primary insurance, body mass index, BMI category, and systolic and diastolic blood pressure. Make the Table as well as you can within R, and display the result as part of your HTML file.

- Note that you'll have to deal with some missingness in the data, in an appropriate way. Be sure to specify what you did with the missing data (and how much you had to deal with) in a footnote to the table.
- Be sure, too, to make reasoned choices about whether means and standard deviations or instead medians and quartiles are more appropriate displays for the quantitative variables, and whether or not to use exact tests for categorical ones. Include your reasons in a footnote to the table.
- Note that body mass index (BMI) and BMI category are not supplied in the data, although you do have height and weight. 
- For BMI categories, use the four groups specified in the [How is BMI interpreted for Adults section of this description](https://www.cdc.gov/healthyweight/assessing/bmi/adult_bmi/index.html) of Adult BMI by the Centers for Disease Control.

## Question 2.

Does which **practice** a person attends seem to have a meaningful impact on their **systolic blood pressure**, adjusting for whether or not they are on a **blood pressure medication**? Decide whether your model should include an interaction term sensibly, and then fit your choice of model and interpret and display the findings carefully. Be sure to provide a written explanation of your findings, in complete sentences.

## Question 3.

Does the addition of the subject's **age** add meaningful predictive value to the model you developed in question 2? Does it change the nature of the conclusions you can draw from the model? How do you know?  Be sure to provide a written explanation of your findings, in complete sentences, to accompany any output you choose to include.

## Question 4.

Please specify your GitHub user name. If you don't have a (free) GitHub account, get one.


