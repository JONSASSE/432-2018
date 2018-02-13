# 432 Class 09: 2018-02-13

### Key Materials

- [The slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class09) are posted above (including some of the material originally scheduled for Class 08.) I expect that we'll get through a bit more than half of these slides, and that the rest will be covered in Class 10.
- The [audio files](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class09) will be posted as soon as they are available.

In today's class, we'll continue our discussion of logistic regression.

## Announcements Before Class 09

1. [Homework 4](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw4) is due at 1 PM on Friday 2018-02-16.
    - The ambiguity regarding controlling for smoking, for instance, is deliberate. You need to make a decision about what best to include in your model, and justify that decision. All I'll say is that there is more than one possible appealing approach.
    - The Homework 3 answer sketch and a draft of the grading rubric [are now available](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw3).
    - [Grades on HW2](https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw2/hw2grades.pdf) are now available, too.

2. Your [project 1 proposal](https://github.com/THOMASELOVE/432-2018/blob/master/projects/project1/README.md#the-proposal) is due at noon  Monday, 2018-02-19.

3. R Studio version 1.1.423 [is now available](https://www.rstudio.com/products/rstudio/download/#download). I updated.

4. No substantial progress on the [Course Notes](https://thomaselove.github.io/432-notes/) this week. Only change is a typo repair in section 10.3.1, about simultaneous confidence intervals in an `ols` fit.

## Minute Papers after Class 08 (n = 35/41)

Thanks very much to the 35 of you who completed the task. I appreciate it.

### What was the most important thing you learned related to 432 this week?

The most common responses describe:

- Logistic Regression, including
    + What a logistic regression actually does, and how it differs from a linear regression model, and its constraints
    + How to fit a logistic regression with `glm` and interpreting in terms of probability and odds thanks to the logit link
- The Spearman rho-squared plot and the notion of "spending" degrees of freedom with care
    + Note that this is about adding non-linear terms, and not really about selecting variables to include or exclude
- Fitting non-linear predictors / features with splines and polynomials

Other responses included:

- Improved my knowledge of visualization of data and exploratory data analysis.
- The 20:1 rule
- The impact and importance of sample size on/for regression modeling.
- Careful and thoughtful exploration of variables prior to jumping into modeling really pays off
- I learned a way to directly import data from the data and codes section of the Github page we use.
- Using the forcats and dplyr packages more independently
- ROC curve analysis

### Project 1

#### Tell me about your progress towards getting data for Project 1

Count | Description
----: | --------------------------------------------------------------------------------------------------
13 (37%) | I have a data set in hand that I can use that is shareable with the world, of appropriate size. 
19 (54%) | I have a data set in mind, but I don't have the data in my hands yet.
3 (9%) | I don't yet have a data set in mind. I need to get going on that.

#### Have you looked at the Sample Project 1 Proposal document yet?

Count | Description
----: | --------------------------------------------------------------------------------------------------
27 (77%) | Yes, I've looked at what's involved outside of a class demonstration.
8 (23%) | Not yet. I should do that soon.

#### Have you opened the Project 1 Template and typed in any new information yet?

Count | Description
----: | --------------------------------------------------------------------------------------------------
5 (14%) | Yes, I've opened the template and done something.
30 (86%) | Not yet. I should do that soon.

