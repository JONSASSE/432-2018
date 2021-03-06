# 432 Class 11: 2018-02-20

### Key Materials

- [The slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class11) are posted above. They include some leftover materials from Class 10 on logistic regression, followed by a discussion of linear regression using the `ols` function in the `rms` package. 
- The [audio files](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class11) are now posted.

In today's class, we'll finish our discussion of the logistic regression models for the Framingham Heart Study that we began in Class 10. All of this material is also contained in a new [Chapter 14 of the Course Notes](https://thomaselove.github.io/432-notes/). Then we'll discuss the use of the `ols` function and related materials from `rms` and `Hmisc` in fitting linear regression models, amplifying what you'll find in [Chapter 10 of the Course Notes](https://thomaselove.github.io/432-notes/using-ols-from-the-rms-package-to-fit-linear-models.html).

## After Class

- Audio file is posted above.
- We got through slides 1-24, and so the slides above have now been edited to show only that material. The remaining slides are now to be found in the slides for [Class 12](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class12).

## Announcements Before Class 11

1. [Homework 4](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw4) is due at 1 PM on Friday, 2018-02-23.

2. Your [project 1 proposal](https://github.com/THOMASELOVE/432-2018/blob/master/projects/project1/README.md#the-proposal) is also due at 1 PM on Friday, 2018-02-23. Five people have this in already - I hope to get to them tonight.

3. A coding tip: If you filter a data set in R to focus on specific levels of a factor, R retains all of those factor levels by default. If this is a problem, use the `droplevels` function. [See here](https://stackoverflow.com/questions/32059343/when-filtering-with-dplyr-in-r-why-do-filtered-out-levels-of-a-variable-remain) for more details.

4. Having trouble developing a reproducible example, or just need help asking a question? Take a look at the `reprex` package and [this help page](https://www.tidyverse.org/help/).

5. There is a new (partially completed) Chapter 14 in the [Course Notes](https://thomaselove.github.io/432-notes/), which builds a pair of logistic regression models for exercise in the BRFSS data we've analyzed earlier. The Chapter includes a complete case analysis (to be sure the code runs) and full models with simple imputation. I'll add multiple imputation (and thus complete the chapter) before I see you on Thursday, I hope. 

6. **Installing vs. Updating vs. Loading Packages** All of the packages we've introduced recently were installed by you in R at the beginning of the semester, and [those instructions are here](https://github.com/THOMASELOVE/432-2018/blob/master/data-and-code/PACKAGES.MD), or at any rate, that was what you were supposed to do. That includes the `rms` package, which for some reason, people keep misspelling. 
    - You **install** a package once or twice a semester, you **load** it (with the library command) every day as you need it in an individual session. 
    - So, **installing** a package is something you do every time you install a new version of R. This happens rarely, maybe twice this semester. The current version of R I am running is 3.4.3, but there will be a new version (probably 3.5.0) later this semester, I believe. Again, [instructions for installation are here](https://github.com/THOMASELOVE/432-2018/blob/master/data-and-code/PACKAGES.MD).
    - **Updating** your packages is a good idea. I do this weekly. If you're getting an error message about a package, an update will sometimes fix that problem. Start a fresh R Studio session, and then, in R Studio, go to the Packages tab on the lower right, and click on Update. You'll also update after you install a new version of R Studio. The current version of R Studio I am running is 1.1.423.
    - **Loading** a package is something you do in an R Markdown file to tell that specific program that you want to include the functions in a particular package in that analysis. Load packages in any order, except that you should **always load the tidyverse last**.

## Minute Papers After Class 10

### Project 1 Progress (n = 39/41)

#### Tell me about your progress towards getting data for Project 1

Count (%) | Description
---------: | -------------------------------------------------------------------------------------
33 (85%) | I have a data set in hand that I can use that is shareable with the world, of appropriate size.
6 (15%) | I have a data set in mind, but I don't have the data in my hands yet.
0 (0%) | I don't yet have a data set in mind. I need to get going on that.

#### Have you opened the Project 1 Template and typed in any new information yet?

Count (%) | Description
---------: | -------------------------------------------------------------------------------------
29 (74%) | Yes, I've opened the template and done something.
10 (26%) | Not yet. I should do that soon.

#### How confident do you feel about your ability to complete the Project 1 Proposal?

Result | 5 = Extremely Confident | 4 | 3 | 2 | 1 = Not confident at all | Total | Mean
---------: | ----------------: | -----: | -----: | -----: | -----: | ----: | ----:
Count (%) | 12 (30.8) | 17 (43.5) | 8 (20.5) | 2 (5.1) | 0 (0) | 39 | 4.0

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
    - Some people think of calibration as "goodness of fit" and discrimination as "predictive power". That can be a helpful split. 
    - Sometimes a poorly calibrated model could be improved by including interaction or other non-linear terms.
    - The most popular statistic for testing goodness of fit is the Hosmer-Lemeshow test, which has several problems associated with it as pointed out [by Frank Harrell here](https://stats.stackexchange.com/questions/169438/evaluating-logistic-regression-and-interpretation-of-hosmer-lemeshow-goodness-of), and as a result, we don't recommend its use. Instead, we use the bootstrap to estimate overfitting and get an overfitting-corrected high-resolution smooth calibration curve, with `plot(calibrate(model))`. If a test is needed, Frank suggests that you assess calibration with a different Hosmer et al. test that uses one degree of freedom and is implemented in the `residuals.lrm` function.

2. How do we do variable selection for logistic regression?
    - Stepwise procedures still work, as do ANOVA, AIC and BIC.
    - Cross-validation is still relevant, as is splitting into training and test samples.
    - Making decisions about non-linearity is still relevant, and still done in the same way as in a linear regression model.

3. Should we use imputation instead of eliminating missing cases in all logistic regression examples?
    - Which kind of regression you're doing doesn't matter. The same advice applies to any sort of regression model.
    - Complete Case analyses have problems. Simple imputation has problems. Multiple imputation has problems. 
    - None of these approaches is always a dominant strategy over the others. 
    - There are plenty of settings where you will need to make a choice. I encourage you to see the value of adding all three approaches to the set of things you can do in practice, rather than looking for a "one size fits all" answer.
    - In general, multiple imputation is the most defensible approach, but it also restricts what we can do more than the other methods. In many, many settings, I'll use complete case analysis to fit an initial model and check to be sure that my code does what I expect, and then develop an imputation strategy after that's accomplished. The decision between simple and multiple imputation often depends on how much missingness I actually have, and which variables have missing data. 
    - For instance, I tend not to impute outcomes or key predictors if I can avoid it, but I might use simple imputation if ancillary covariates are all that is missing, or if there is very little missingness on any predictor I consider to be important.

4. What if our outcome is multi-categorical, rather than binary?
    - Then you'll need a different kind of generalized linear model. There are separate types of logistic regression models for non-binary ordinal and non-binary nominal categorical outcomes.

5. Can you say more about sample size in regression models?
    - The sample size you need depends on the research question you are trying to answer, just as it always has.
    - The two main uses of regression models are (1) *prediction*, which includes *classification* and (2) *explanation*.
    - If you're using the model to **explain** whether a particular hypothesized relationship holds, then you should be able to specify the details on what groups are being compared, and how, and apply standard power analysis methods to see what sort of sample you require. 
        + One natural starting point is to look at the widths of the confidence intervals for your key parameter of interest (often the slope of the key "treatment" variable) to understand the power of your regression study for explanation of the link between the treatment and the outcome, while accounting for other covariates.
        + Another is to generate a model without covariates, which likely corresponds to a straightforward ANOVA comparison, which can be powered (for example) with the `power.anova.test` function (for a balanced one-way ANOVA) or equivalently with the `pwr.anova.test` approach (from the `pwr` package) and by the `pwr.2p2n.test` in the `pwr` package for a comparison of two proportions with (potentially) differing sample sizes.
        + Specialized software, [like G*Power](http://www.gpower.hhu.de/en.html) can help in this setting. See [Faul, Erdfelder, Buchner and Lang](http://www.gpower.hhu.de/fileadmin/redaktion/Fakultaeten/Mathematisch-Naturwissenschaftliche_Fakultaet/Psychologie/AAP/gpower/GPower31-BRM-Paper.pdf). [UCLA also has a page](https://stats.idre.ucla.edu/other/gpower/) explaining the use of G*Power in several contexts, including multiple regression.
        + Power analyses for more complex situations usually rely on simulation.
    - In terms of the number of observations needed to fit a reliable (i.e. consistent) regression model for **prediction**, the 20:1 rule discussed in [the Class 8 README](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class08) is a useful one. Repeating the key bits here:

**The 20:1 Rule** 

- Let *m* denote the effective sample size 
    + If you have a quantitative outcome with no missing values, then *m* is the number of subjects.
    + If you have a binary outcome (1 or 0) with no missing values, then *m* is the **smaller** of (number of 1s, number of 0s).
    + If you are building a model for a time-to-event analysis, then *m* is the number of events that are observed.
    + Do not impute missing outcome values, nor count those subjects with missing outcomes in establishing *m*.
- Let *p* denote the number of candidate predictor terms that were examined in any way with respect to the outcome.
    + *p* includes non-linear terms, product terms, different transformations attempted, the total number of cutoffs attempted to be applied to continuous predictors, and the number of variables dropped from the final model in a way that was unblinded to the response.
- Now, calculate *m/p*. 
    + If this ratio exceeds 20, the model is likely to be fairly reliable, and a validation is appealing but less critical.
    + If this ratio is less than 20, the model is especially in need of validation, and even then may be unreliable when applied to new data.

6. How can I learn more about merging two data sets?
    - I usually do this with one of the `join` functions from the `dplyr` package. 
        + Here are some thoughts on [joining two tbls together](http://dplyr.tidyverse.org/reference/join.html).
        + I can also recommend the R Studio cheatsheet on [data transformation](https://github.com/rstudio/cheatsheets/raw/master/data-transformation.pdf) (which has a whole section devoted to combining data tables/tibbles.


