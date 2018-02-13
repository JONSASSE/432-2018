# 432 Class 09: 2018-02-13

### Key Materials

- [The slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class09) are posted above (including some of the material originally scheduled for Class 08.) I expect that we'll get through a bit more than half of these slides, and that the rest will be covered in Class 10.
- The [audio files](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class09) will be posted as soon as they are available.

In today's class, we'll continue our discussion of logistic regression.

+ Note that it's not **logistical regression** or **log(istic) regression**. 
+ Logistic regression is a generalized linear model approach used to predict a binary (yes/no represented as 1/0) outcome using a linear function of predictors.
    + The linear function of predictors is connected to the respnse with a logit link, so that we actually predict the log odds of an outcome on a linear scale of the predictors.
    + Exponentiation can allow us to describe the effects of the model predictors in terms of odds ratios.
    + An additional mathematical transformation can allow us to estimate predictions in terms of probabilities that the outcome = 1 or yes.

## Announcements Before Class 09

1. [Homework 4](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw4) is due at 1 PM on Friday 2018-02-16.
    - The ambiguity regarding controlling for smoking, for instance, is deliberate. You need to make a decision about what best to include in your model, and justify that decision. All I'll say is that there is more than one possible appealing approach.
    - The Homework 3 answer sketch and a draft of the grading rubric [are now available](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw3).
    - [Grades on HW2](https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw2/hw2grades.pdf) are now available, too.

2. Your [project 1 proposal](https://github.com/THOMASELOVE/432-2018/blob/master/projects/project1/README.md#the-proposal) is due at noon  Monday, 2018-02-19.

3. R Studio version 1.1.423 [is now available](https://www.rstudio.com/products/rstudio/download/#download). I updated.

4. No substantial progress on the [Course Notes](https://thomaselove.github.io/432-notes/) this week. Only change is a typo repair in section 10.3.1, about simultaneous confidence intervals in an `ols` fit.

## Minute Papers after Class 08 

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

### What question(s) about the course are uppermost in your mind now?

1. How do we go about interpreting estimated coefficients and their confidence intervals in logistic regression?
    + Interpreting the exponentiated coefficients, in terms of odds ratios, is the most appealing approach. We'll discuss today.
2. Several related questions asked how do we **graph the results of a logistic regression**.
    + Visualization will require the development of some new ideas.
    + A scatterplot, for instance, can be used to describe the relationship between a binary outcome and a single quantitative predictor, or perhaps a single quantitative predictor and a second categorical predictor.
    + With facetting, perhaps you can look at a couple of categorical and a single quantitative predictor at once, but that's about it.
    + So the answer is that we won't be using scatterplots alone to graph the relationships between a binary outcome and more than a few predictors. The nomogram is one approach. Another is to focus on the predicted effect sizes, and the predictions made, across multiple predictors holding others constant.
3. Is there an R-square analog for logistic regression?
    + Yes, in fact there are several. When we get there, we'll focus on the Nagelkerke R-square, as described in the [Notes, section 13.12](https://thomaselove.github.io/432-notes/logistic-regression-and-the-resect-data.html#logistic-regression-using-lrm)
4. Can we use stepwise regression for a binary outcome?
    + Yes.
5. Is there a way to do "best subsets" for a binary outcome?
    + No. Not using `leaps`, anyway. But AIC and BIC are still relevant. And we'll also look at ROC curve analyses, and C statistics.
6. How do we implement **polynomial regression**?
    + Including an orthogonal polynomial is straightforward in an `lm` setting - just add the `poly(x, 2)` statement to get a polynomial of degree 2 in variable `x`, for instance. More details in [Section 9.4 of the Course Notes](https://thomaselove.github.io/432-notes/adding-non-linear-terms-to-a-linear-regression-model.html#orthogonal-polynomials). The same approach works in `glm`, too.
    + I have never used a higher degree than 3 in a polynomial function in clinical work.
    + Polynomials are used for quantitative predictors, and not categorical ones.
    + As we introduce the `rms` package and its model fitting functions `lrm` and `ols` this week, we'll have another method for doing this.
7. How do we use **restricted cubic splines** to capture non-linearity?
    + Again, the inclusion of a restricted cubic spline with four knots in the predictor `x` is straightforward in an `lm` setting - just add the `rcs(x, 4)` statement to your model, for instance. [See Section 9.6 of the Notes](https://thomaselove.github.io/432-notes/adding-non-linear-terms-to-a-linear-regression-model.html#fitting-a-restricted-cubic-spline-in-a-linear-regression). The same approach works for `glm`, `lrm` and `ols`.
    + I have never used a number of knots other than 3, 4 or 5 in a restricted cubic spline in clinical work.
    + Restricted cubic splines are used for quantitative predictors, and not categorical ones.
    + Interpreting the result is the challenge, and the key idea there is to study the effect of the restricted cubic spline in terms of the predictions it makes. Another key helper for interpretation is the nomogram, which we'll discuss today (or Thursday).
8. Can we use multiple non-linear representations of predictors in a single model?
    + Sure. There's no restriction on how much of this you can do, other than sample size and precision of estimates.
9. Do people actually use orthogonal polynomials and restricted cubic splines in clinical research / clinical prediction models?
    + [These](https://www.ncbi.nlm.nih.gov/pubmed/8511440) "modern" [ideas](https://academic.oup.com/jnci/article-abstract/80/15/1198/925981) are [used](http://onlinelibrary.wiley.com/doi/10.1002/sim.4780080504/full) all the [time](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3192444/) and [actually](http://onlinelibrary.wiley.com/doi/10.1002/sim.6986/full) aren't [all](https://www.sciencedirect.com/science/article/pii/S0895435608002783) that [modern](https://bmcmedresmethodol.biomedcentral.com/articles/10.1186/s12874-016-0141-3). Some [have](https://www.researchgate.net/figure/Restricted-cubic-spline-plots-showing-the-association-of-heart-rate-and-clinical_fig2_262191985) been [around](https://books.google.com/books?id=It5bCwAAQBAJ&pg=PT376&lpg=PT376&dq=orthogonal+polynomials+in+clinical+research&source=bl&ots=suZrWmKLMs&sig=Y2jh0TE-LoU6GuZMs-zF_ZsQToM&hl=en&sa=X&ved=0ahUKEwiNi8HJ8qLZAhUH1lMKHdxDAnI4ChDoAQgzMAI#v=onepage&q&f=false) for [years](https://link.springer.com/content/pdf/10.3758/BF03200967.pdf).
10. Can I use **this package Dr. Love has never taught us** to do something in R?
    - In a homework assignment or project? Sure, so long as it does what it needs to do correctly and consistently, and you can describe what you are doing.
    - On a quiz where he asks you to edit a particular batch of code to achieve a specific end? There, I would stick with the materials from the course.
11. Why is it so difficult to find an open-access data set that has useful quantitative information in it?
    + A part of the reason is that so much more survey data is easily accessible than anything else, and people writing surveys often prefer to use response categories rather than quantitative responses. Sometimes this is for good reasons, but it is frustrating.
    + Others mentioned how difficult it was to get access to research data. You're not alone. The process can be infuriating. This is part of the reason why the "Open Data" movement has some momentum.
    + It's especially frustrating to realize that if you want to sell someone something (healthy or unhealthy), getting useful data for that task is generally easier than getting the data you need to try to improve their health.
    + There's a whole lot of [data published by fivethirtyeight.com](https://github.com/fivethirtyeight/data), which might be of interest, although you have to avoid the stuff that's in the [`fivethirtyeight` package in R](https://cran.r-project.org/web/packages/fivethirtyeight/vignettes/fivethirtyeight.html) already.
12. (a) When will we learn about the details for Project Two and (b) what can we be doing to prepare in the meantime?
    + (a) After Project 1 is over. (b) Do Project 1, and identify data of interest to you for a new project.
