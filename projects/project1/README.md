# 432 Project 1 Instructions

As a substantial part of your course grade, you will complete two Projects this semester. This document describes Project 1. [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) is due at the end of the semester.

## Submission Guidelines and Deliverables

There are three Tasks associated with Project 1.

1. Your [proposal](https://github.com/THOMASELOVE/432-2018/blob/master/projects/project1/README.md#the-proposal) and [data](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project1#characteristics-of-an-acceptable-data-set).
    - You will identify a study of interest and write a brief proposal, which will include a .csv copy of your data, and an R Markdown file (with HTML result) addressing a set of nine pieces of information [described below](https://github.com/THOMASELOVE/432-2018/blob/master/projects/project1/README.md#the-proposal).
    - These proposals will be shared with your colleagues, so anonymity is impossible.
    - The proposal is due Monday 2018-02-19 at noon. Submission will be through [canvas](https://canvas.case.edu/)
2. Your [review](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project1#the-review-process) of the portfolios (in progress) of the colleagues in your Project 1 group. 
    - Using R Markdown, you will build a detailed portfolio of your work for Project 1 which can be used to replicate all of your main analyses, and which also includes a discussion of your reactions to the results. You will generate both the hardworking source code (the R Markdown) and the front-facing report (as HTML, likely) that comes from knitting your Markdown document. This will be posted online so that it can be viewed by evaluators.
    - You will be meeting (in person during class time as well as electronically) with your colleagues to give them feedback on their work in February and March.
    - You'll post a first draft of your work online by 2018-02-28 and you will review the work of your colleagues up through 2018-03-09.
3. Your [final portfolio](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project1#the-portfolio-due-2018-03-19-at-noon-submit-via-canvas) of analyses is due at noon on Monday 2018-03-19. 
    - At this time, you will submit your final data, Markdown file, and your HTML output, through [canvas](https://canvas.case.edu/)

## The Project 1 Template

**Coming Soon** An R Markdown template document **is available here** for this purpose. The template has headings for each of the nine tasks below. **Please** use this template in preparing your response, as it facilitates grading and redos.

## Sample Project

**Coming Soon** There is a complete sample project available for your review, built by Dr. Love.

## Introduction

It is hard to learn statistics (or anything else) passively; concurrent theory and application are essential. Expert clinical researchers and statisticians repeatedly emphasize how important it is that people be able to write well, present clearly, work to solve problems, and show initiative. This project assignment is designed to help you develop your abilities and have a memorable experience. 

Project 1 involves the development of linear and logistic regression models for a set of data that you will obtain.

## Characteristics of an Acceptable Data Set

In your project, you will be analyzing, presenting and discussing a pair of regression models, specifically a linear regression and a logistic regression, describing a data set you identify. 

1. **Shareable with the World**. The data must be available to you, and shared with me and everyone else in the world (without any identifying information) as a well-tidied .csv file on 2018-02-19. If the data is from another source, the source (web or other) must be completely identified to me. Ongoing projects that require anyone's approval to share data are not appropriate for Project 1, but are likely appropriate for Project 2. 
    - For Project 1, you may not use any data set that was used in 431, nor may you revisit your 431 project, and you cannot use any data sets used in the teaching materials for 432. You may not use any data set included in [an R package that we are installing](https://github.com/THOMASELOVE/432-2018/blob/master/data-and-code/PACKAGES.MD) this semester, other than NHANES. 
    - You are allowed to use NHANES data in Project 1 **or** in Project 2, but not in both.

2. **Size**. A **minimum** of 100 complete observations are required on each variable. It is fine if there are some missing values, as well, so long as there are at least 100 rows with complete observations on all variables you intend to use in each model. The **maximum** data set size is 1000 observations, so if you have something larger than that, you'll need to select a subset.

3. **Outcomes**. The columns must include at least one quantitative outcome and one binary categorical outcome. If necessary, the binary outcome can be generated from the quantitative outcome (as an example, your quantitative outcome could be resting heart rate in beats per minute, and your binary outcome could be whether the resting heart rate is below 70 beats per minute.)

4. **Inputs**. You will need at least four regression inputs (predictors) for each of your two models. At least one of the four must be quantitative (with a minimum of 10 different, ordered, observed values), *and* at least one must be multi-categorical (with at least 3 categories) for each model. Your other inputs can represent binary, multi-categorical or quantitative data. You can examine different candidate predictors for each outcome, or use the same ones in both your linear and logistic regression models. Depending on your sample size, you can study more regression inputs. Specifically, if you have N complete observations in your data set, you are permitted to study up to 4 + (N-100)/100 candidate regression inputs, rounding down.

## The Proposal, due Monday 2018-02-19 at noon. Submit via [canvas](https://canvas.case.edu).

Your proposal will include 
    - (a) a `.csv` file of the [data](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project1#characteristics-of-an-acceptable-data-set), 
    - (b) a R Markdown file built on **the Project 1 template** containing the information listed below, and 
    - (c) an HTML document which is the unedited result of knitting your Markdown file.

The nine pieces of information we should find in the Markdown and HTML versions of your proposal are:

1. Complete information on the source of the data: how did you get it, how was it gathered, by whom, in what setting, for what purpose, and using what sampling strategy.
2. Code to load the raw `.csv` file into a tibble, and tidy/clean up the data to be useful for your modeling work. 
3. A listing of the tibble, with all variables correctly imported (via your code) as the types of variables (factor/integer/numeric, etc.) that you need for modeling. Be sure that your listing specifies the number of rows and number of columns in your tidy data set.
4. A code book, which provides, for each variable in your tibble, the following information:
    + The name of the variable used in your tibble
    + The type of variable (binary, multi-categorical, quantitative)
    + The details for each variable 
        * if a categorical variable, what are the levels, and what % of subjects fall in each category
        * if a quantitative variable, what is the range of the data, and what are the units of measurement
        * if there are missing data, tell us how many observations are missing, and why, if you know why.
5. A description (one or two sentences) of who or what the subjects (rows) are in your data set.
6. A sentence or two for each variable (column) providing a description of what the variable measures or describes, in English.
7. A sentence or two telling us what you will use your linear regression model to explain or predict, *followed by* a sentence or several telling us very precisely which (quantitative) variable will serve as your outcome in your linear regression model, and which four (or more) candidate predictors you intend to use for that model.
8. A sentence or two telling us what you will use your logistic regression model to explain or predict, *followed by* a sentence or several telling us very precisely which (binary) variable will serve as your outcome in your logistic regression model, and which four (or more) candidate predictors you intend to use for that model.
9. An affirmation that the data set meets all of the requirements specified here, most especially that the data can be shared freely over the internet, and that there is no protected information of any kind involved. You need to be able to write "I am certain that it is completely appropriate for these data to be shared with anyone, without any conditions. There are no concerns about privacy or security." If you are unsure whether this is true, select a different data set.

### Evaluating the Project 1 Proposal

- Your project will be evaluated on a scale of 0-10, with one point for getting all of the necessary materials (.csv, .Rmd and HTML) in and then one additional point for each of the nine tasks if they are successfully completed. 
- If you receive a grade lower than 10, you will need to redo until you reach 10. Redos are expected within 48 hours of receipt of the redo request.

## The Review Process

You will be meeting with a group of 2-3 other people in the class to work through your project 1. You will post a "first draft" of your portfolio materials to [canvas](https://canvas.case.edu) before the end of February, and you will be reviewing and commenting on the work of your colleagues, both in person and electronically, up until noon on Friday 2018-03-09. More details in class.

## The Portfolio, due 2018-03-19 at noon. Submit via [canvas](https://canvas.case.edu).

Your final portfolio will include 
    - (a) a `.csv` file of the [data](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project1#characteristics-of-an-acceptable-data-set), 
    - (b) a R Markdown file built on **the Project 1 template** containing the information listed below, and 
    - (c) an HTML document which is the unedited result of knitting your Markdown file.

### The twelve tasks that should be included in the final portfolio.

These tasks should absolutely be built up from your proposal, by adding the last three sections. 

- 1-9. The materials from your proposal, after editing, as needed, to reflect what you actually did and clarifying any points of confusion.
- 10.  A section on your linear regression model. This should include all relevant code used to prepare your final results. We should be easily capable of finding:
    + Your approach to capturing potential non-linearity. What did the Spearman rho-squared plot suggest, and how did you spend your degrees of freedom?
    + Your variable selection process in developing the model, which should be more than just a stepwise approach. Why did you select the predictors you did? 
    + Your calibration and validation results. What is an appropriate estimate of the likely performance of this model for new data, according to a validated R-squared statistic?
    + An appropriate summary of the final model you landed on, including a listing of the equation, a description of the effect sizes, and an annotated nomogram with a demonstration of a prediction (and appropriate prediction interval) for a new subject of interest.
- 11. A section on your logistic regression model.
    + Your approach to capturing potential non-linearity. What did the Spearman rho-squared plot suggest, and how did you spend your degrees of freedom?
    + Your variable selection process in developing the model, which can be a stepwise approach here. Why did you select the predictors you did? 
    + Your calibration and validation results. What is an appropriate estimate of the likely performance of this model for new data, according to a validated C statistic?
    + An appropriate summary of the final model you landed on, including a listing of the equation, a description of the effect sizes, and an annotated nomogram with a demonstration of a predicted probability of having the outcome of interest for a new subject.
- 12. A 100-250 word discussion of your thoughts on the process. 
    + What was substantially harder or easier than you expected? 
    + What do you wish you'd known at the start of this process that you know now?
    + What was the most confusing part of doing the project?
    + What was the most useful thing you learned while doing the project?
