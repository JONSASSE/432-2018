# 432 Class 17: 2018-03-20

### Key Materials

- The [slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class17) for today are now available.
    - We will (briefly) cover material from [Chapter 16 in the Course Notes](https://thomaselove.github.io/432-notes/colorectal-cancer-screening-and-some-special-cases.html) on logistic regression for aggregated outcomes, and for probit regression.
- The [audio file](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class17) is now available.

- Before today's class, remember to post your Progress on Project 1 to [Canvas](https://canvas.case.edu/), please.

## Announcements at the start of class

1. Some students have been using the [431 Project Study 1 Demonstration](https://github.com/THOMASELOVE/431project/blob/master/TaskE/431-project-study1-demonstration.pdf) and [431 Project Study 2 Demonstration](https://github.com/THOMASELOVE/431project/blob/master/TaskE/431-project-study2-demonstration.pdf) PDF files I built to help you do projects in 431.  There's lots of useful data cleaning information in those documents. I encourage you to look them over.
    - I also recommend the series of [four YouTube videos on Data Wrangling with R and the Tidyverse](https://www.youtube.com/channel/UC3xfbCMLCw1Hh4dWop3XtHg) by Garrett Grolemund put out recently by R Studio. I particularly recommend the fourth of these videos, on [Working with Two Datasets](https://www.youtube.com/watch?v=AuBgYDCg1Cg&) which can help you combine two data sets together.

2. There is a new [Chapter 16 in the Course Notes](https://thomaselove.github.io/432-notes/colorectal-cancer-screening-and-some-special-cases.html). This briefly illustrates issues related to two topics we've yet to discuss regarding regression models for binary outcomes:
    - the fitting of logistic regression models to data which have been aggregated, so that we know the counts of "yes" and "no" (or "yes" and "total") within each combination of predictors, but not the data on individual subjects. I briefly demonstrate both the `glm` approach, and the `Glm` approach (which is within `rms`.)
    - the use of a different link, specifically the `probit`, in the context of a binary regression model. This produces a probit regression model, which is a reasonable alternative in some settings to a logistic regression.
    
3. Chapters 17 and 18 of the [Course Notes](https://thomaselove.github.io/432-notes/cleaning-the-brfss-smart-data.html) are also now available for you to review. The main document contains a brief summary, with links to pages containing the (substantial) details.
    - Chapter 17 on Cleaning the BRFSS SMART data [can be read here](http://htmlpreview.github.io/?https://github.com/THOMASELOVE/432-2018/blob/master/data-and-code/SMART/smart.html), and there's more information in [this README file](https://github.com/THOMASELOVE/432-2018/tree/master/data-and-code/SMART).
    - Chapter 18 on Regression Models for Count Outcomes [can be read here](http://htmlpreview.github.io/?https://github.com/THOMASELOVE/432-2018/blob/master/texts/chapter18/oh_smart_counts.html), and there's more information in [this README file](https://github.com/THOMASELOVE/432-2018/blob/master/texts/chapter18/README.md).
    
4. Other New Things:
    - Typos have been fixed in many of the chapters of the Course Notes.
    - I added a couple of new packages to install on [the PACKAGES page](https://github.com/THOMASELOVE/432-2018/blob/master/data-and-code/PACKAGES.MD), including `pscl` and `VGAM`, as well as `countreg` which is only available on R-Forge, and requires a special installation routine, described on [the PACKAGES page](https://github.com/THOMASELOVE/432-2018/blob/master/data-and-code/PACKAGES.MD).
    - [Homework 6](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw6) is now posted. It's due 2018-04-06.
    - [Homework 7](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw7) is now posted. It's due 2018-04-13.
    - Remember than Homework 8 has been canceled, so all (both) of the remaining Homeworks are now posted.
    - [Project 2 instructions](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) are now available. We'll discuss them in class on 2018-03-27, after Project 1 is done.

5. Those of you who scored below 80 on Quiz 1 should look at [this Bonus Assignment for those looking to improve a poor Quiz 1 grade](https://github.com/THOMASELOVE/432-2018/tree/master/quizzes/quiz1/bonus). If you scored 80 or higher on Quiz 1, this isn't open to you. If you scored between 75 and 79, it's optional. Answers will be posted to this assignment in April, if you want to use it as a review for Quiz 2 or something.

6. In looking over the [Homework 5 grades](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw5), some were quite low. In a few cases, it seems clear that a mistake was made early on and then you were penalized for it repeatedly, when, in fact, given your mistake early on, you then proceeded to do things correctly. If you find yourself in a situation like this in **any** Homework assignment, I strongly encourage you to submit a regrading request through [this Google Form](https://goo.gl/forms/aQNPnlAWGIn72a7h1) any time between now and noon on Wednesday 2018-05-09, so that I will look your assignment over carefully at the end of the term, if it has any chance of making a difference in your course grade.

## Minute Papers After Class 16 (n = 40/41)

### How confident do you feel about your ability to complete Project 1?

1 (Not at all confident) | 2 | 3 | 4 | 5 | 6 | 7 (Extremely confident) | Responses | Mean
---: | ---: | ---: | ---: | ---: | ---: | --- | ---: | ---: 
0 | 0 | 0 | 2 | 14 | 16 | 8 | 40 | 5.75

### Rate the following subjects in terms of ... 

The table shows Your **Current Knowledge** (*left*) and Your **Interest** in Learning More (*right*).

A Lot | Little | DK | Topic | High | Some | Not | DK
--: | --: | --: | :---------------------------------------------: | --: | --: | --: | --:
3 | 18 | 19 | Regression on time-to-event, survival outcomes | 31 | 8 | 0 | 1
8 | 12 | 20 | Regression on multi-categorical outcomes | 25 | 14 | 0 | 1
1 | 12 | 27 | Regression for count outcomes | 22 | 13 | 2 | 3
5 | 12 | 23 | Linear mixed effects models | 20 | 12 | 3 | 5
2 | 15 | 23 | Cluster / Principal components analysis | 19 | 10 | 2 | 7
0 | 14 | 26 | Classification and regression trees | 16 | 15 | 2 | 7
2 | 7 | 31 | Probit models for binary outcomes | 9 | 17 | 3 | 11

- *Left*: Rate the following subjects in terms of your current knowledge. 
    - "A Lot" = I know how to do this sort of analysis comfortably in R.
    - "Little" = I know a little about this, but not enough to comfortably do an analysis in R.
    - "DK" = I don't know much about this.
- *Right*: Rate the following subjects in terms of your interest in learning more about them.
    - "High" = Very interested in this topic.
    - "Some" = Somewhat interested in this topic.
    - "Not" = Not interested in this topic.
    - "DK" = I don't know enough about this to form an opinion.

### So what will we cover in the rest of the course?

- I've taken the material I planned to show you on probit models for binary outcomes, and logistic regression for outcomes where you have aggregated data and put them in Chapter 16. We'll discuss that lightly today.
- I've taken the detailed materials on cleaning data for the BRFSS SMART study and put that in Chapter 17. I'll essentially leave that for you to read.

After that, we'll work on (in this order, I believe):

1. Models for count outcomes, outcomes with extra zeros, and outcomes which are censored. (That's [Chapter 18](https://github.com/THOMASELOVE/432-2018/blob/master/texts/chapter18/README.md).)
2. Models for nominal categorical outcomes and models for ordinal categorical outcomes.
3. Models for time-to-event / survival outcomes.
4. The Statistical Crisis in Science, Retrospective power and Type S and Type M errors

The [Schedule](https://github.com/THOMASELOVE/432-2018/blob/master/SCHEDULE.md) reflects my current plan.

- Later chapters in the Notes (for which I am still drafting materials) will cover items 2 and 3 in that list.
- Most of the material for item 4 will come out of [this talk I gave last Friday](https://github.com/THOMASELOVE/rethink).
    - I'll try to build some new things for the pair of you who made it to that talk.
- This leaves about four classes as yet unplanned.
    - Linear mixed effects models are easy to do a little bit on, but difficult to do in a lot of detail. I'll see if I can strike a balance, but I will try to at least say something about them.
    - I probably won't do much with cluster analysis, but I'm still thinking about it.
    - I have some material on CART prepared, because I did some of that last year. It's an appealing topic to me, because people don't know much about it, but it wasn't quite as popular, so we'll see.
    - I usually do a class on propensity scores and matching analyses in observational studies, since it's the topic of the more advanced (500) course I teach, it's interesting, and it's my "specialty" field. But we'll see.

### What question(s) about the course are uppermost in your mind now? (A curated sample.)

1. **When should I use `ols` as opposed to `lm`?**
    - This is a false choice. `ols` and `lm` fit identical models, but provide easy access to different types of output. If you want to use the output generated by the `rms` package using the `ols` function (like, for instance, a nomogram) it's easier to fit the model with `ols` to accomplish that. If you want to use output generated more easily by `lm` (like, for instance, the set of four residual plots) then use `lm`. Or use both. There's nothing to stop you from doing so.

2. **Why would we use nomograms?**
    - There are plenty of situations where you need a graphical representation of a model in order to understand how it works better.
    - There are plenty of situations where nomograms remain fast, compact and easy to use, especially when a computer isn't available.

3. **Is it always better to use complete case analyses for outcome variables, rather than imputing them?**
    - No, but it's often the simpler choice to explain to people. 
    - I'd argue that **multiple** imputation of outcomes is usually a competitive strategy with complete case analysis, since multiple imputation is primarily a way of taking the missingness into account in a rigorous way, but I don't think I'd say the same for simple imputation of outcomes.
    
4. **When is it better to use a spline vs. a polynomial fit?**
    - Sorry, but this is another false choice. There's nothing stopping you from doing either in any setting.
    - A spline is likely a more obvious choice whenever you want to let the data decide where the bends in the curve are, rather than (essentially) pre-specifying them, so long as you don't care about explaining the guts of the model to other people. Describing what a spline does **inevitably** involves a graph.
    - If you do care deeply about explaining the guts of the model to other people (as opposed to explaining it to computers) then polynomial fits become more attractive than they do otherwise.

5. **How do we select the best possible regression model for the study?**
    - Get past the idea that there is one model that is best, and you just need to find it. All models are wrong, and many are useful. You just need to maximize your chances of finding something useful.

6. **It seems as though if degrees of freedom are a limiting factor, wouldn't that be really important, and drive our analysis?**
    - Exactly. That's why you have to think hard about what sort of model you want to fit (in terms of which predictors are to be gathered / included) as often as you can. Getting good data is the hardest part. Fitting all of these various models is the easy piece.
    
7. **What about comparing groups in randomized clinical trials?**
    - That was most of 431 Part B, and then our discussion of regression models and analysis of variance. If you're talking about a binary outcome, it's mostly logistic regression, 2x2 tables and chi-square tests so far, but there's a little more to come.
    - The most common scenarios people generate still can be fit well with ordinary least squares. We'll see lots of other options, but the improvements associated with them are sometimes small.

8. **What about adjusting for baseline differences?**
    - In a regression model, that was a large part of 431 Part C, and then our discussion of analysis of covariance, as well as, well, about 80% of our examples in 432 for ordinary least squares.
    - The fundamental point is that it depends on what sort of analysis you're doing whether simply accounting for differences at baseline with a regression model will be sufficient, or whether some sort of matching/subclassification/weighting approach will be necessary. I teach a whole course in making those decisions in observational studies, called PQHS 500 given every Spring. I hope you'll consider it. I'll spend one class talking about that before the semester ends.

9. **When do we use robust linear regression instead of ordinary least squares?**
    - Well, on some level, whenever you like.
    - But I guess the main point is that robust methods are more appealing when regression assumptions don't hold. 

10. **How should I build *numerical* categorical variables?**
    - For some tools, like best subsets or the lasso, you will occasionally see an error that requires you to have all variables be numerical. If so, then you will have to create numerical versions of your categorical variables. 
    - You can do that with indicator (1/0) variables for binary things, and with a series of indicator variables for multi-categorical things, or use `as.numeric` with a multi-categorical factor to build a numeric version (although this is less defensible if your multi-categorical factor is only nominal, and not ordered.) 
        - Note that the codes may not match up as you expect, so you should run a count as a sanity check.

11. **I have an outcome that is a count of something, or that is a count of something with an upper and lower value, or that has a lot of zeros. What should I do?**
    - For Project 1, use an ordinary least squares regression model.
    - After that, we'll have discussed Chapter 18, which is all about such things.

12. **Does the survey you had us take imply `THIS-THING-I-WANT-YOU-TO-DO-WILL-HAPPEN-A-LOT-IN-THE-REST-OF-432`?**
    - No, it doesn't.

## Project 1 Groups for Discussion in Class

Group | Names
------: | -----------------------------------------------------------------------------
1 | Laura Baldassari, Jenny Feng, Maher Kazimi, Satyakam Mishra, Vinh Trinh
2 | Zainab (Albar) Albar, Dongze (Zaza) He, Nik Krieger, Andrew Shan
3 | Andrew Tang, Sneha Vakamudi, Ruipeng Wei, Peter Wilkinson
4 | Gwen Donley, Carli Lehr, Connor Swingle, Frances Wang
5 | Ryan Honomichl, JJ Huang, Xin Xin Yu, Bilal Zonjy
6 | Khaled Alayed, Kedar Mahajan, Preeti Pathak, Sarah Planchon Pope
7 | Estee Cramer, Laura Cremer, Hyun Jo Kim, Roberto Martinez
8 | Abhishek Deshpande, Jack McDonnell, Grace Park, Gabby Rieth
9 | Haimeng Bai, Sophia Cao, Kate Dobbs, Elina Misicka
10 | Vaishali (Vee) Deo, Caroline El Sanadi, Kaylee Sarna, Sandra Silva Camargo

### Your Group Tasks

1. Before class on March 20, you need to post your Progress on Project 1 to Canvas.
    - The work in progress location that is up at Canvas now is a revised setup, which should let you review your colleagues' work if they submit it properly, but still maintain your work as your own, even through multiple passes.
    - The temporary directory I built on GitHub to house HTML files is now gone.
2. In class today, you and your group should discuss the most pressing question each of you has, at this point, about your project.
3. During and after class on Tuesday, but before class on Thursday March 22, you'll be looking over the code of the people in your group, and giving them some feedback on what you see. 
    - At a minimum, be sure to check and see if their HTML file contains anything it should not (like my instructions) or if the labeling doesn't make sense or isn't easy to work with. Make sure they have a real title and their name is provided where it belongs, and that the HTML file contains their name. Your class participation grade will be affected by the quality of the comments you post to Canvas, as well as by the opinions of your fellow project group members about your efforts, as expressed in a Minute Paper to come.
