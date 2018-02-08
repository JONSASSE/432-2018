# 432 Class 08: 2018-02-08

### Key Materials

[The slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class08) are posted above, and the [audio files](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class08) will be posted as soon as they are available.

In today's class, we'll introduce the logistic regression model. We'll cover all of Chapter 12 and some of Chapter 13 in the [Course Notes](https://thomaselove.github.io/432-notes/). Next week, we'll finish that logistic regression material, then move forward to look at Chapter 10's material on using `ols` to fit linear models.

## Tweet of the Day: A Close Battle

- [Jeff Leek](https://twitter.com/jtleek/status/961310256805576705)
- [Amelia McNamara](https://twitter.com/AmeliaMN/status/961552968611975169)
- [Nicholas Sanders](https://twitter.com/nj_sanders/status/960997956269826048)
- and I also enjoyed Jeff's blog entitled "[What do Fahrenheit, comma separated files, and markdown have in common?](https://simplystatistics.org/2018/02/08/what-do-fahrenheit-comma-separated-files-and-markdown-have-in-common/)"

## Announcements Before Class 08

1. [Homework 3](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw3) is due at 1 PM on Friday 2018-02-09. The link on [Canvas](https://canvas.case.edu) should be open now.

2. The [Minute Paper after Class 08](https://goo.gl/forms/IRPizcTN8Y7k8Y2f1) is now available. Please complete this by 10 AM on Monday 2018-02-12.

3. Your [project 1 proposal](https://github.com/THOMASELOVE/432-2018/blob/master/projects/project1/README.md#the-proposal) is due the following Monday, 2018-02-19 at noon. Submit it via [Canvas](https://canvas.case.edu/).
    - There is now a complete sample **project** (not just the proposal) available now, built using the template, by Dr. Love. This adds the Analyses (Section 10 on Linear Regression and Section 11 on Logistic Regression) to the sample Proposal document. This example was mostly built in Spring 2017, and the code here has largely NOT been updated to reflect changes in the way I am teaching 432 this year. See the note in Section 0.1 of [the HTML file](http://htmlpreview.github.io/?https://github.com/THOMASELOVE/432-2018/blob/master/projects/project1/example-project-432-spring2018.html).
        - You can get the full sample project's `example-project-432-spring2018.Rmd` [markdown file used to generate the results](https://raw.githubusercontent.com/THOMASELOVE/432-2018/master/projects/project1/example-project-432-spring2018.Rmd), and you can [view the full project HTML result](http://htmlpreview.github.io/?https://github.com/THOMASELOVE/432-2018/blob/master/projects/project1/example-project-432-spring2018.html).
        - You can get the `cardiac.dat` data used in the sample project at [the Data and Code page](https://github.com/THOMASELOVE/432-2018/tree/master/data-and-code).

4. I've added considerable material to the [Texts page](https://github.com/THOMASELOVE/432-2018/tree/master/texts) to provide some suggestions (including several downloadable books) which may help you move forward.
    - In particular, I built a [Google Drive folder which you can access via CWRU](https://drive.google.com/drive/folders/1vN8dfqtz-hGyu7hrsPpBRnJptKI1B0BV?usp=sharing) containing four e-books.

5. Useful item of the day is this [tutorial by Joyce Robbins on re-ordering the bars in a bar chart](https://github.com/jtr13/codehelp/blob/master/R/reorder.md), which explains lots of useful things in the `forcats` package, and links to the great "[Be the boss of your factors](http://stat545.com/block029_factors.html)" materials from Jenny Bryan.

6. I mentioned a piece by Andrew Gelman last time. Here it is: [p=0.24: “Modest improvements” if you want to believe it, a null finding if you don’t](http://andrewgelman.com/2018/02/05/p0-24-modest-improvements-want-believe-null-finding-dont/).

7. Last time, I talked about Spearman rho-squared plots and spending degrees of freedom. Let me say more on that here:
    - The reason to use a Spearman rho-squared plot, most commonly, is that each of the following things are true:
        - Your subject matter understanding allows you to identify potentially appealing predictors that you want to include in a model.
        - Your understanding, though, is limited when it comes to identifying important non-linearity in the data, or interactions that must be included to maintain face validity.
        - Your data aren't large enough to meet the 20:1 rule (as explained below, from [Frank Harrell's manuscript checklist](http://biostat.mc.vanderbilt.edu/wiki/Main/ManuscriptChecklist).)

**The 20:1 Rule**

> The 20:1 rule is as follows. Let m denote the effective sample size (the number of subjects if the response variable is a fully-observed continuous one; the number of events if doing a survival analysis; the lower of the number of events and number of non-events if the response is dichotomous) and p denote the number of candidate predictor terms that were examined in any way with respect to the response variable. p includes nonlinear terms, product terms, different transformations attempted, the total number of cutoffs attempted to be applied to continuous predictors, and the number of variables dropped from the final model in a way that was unblinded to the response. If the ratio of m to p exceeds 20, the model is likely to be reliable and there is less need for the model to be validated.

Frank has several other related comments in that checklist:

> Researchers frequently formulate their first model in such a way that it encapsulates a model specification bias that affects all later analytical steps.  

> When a multivariable model is reported, an unbiased validation (at least an internal validation) should be reported in the paper unless: (a) The model terms were pre-specified and the purpose of model fitting was not to report on the predictive accuracy of the model but to compute pre-specified partial test statistics, estimates, and confidence intervals for a small selected set of predictors or (b) The dataset meets the "20:1" rule.
    
> There are many ways that authors have been seduced into taking results out of context, particularly when reporting the one favorable result out of dozens of attempted analyses. Filtering out (failing to report) the other analyses is scientifically suspect. At the very least, an investigator should disclose that the reported analyses involved filtering of some kind, and she should provide details. 

> When using traditional frequentist statistical methods, adjustment of P-values for multiple comparisons is necessary unless
    - The investigator has pre-specified an ordered priority list of hypotheses, and
    - The results of all hypothesis tests performed are reported in the pre-specified order, whether the P - values are low or high
    - P-values should be adjusted for filtering as well as for tests that are reported in the current paper. 

> Stepwise variable selection, univariable screening, and any method that eliminates "insignificant" predictor variables from the final model causes [a multitude of serious problems](http://www.stata.com/support/faqs/statistics/stepwise-regression-problems) related to bias, significance, improper confidence intervals, and multiple comparisons. See also [this Stack Exchange post](http://stats.stackexchange.com/questions/20836/algorithms-for-automatic-model-selection).

A practical issue related to a question Peter Wilkinson was good enough to ask last time (**is it better to split the data and validate your model in a completely new sample as opposed to doing cross validation?**) is addressed there, specifically: **when can you get reliable answers with data splitting into a 50-50 training-test split**? 
    
-  Frank's answer ([see partway down the page here](https://stats.stackexchange.com/questions/20836/algorithms-for-automatic-model-selection)) is that in a binary logistic regression model, where you're interested in ROC curve analysis, with 50 parameters examined, you needed **n > 20,000** to get reliable results. The story's not quite as bad for linear regression, but you need really really big samples for binary logistic regression.
- The reason you need big samples is because of poor precision. Lots of times, people consider 100 repeats of 10-fold cross validation, or bootstrapping, to deal with this sort of issue. 
- Frank recommends the bootstrap for validation when possible, especially for summary statistics like R-squared, and tools in the `rms` package that we will learn can help accomplish this sort of validation. Our k-fold cross-validation approach is also reasonable, although it looks like for important issues, you may want to run it several times (with different random seeds) to see how the answers evolve.

## One Last Thing

If you're not sad enough, think about this [tweet from Guillaume Bourque](https://twitter.com/guilbourque/status/959248544002699266)
