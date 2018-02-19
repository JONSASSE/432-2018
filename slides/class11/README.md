# 432 Class 11: 2018-02-20

### Key Materials

- [The slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class11) are posted above. They include some leftover materials from Class 10 on logistic regression, followed by a discussion of linear regression using the `ols` function in the `rms` package. 
- The [audio files](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class10) will be posted as soon as they are available.

In today's class, we'll finish our discussion of the logistic regression models for the Framingham Heart Study that we began in Class 10. Then we'll discuss the use of the `ols` function and related materials from `rms` and `Hmisc` in fitting linear regression models, amplifying what you'll find in [Chapter 10 of the Course Notes](https://thomaselove.github.io/432-notes/using-ols-from-the-rms-package-to-fit-linear-models.html).

## Announcements Before Class 11

1. [Homework 4](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw4) is due at 1 PM on Friday, 2018-02-23.

2. Your [project 1 proposal](https://github.com/THOMASELOVE/432-2018/blob/master/projects/project1/README.md#the-proposal) is also due at 1 PM on Friday, 2018-02-23.

3. A coding tip: If you filter a data set in R to focus on specific levels of a factor, R retains all of those factor levels by default. If this is a problem, use the `droplevels` function. [See here](https://stackoverflow.com/questions/32059343/when-filtering-with-dplyr-in-r-why-do-filtered-out-levels-of-a-variable-remain) for more details.

4. Having trouble developing a reproducible example, or just need help asking a question? Take a look at the `reprex` package and [this help page](https://www.tidyverse.org/help/).

## Minute Papers After Class 10

### Project 1 Progress (n = 38/41)

#### Tell me about your progress towards getting data for Project 1

Count (%) | Description
---------: | -------------------------------------------------------------------------------------
32 (84%) | I have a data set in hand that I can use that is shareable with the world, of appropriate size.
6 (16%) | I have a data set in mind, but I don't have the data in my hands yet.
0 (0%) | I don't yet have a data set in mind. I need to get going on that.

#### Have you opened the Project 1 Template and typed in any new information yet?

Count (%) | Description
---------: | -------------------------------------------------------------------------------------
29 (76%) | Yes, I've opened the template and done something.
9 (24%) | Not yet. I should do that soon.

#### How confident do you feel about your ability to complete the Project 1 Proposal?

Count (%) | Score
---------: | -------------------------
11 (29%) | 5 = Extremely confident
17 (45%) | 4
8 (21%) | 3
2 (5%) | 2
0 (0%) | 1 = Not confident at all

Class Mean = 3.97

### What was the most important thing you learned related to 432 this week?

The most common responses were:

- ROC curve analysis for logistic regression
    + Estimating and interpreting the C statistic (the area under the curve)
- The difference between calibration and discrimination in thinking about the accuracy of a model's predictions.
- Using `lrm` to fit and evaluate a logistic regression model
- Using `glm` to fit and evaluate a logistic regression model.
- Interpreting a nomogram
- Plots to help understand missing data, specifically `naplot(naclus(datasetname))`

### What question(s) about the course are uppermost in your mind now?

1. There were several questions about discrimination and calibration. Here are a few key points, although we're not done talking about this in class:
    - A well-calibrated model shows predicted probabilities that agree well with observed probabilities of the outcome.
    - The Nagelkerke R-square and C statistics reflect the discrimination of a model, not its calibration.
    - A model that discriminates well will accurately place low-risk people below high-risk people, and will show a high C statistic, for example.
    - But we cannot use the C statistic alone to assess the quality of predictions our model makes, for instance, see [this paper by Nancy Cook](http://circ.ahajournals.org/content/115/7/928.full.pdf).
    - Some people think of calibration as "goodness of fit" and discrimination as "predictive power". Models can be 
    - Sometimes a poorly calibrated model could be improved by including interaction or other non-linear terms.
    - The most popular statistic for testing goodness of fit is the Hosmer-Lemeshow test, which has several problems associated with it as pointed out [by Frank Harrell here](https://stats.stackexchange.com/questions/169438/evaluating-logistic-regression-and-interpretation-of-hosmer-lemeshow-goodness-of), and as a result, we don't recommend its use. 
    - Instead, we use the bootstrap to estimate overfitting and get an overfitting-corrected high-resolution smooth calibration curve, with `plot(calibrate(model))`.
    - If a test is needed, Frank suggests that you assess calibration with a different Hosmer et al. test that uses one degree of freedom and is implemented in the `residuals.lrm` function.

2. How do we do variable selection for logistic regression?
    - Stepwise procedures still work, as do ANOVA, AIC and BIC.
    - Cross-validation is still relevant, as is splitting into training and test samples.
    - Making decisions about non-linearity is still relevant, and still done in the same way.

3. Should we use imputation instead of eliminating missing cases in all logistic regression examples?
    - Which kind of regression you're doing doesn't matter. The same advice applies to any sort of regression model.
    - Complete Case analyses have problems. Simple imputation has problems. Multiple imputation has problems. None is always a dominant strategy over the others. There are plenty of settings where you will need to make a choice. In general, multiple imputation is the most defensible approach, but it also restricts what we can do more than the other methods. It might be worth it to see the value of all  three approaches.

4. What if our outcome is multi-categorical, rather than binary?
    - Then you'll need a different kind of generalized linear model. There are separate types of logistic regression models for non-binary ordinal and non-binary nominal categorical outcomes.

Other questions I'm still pondering:

- How to merge >2 dataframes with different lengths based on same ID.  
- Can you say more about sample size in regression models?

