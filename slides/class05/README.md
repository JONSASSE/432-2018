# 432 Class 05: 2018-01-30

### Key Materials

[The slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class05), and the [audio files](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class05) will be posted above when they become available.

In today's class, we'll focus on model selection via best subsets and on cross-validation.

## Announcements Before Class 05

1. R Studio version 1.1.419 is now [available for download](https://www.rstudio.com/products/rstudio/download/#download). You probably want to do so.

2. Homework 1 and Grading, in general. 
    - The [Homework 1 Answer Sketch](https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw1/README.md) is now available in R Markdown, HTML and PDF.
    - The [Grading Rubric](https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw1/README.md) is also available.
    - Once Homework 1 has been graded, we'll post grades and a few TA comments, in a list, with students identified by HW ID number.
        + By the time Class 5 begins, you should have received an email from Professor Love with your HW ID number.
    - Should you have questions about the Homework's concepts or other **non-grading** issues, please contact us at 431-help or in office hours.
        + The TAs are available to help you understand an appropriate way to tackle each problem, and also to help you understand potential concerns related to your answer.
    - But if you have questions about **grading**, you'll submit those to Dr. Love for all homework assignments, in a batch.
        + Dr. Love takes care of regrading requests in a batch at the end of the term. Fill out [this Google Form](https://goo.gl/forms/aQNPnlAWGIn72a7h1) before noon on Wednesday 2018-05-09 to request a regrade of any homework assignment.
        + If you've already got an A in the course without any additional credit on homework assignments, then Dr. Love won't bother to review your regrading requests in May, but if you don't have an A yet, he will do so very carefully after noon on 2018-05-09.
        + Please **don't** expect the TAs to address grading issues: Dr. Love will do that, at the end of the semester.

3. Here's a little progress report on course materials.
    1. We've corrected typos in Chapters 3, 4, 6 and 7 of the [Course Notes](https://thomaselove.github.io/432-notes/), all found by students. Thanks!
    2. There were some minor additions (hints, really) to [Homework 2](https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw2/README.md) this weekend.
    3. [Homework 3](https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw3/README.md) and [Homework 4](https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw4/README.md) and [Homework 5](https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw5/README.md) are now available, too. So you're set for HW through February.

4. Deadline Questions? Check the [SCHEDULE](https://github.com/THOMASELOVE/432-2018/blob/master/SCHEDULE.md), please. 

5. Here's a hint for question 3 in [Homework 2](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw2), which I've added [to the assignment](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw2) as well. 
    - R may well warn you about something like "singularities" in your output, but we'd like a clearer answer than that from you. 
    - To obtain it, look at the output, and then look at your data. 
    - Looking at the output is easy-ish. To look at the data, consider specifically the value of counting things. 
    - In particular, ask yourself questions like "How many people fall into the levels of the product term I've created?" or "What if I build a table, say with race in the rows and insurance in the columns - how many people fall into each cell of that table?" as a way to figure out what the real problem is in terms more understandable than R's warning message.

## Minute Papers after Class 04 (40/42 responses; THANK YOU!)

### What was the most important thing you learned related to 432 this week? (edited responses)

- Dealing with product terms (interactions) in linear regression models: interpretation, running them
- Two-Way ANOVA models with interaction and the related Means Plots
- Simple imputation for missing data
- Building Table 1
- Criteria for comparing several linear regression models to each other
- When to use a logistic regression model, as opposed to a linear regression model
- Stepwise regression (forward selection and backwards elimination)
- Centering and rescaling predictors in a regression model
- Cross-validation of a regression model
- Using Tukey's HSD (Honestly Significant Differences) approach for pairwise comparisons of subgroup means
- "Plot, early and often"

### How confident are you about your ability to successfully complete Homework 1, due Friday 2018-01-26 at 1 PM?

Response | Count | %
--------------------------------------: | -----: | -----:
I've already submitted the assignment | 27 | 67.5%
I'm very confident about it | 9 | 22.5%
I'm somewhat confident about it | 4 | 10%
I'm not confident about it | 0 | --

### Have you completed the required reading in Jeff Leek's book on "Data Sharing" and on "Scientific Code" as described on [the course schedule](https://github.com/THOMASELOVE/432-2018/blob/master/SCHEDULE.md)?

Response | Count | %
--------------------------------------: | -----: | -----:
Yes, and in fact I've read some other parts of the book, too. | 5 | 12.5%
Yes, I'm up to date, but I haven't read any other parts of the book. | 19 | 47.5%
No, but I'll get to that soon, because it'll help me do my project. | 16 | 40%

### What question(s) remain uppermost in your mind at this point? (edited responses)

1. When should we center and/or rescale predictors?
    - It's especially helpful when you are trying to interpret an interaction term between a factor and a quantitative variable, or when you are trying to describe the importance of each of a set of predictors with different scales in a model, to answer questions like "does BMI or SBP have a bigger association with my outcome"?
2. Is ANOVA a useful approach for variable selection in a linear regression model? When using ANOVA to compare two models with one nested in the other, if there is statistically significant value, does it mean the bigger model is better or the other model is better?
    - If you compare two **nested** models (so, say model 1 is A, B and C and model 2 is A, B, C, D, E, and F) and find a significant difference between them, it means that D, E, and F add significant value over and above what you get from model 1.
    - But, of course, statistical significance of a predictor set within the sample in which you built the model is just one approach to finding a good model, or declaring one model better than another. A useful step, but it leaves out prediction in new data, for instance.
    - And if the models you want to compare aren't **nested**, ANOVA is not especially helpful in sorting out the issues involved.
3. How do we decide if an interaction term is worth including in a model, or not worth including?
    - Relevant approaches include 
        - face validity (if the interaction is an important part of the underlying theory behind the data analysis)
        - tests of statistical significance (via t test of the interaction term in the simplest case of two factors each with two levels, or via sequential `anova` testing of the group of variables included in the interaction term
        - comparisons of model fit with and without the interaction within the sample used to estimate models (including AIC, BIC and adjusted R^2^)
        - comparisons of model prediction quality via cross-validation, comparing the models with and without interaction using the root mean squared prediction error, and the mean absolute prediction error, and yes, I'll talk more about this in the days to come.
4. Does it make sense to use categorical variables to predict numeric ones?
    - Sure. Which would you predict to be taller knowing nothing else about them: a 25-year old man or a 25-year old woman?
    - But of course, sex is a categorical variable, and height is a numeric one. So it's the same idea in other settings.
5. How do we deal with interactions of three or more variables at one time?
    - Build more complicated product terms. This gets harder and harder to graph effectively, though, so that's a real challenge.
6. If we run an ANOVA model (i.e. all predictors are categorical) then our residuals plots look strange, particularly the residuals vs. fitted plots and the scale-location plots. How do we deal with this?
    - Focus on the interaction plots (means plots with standard deviation bars) to assess directly whether non-linearity (in the form of an interaction) is important, and on whether there are meaningful differences in variation across the groups (heteroscedasticity.)
    - You can run the same means plots on the residuals, too.
7. If we could possibly use a piece of information (like BMI) either as a categorical predictor or a continuous one, the continuous one is more appealing if you want to do prediction, right, because with the categorical version, our predictions will clump together?
    - Right. You throw away a lot of data every time you cluster a quantitative predictor into a categorical representation. If your goal is effective prediction, that's almost never a good idea. Use the most granular form of a predictor that you can is the best course.
8. Is stepwise regression ever useful? Do you ever use forward selection, or always backwards elimination.
    - Sure. Lots of times it's helpful to get a quick-and-dirty answer, practically. I've used three different methods - those described in the Course Notes. We'll touch on all three this week.
    - If you're really trying to settle on one "best" model, though, there's no reason stepwise should be your only answer.
9. When is it better to use simple imputation rather than complete case analyses? Which of the many available imputation methods in `simputation` should I choose? How does multiple imputation fit in?
    - I need time to write a chapter about some of these points. Haven't found it yet. I will before we're done.
    - A related question is "how much missingness can I ignore" - the answer is that it depends on what's missing and what questions you're trying to answer. Bluntly, I don't like trying to impute outcomes or key predictors, but I impute covariates all the time.
    - Some of you may be expecting that you'll get a very simple and clear answer about what to do with missing data from me. Disabuse yourself of that notion. I won't provide a universal response that works in every setting, but we will spend meaningful time with real data problems, and discuss some useful approaches to getting a handle on the impact of missingness on your conclusions. Best I can do.
10. How can we fit a prediction model that is non-linear in the predictors? Is this related to using splines and polynomial functions?
    - Yes, and it's coming next week.
11. When are we going to be getting to logistic regression? What other types of regression models will we learn in the course?
    - Check out [the Schedule](https://github.com/THOMASELOVE/432-2018/blob/master/SCHEDULE.md), which lists dates for logistic regression and for generalized linear models.
    - For details on types of models, I can only point you to the (incomplete) [Topics page](https://github.com/THOMASELOVE/432-2018/blob/master/TOPICS.md).
12. The matrix business in R4DS 23.4 is intimidating. Will you be going over this?
    - Not much, no. Some of what I've assigned you in R4DS is critical. Those things will also get discussed in class as they come up. Others provide more details for people who are getting involved in specific issues related to their projects, mostly. Those may or may not get discussed in class. We'll talk about 23.4.4.'s topic - transformations next week.
13. Are R and R Studio pretty stable? I'm worried I'll be updating all the time...
    - It is my intent to use only stuff in this class that I have personally tested on both a Mac and a PC using the minimum requirements listed on the [main Data and Code page](https://github.com/THOMASELOVE/432-2018/tree/master/data-and-code). I can make no further promises than that about what will and won't be an issue for you personally. This is part of the reason we have 6 TAs. 
    - There will be a new version of R coming in the Spring, I assume R 3.4.0. No one yet knows when, but a typical release date would be in early March. 
    - R Studio updates more frequently, but I didn't go to the [r-studio::conf2018](https://www.rstudio.com/conference/) this week (instead, I'm here with you!) so I don't have the inside scoop yet.
