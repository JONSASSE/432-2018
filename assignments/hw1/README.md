# 432 Homework 1 for Spring 2018

## Links to Post-Deadline Materials will go live as they become available

- Answer Sketch: [Download R Markdown](https://raw.githubusercontent.com/THOMASELOVE/432-2018/master/assignments/hw1/hw1sketch.Rmd), or [View HTML result](http://htmlpreview.github.io/?https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw1/hw1sketch.html), or [Download or View PDF result](https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw1/hw1sketch.pdf)
- Grading Rubric [is now available](https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw1/hw1rubric.md).
- Google Spreadsheet Containing Grades, Arranged by HW-ID number (Check your email.)

## The Actual Assignment

Submit your response via [canvas.case.edu](https://canvas.case.edu/) no later than **1 PM on Friday 2018-01-26**. Your response should include an R Markdown file and an HTML document that is the result of applying your R Markdown file to the `hbp330.csv` data. 

Start a separate R Project for Homework 1, as your first step, and place the data in that project's specific directory.

This homework involves the `hbp330.csv` data set, available for download at [the Data and Code page](https://github.com/THOMASELOVE/432-2018/tree/master/data-and-code), and also above. 

The data describe 330 patients with hypertension (high blood pressure) diagnoses who receive primary care in one of two practices. The data are based on real clinical information, but with a small amount of noise included in every variable.

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
`hsgrad`    | estimated percentage of adults living in the subject's home neighborhood who have graduated from high school (via American Community Survey, to the nearest percent)
`tobacco`   | tobacco use status (current, former, never)
`depdiag`   | does subject have depression diagnosis? Yes or No
`height`    | subject's height in meters, rounded to two decimal places
`weight`    | subject's weight in kilograms, rounded to one decimal place
`ldl`       | subject's LDL cholesterol level, in mg/dl
`statin`    | does subject have a current prescription for a statin medication? 1 = Yes or 0 = No
`bpmed`     | does subject have a current prescription for a blood pressure control medication? 1 = Yes or 0 = No
`sbp`       | subject's most recently obtained systolic blood pressure, in mm Hg
`dbp`       | subject's most recently obtained diastolic blood pressure, in mm Hg

## Question 1. (40 points)

Build a Table 1 to compare the subjects in practice A to the subjects in practice B on the following nine variables: age, race, Hispanic ethnicity, sex, primary insurance, body mass index, BMI category, and systolic and diastolic blood pressure. Make the Table as well as you can within R, and display the result as part of your HTML file. **Include a description of the results of your Table 1 that does not exceed 100 words, using complete English sentences**.

- Be sure that your table specifies the number of subjects in each practice.
- Note that you'll have to deal with some missingness in the data, in an appropriate way. Be sure to specify what you did with the missing data (and how much you had to deal with) in a footnote to the table. I would just list the notes as a bulleted list in the Markdown file, and never leave Markdown during the entire enterprise. It's not usually appropriate to report results that include imputation in a Table 1, so I expect the best choice is to build a note specifying the amount of missing data.
- Be sure, too, to make reasoned choices about whether means and standard deviations or instead medians and quartiles are more appropriate displays for the quantitative variables, and whether or not to use exact tests for categorical ones. Include your reasons in a footnote to the table.
- Note that body mass index (BMI) and BMI category are not supplied in the data, although you do have height and weight. **So, you'll have to calculate the BMI and add it to the data set.** If you don't know the formula for BMI, you have Google to help you figure it out.
- For BMI categories, use the four groups specified in the [How is BMI interpreted for Adults section of this description](https://www.cdc.gov/healthyweight/assessing/bmi/adult_bmi/index.html) of Adult BMI by the Centers for Disease Control. **Again, you'll need to use your calculated BMI values and then create the categories in your data set, and you'll need to figure out a way to accurately get each subject into the correct category.**

## Question 2. (30 points)

Does which **practice** a person attends seem to have a meaningful impact on their **systolic blood pressure**, adjusting for whether or not they are on a **blood pressure medication**? Decide whether your model should include an interaction term sensibly, and then fit your choice of model and interpret and display the findings carefully. Be sure to provide a written explanation of your findings, in complete sentences. Responses without graphs are not complete.

## Question 3. (25 points)

Does the addition of the subject's **age** add meaningful predictive value to the model you developed in question 2? Does it change the nature of the conclusions you can draw from the model? How do you know?  Be sure to provide a written explanation of your findings, in complete sentences, to accompany any output you choose to include. Responses without graphs are not complete.

## Question 4. (5 points)

Please specify your GitHub user name. If you don't have a (free) GitHub account, get one. If you sign up for a student account using your case.edu address, you will get access to unlimited (and free) private repositories. That's the ideal plan.


