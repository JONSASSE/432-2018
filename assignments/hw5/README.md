# 432 Homework 5 for Spring 2018

Submit your response via [canvas.case.edu](https://canvas.case.edu/) no later than **1 PM on Friday 2018-03-02**. Your response should include an R Markdown file and an HTML document that is the result of applying your R Markdown file. 

Start a separate R Project for Homework 5 as your first step, and place all of your work in that project's directory.

# Question 1 (25 points)

I have provided three essay prompts below. Select **one** of the three available prompts and answer it. Start the essay by clearly labelling the prompt you are using. We are looking for well-written, clear and thoughtful responses. Going a little over the suggested length is OK. Under is not OK.

- a) In the section on scientific blogging in Jeff Leek's *How to Be A Modern Scientist*, he remarks that "Everyone is an internet scientist now." In 5-10 complete English sentences, I want you to specify, using your own words and complete English sentences, one or two different ways in which you anticipate your work changing in light of this remark. What might you do differently, if you thought of yourself as an internet scientist? Do you, already, feel this way? Does this make being a scientist seem more or less appealing to you, and why? Please feel encouraged to provide an example from your own experiences that helps you explain your reactions to this idea.

- b) In 5-10 complete English sentences, I want you to specify, using your own words and complete English sentences, the least helpful piece of advice you took away from reading Jeff Leek's *How To Be A Modern Scientist*. Please provide a reference to the section of the book that provides this problematic advice. Please avoid selecting something because it does not apply to your current situation, but instead identify something that might be relevant to you, but that you are actually unwilling to do, and explain why. Please feel encouraged to provide an example from your own experiences that helps you explain why you are unwilling to take this piece of advice.

- c) Reread the section of Jeff Leek's *How To Be A Modern Scientist* on data sharing, where, among other things, he states that "the reproducibility debate is over." In 5-10 complete English sentences, I want you to specify how the "debate" over reproducibility has affected your field, and what changes you have made (or intend to make) in light of what you've learned in this course, from Leek's book, and from your experiences over the last year to make your work more reproducible. How important is building reproducible science in your field? In your view, what does "reproducible science" mean to you, and to the people you will be working with as you complete your degree program? Please feel encouraged to provide an example from your own experiences that helps you explain your reactions to the notion of reproducible science.

# The Data for Questions 2-9.

The data come from the [NHANES National Youth Fitness Survey](http://wwwn.cdc.gov/nchs/nhanes/search/nnyfs12.aspx). Data collected in the `nnyfs1.csv` file above and on the [Data and Code] page from our site come from the **Demographics** files, and from the **Medical Conditions** and **Physical Activity** files, which are each part of the **Questionnaire** data.

I merged files on the basis of the respondent sequence number (SEQN). The variables available to you are:

1. `SEQN` - the *respondent sequence number* (there are 1,576 subjects in the `nnyfs1.csv` file made available to you)
2. `RIASEX` (from the Demographics files) - *sex of subject (1 = male, 2 = female)*
3. `RIDAGEYR` (from the Demographics files) - *age in years at screening (3-15)*
4. `RIDRETH1` (from the Demographics files) - *race/hispanic origin (1 = Mexican-American, 2 = Other Hispanic, 3 = Non-Hispanic White, 4 = Non-Hispanic Black, 5 = Other Race including Multi-Racial)*
5. `INDFMPIR` (from the Demographics files; **impute** all subjects with missing values on the basis of `RIDRETH1` and `RIDAGEYR`) - *ratio of family income to poverty (data show 0-4.99, and then truncated as 5 for all who are in fact greater than or equal to 5)*
6. `MCQ010` (from the Medical Conditions files; all subjects should have values of 1 [Yes] or 2 [No]) - *has the child ever been told they have asthma*
7. `PAQ706` (from the Physical Activity files; **drop** all subjects with values other than 0, 1, 2, 3, 4, 5, 6, or 7) - *days (in the past 7) physically active at least 60 minutes* **I absolutely expect you to treat this as a quantitative variable in your modeling. It is a count, and should be treated as quantitative.**

# Question 2 (5 points)

How many of those subjects wind up in your final data set, after applying the inclusion and exclusion criteria described above?

# Question 3 (10 points)

Find the cross-product odds ratio and an appropriate 95% confidence interval for that odds ratio for being told you have asthma for females as compared to males within this sample. Specify the relevant cross-tabulation (contingency table).

# Question 4 (5 points)

Use a logistic regression model to predict the following binary outcome:

- Variable Name: `MCQ010` "Ever been told you have asthma" = YES [1] 

on the basis of the following variables:

- sex (captured in an indicator of `female`)
- subject's age at screening
- Ratio of family income to poverty
- Days physically active in the past 7

Specify the equation of the model you have fit.

# Question 5 (10 points)

Specify and interpret the model's odds ratio estimate for being told you have asthma for females as compared to males, after adjusting for the other variables included in the model you fit in Question 4. Provide a 95% confidence interval for this odds ratio.

# Question 6 (10 points)

Compare your result in Question 3 to your result in Question 5. Are they different? If so, why?

# Question 7 (10 points)

Specify and interpret the Question 4 model's odds ratio estimate (and a 95% confidence interval around that point estimate) associated with the "days physically active in the past 7" predictor. 

# Question 8 (10 points)

Use the model you fit in Question 4 to provide a prediction for the probability that a 10-year-old male child will have been told they have asthma, if they are active 3 days in the past 7, and have a ratio of family income to poverty of 2.5.

# Question 9 (15 points)

Refit the model you fit in Question 4 but now, add in an additional predictor variable that indicates if the subject's race/Hispanic origin value is Non-Hispanic White (i.e. RIDRETH1 = 3), or not. Decide whether or not an interaction term between age and race/ethnicity is required (but do not consider other interaction terms or other types of non-linearity). Specify the logistic regression equation you wind up fitting. 

