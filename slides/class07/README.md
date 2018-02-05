# 432 Class 07: 2018-02-06

### Key Materials

[The slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class07) and the [audio files](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class07) will be posted as soon as they are available.

In today's class, we'll discuss the incorporation of non-linear terms in a linear regression model, and discuss the use of `ols` to fit and evaluate linear models. That material is in Chapters 9-10 of our Course Notes.

## Announcements Before Class 07

1. Homework 2 Answer Sketch is available in [R Markdown](https://raw.githubusercontent.com/THOMASELOVE/432-2018/master/assignments/hw2/hw2sketch.Rmd), or [HTML](http://htmlpreview.github.io/?https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw2/hw2sketch.html), or [PDF](https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw2/hw2sketch.pdf).

2. Updates in the [Course Notes](https://thomaselove.github.io/432-notes/)
    - I've made a few small edits in Chapters 1-7, especially 1 and 5. 
    - I've made some meaningful edits to Chapter 8. 
        - In particular, I added some material to clarify the calculation of *uncorrected* AIC, and how it (a) differs from bias-corrected AIC, (b) provides no new information beyond what we get from Mallows' Cp in the linear regression setting, and so we don't plot it and (c) is only defined up to an additive constant, so `extractAIC` and `AIC` give different results when applied to a single model, but when comparing two models, either can be used. 
        - I also dropped the non-ggplot2 approach to plotting, and 
        - I added some material on interaction terms, and on the limitations of best subsets regarding the development of best subsets work with multicategorical variables.
    - New Chapters:
        - 9 (on incorporating non-linearity in a linear regression model, particularly polynomial regression and spline models), 
        - 10 (on using `ols` to fit and evaluate linear models), 
        - 11 (which provides brief demonstrations of the use of ridge regression and the lasso), 
        - 12 (introduction to logistic regression ideas)
        - 13 (a first detailed example of logistic regression, including both `glm` and `lrm` approaches to fit and evaluate models)
    - The next chapters on my "to do" list involve (a) another, more complex logistic regression example, including some material on probit regression, and (b) the use of multiple imputation procedures, in some order.

3. The tentative plan is to leave off after Class 7 on linear regression for a bit, and in Class 08 on Thursday, we will discuss some of the logistic regression materials in Chapters 12 and 13. When we finish with Chapter 13 after a class or three, we'll return to complete examples in class mirroring what you'll find in Chapters 9 and 10 and then work through an example like that shown in Chapter 11 before returning to logistic regression in more complicated settings, and then discussing the use of multiple imputation in both linear and logistic regression. I may wind up moving some of the chapters around to accomplish this. We'll see.
