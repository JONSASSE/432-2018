# 432 Class 23: 2018-04-10

## Key Materials

- The [slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class23) will be posted as soon as they are available.
- The [audio files](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class23) will be posted as soon as they are available.

Today's class will begin with discussion of a data visualization, and then we'll discuss methods for exploring time-to-event, or survival data. The survival data ideas discussed today are (mostly) covered in [Chapter 21 of the Course Notes](https://thomaselove.github.io/432-notes/). 

## Announcements prior to class

1. Chapter 21 of the [Course Notes](https://thomaselove.github.io/432-notes/) is now available. It describes some of the fundamental ideas in dealing with time-to-event (survival) data, including survival functions, hazard functions, censoring and Kaplan-Meier estimates, and it demonstrates R code to complete some of these explorations.

2. Chapter 22 of the [Course Notes](https://thomaselove.github.io/432-notes/) is also available. It describes the main ideas behind Cox proportional hazards regression models incorporating covariates that do not change over time. We will discuss this material starting in Class 24, and (I expect) continuing into Class 25.

3. Need some help with using R's sometimes inscrutable Help pages? Check out this Appendix from [Kieran Healy's book on Data Visualization](http://socviz.co/appendix.html#a-little-more-about-r). Actually, the whole Appendix is well-designed and contains lots of useful tips for using R better, and doing things like managing projects, making maps, and a lot of other good stuff. I encourage you to look over [the whole book](http://socviz.co/index.html#preface). This summer, that'll be something I hope to do more closely.

4. A hint for Homework 6 (and for your Project, potentially):

`polr` and several of the other modeling pieces we've worked on recently are finicky, at least in comparison to OLS. Sometimes, you'll get to the point where it seems like the model won't run, or won't summarize properly, or you have some extremely large or extremely small coefficient estimates or standard errors. Should this happen to you, the first thing I would do is try to identify which of your predictors is causing this problem, by running the model first with one predictor, then two, etc. until you figure out which predictors cause problems. Reasons why you could be having a problem include:

1. a predictor has values that completely identify the category of your outcome variable, perfectly (e.g., one category's predictor values are inevitably lower than all of another category's predictor values, with no overlap)
2. the scales of the predictors are wildly different, for instance one predictor has extremely large or extremely small values, causing the estimated standard errors to explode, which should cause you to think about reducing the impact of that, perhaps by changing the units, say from $s to $1000s or by standardizing the predictors
3. intense collinearity between two or more of your predictors
4. coding issues in setting up one or more of the variables.

For example, some people tried to use `median_income` in their models in Homework 6 along with other variables that have much smaller scales (ranges). I would try rescaling those variables with large ranges to have similar magnitudes to the other predictors, perhaps simply by expressing the median income in thousands of dollars (by dividing the raw data by 1000) rather than on its original scale, or perhaps by standardizing all of the coefficients.

As another example, some people tried using age-adjusted mortality to predict years lost rate, but if you divide the years lost rate into several ordinal categories, it's not hard to wind up in a situation where age-adjusted mortality is perfectly separated, so that if you know the mortality, it automatically specifies the years lost rate category in these data.

5. I corrected a few errors on slide 52 of the [Class 20 Slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class20), where I had switched the coefficients for the truncated Poisson and logistic regression models, and where I had used min, when I meant max.

6. Remember that the Project 2 Registration (and Scheduling) [Google Form](https://goo.gl/forms/Zfgnq5pyAAzAlmUm1) is due 2018-04-17, but the sooner the better. A few people have completed it successfully, and others need to revise and resubmit (which you can do by editing the form using the link that is automatically emailed to you when you submit the form.) 
    - I've added some text to the questions on the form to make it a little clearer in terms of what I need in order to approve your work. In particular, I need more details about the data (particularly if it isn't freely available to me online) than some folks provided on their first try. 
    - Approved projects are summarized at [this link](https://github.com/THOMASELOVE/432-2018/blob/master/projects/project2/APPROVED.md).
    - If you have questions about Project 2, **PLEASE** ask them at 431-help, or at Office Hours, or after class or in minute papers. **WE WANT TO HELP YOU**.

7. I've added four more papers to our [texts material](https://github.com/THOMASELOVE/432-2018/tree/master/texts), written by Peter Austin and colleagues. These include
    - a look at the [number of subjects required to build a linear regression model](https://github.com/THOMASELOVE/432-2018/blob/master/texts/Austin%20Steyerberg%202015%20Subjects%20required%20in%20linear%20regression.pdf) which suggests that as few as two subjects per variable can be sufficient to guarantee unbiased estimation of coefficients and adjusted R^2^ values, but larger numbers for adequate statistical power and variable selection. (Good estimates for survival analysis are 10+ events per variable, and for logistic regression, at least 10 EPV for prediction and 50 for reliable variable selection where the events are the smaller of the (# of yes, # of no) in the binary outcome.)
    - a look at the [calibration of logistic regression models using loess smooths](https://github.com/THOMASELOVE/432-2018/blob/master/texts/Austin%20Steyerberg%202013%20Calibration%20of%20Logistic%20Regression%20with%20loess.pdf) which encourages the increased usage of loess methods to identify a lack of calibration in external validation samples.
    - a look at the use of [regression trees in predicting mortality in cardiovascular disease](https://github.com/THOMASELOVE/432-2018/blob/master/texts/Austin%20Lee%20Steyerberg%20Tu%202012%20Regression%20trees%20for%20predicting%20mortality%20in%20CVD.pdf), where trees and ensemble methods didn't really show meaningful improvement over logistic regression, and
    - a look at [using data mining / machine learning technologies for disease classification](https://github.com/THOMASELOVE/432-2018/blob/master/texts/Austin%20Tu%20Ho%20Levy%20Lee%202013%20Using%20data%20mining%20and%20machine%20learning%20for%20disease%20classification%20in%20HF.pdf) where trees did well, but not much better than logistic regression.

## Discussion of the Minute Paper after Class 22

Thank you for completing the Minute Paper. I really appreciate the feedback.

### Have you looked at Homework 6 in a meaningful way yet?

Count | Response
----: | -------------------------------------------------------
7 | Yes, and I've made some progress towards completing it.
7 | Yes, I've looked at it, but not yet made any progress.
7 | No. I better get on that.

### Project 2 "nudges"

Count | **Do you plan to work alone or in a team of two for Project 2?**
----: | --------------------------------------------------------------
10 | I will definitely work alone.
8 | I don't know for sure, but I expect to work alone.
0 | I don't know for sure, but I expect to work with a partner.
3 | I will definitely work with a partner.

Count | **Have you read (carefully) the general Post-Project 1 Feedback?**
----: | ------------------------------------------------------------------
18 | Yes, I've read it carefully.
3 | No, I haven't read it carefully. I should do that, too.


Count | **Do you know what data you will use for Project 2?**
----: | -----------------------------------------------------
9 | Yes, I have a definite plan for what data I will use.
9 | Maybe, I have an idea about what I will do, but haven't settled on the details yet.
3 | No, I haven't gotten to that point yet in my thinking about Project 2.

### What is the most important thing you've learned recently from the course? (not yet edited, first 21 responses)

- fitting different logistic model and use rootogram.
- A lot, for example, how to evaluate logistic regression, how to use ggplot, how to do cross validation for simple linear regression models.
- converting wide and long format data; joining commands to combine data sets
- multinomial logistic regression
- How to predict a categorical outcome
- How to use a rootogram
- New modeling techniques for different types of outcomes
- How to graph multinomial logistic regression results 
- Poisson Regression
- How to deal with categorical outcomes and count outcomes. 
- zero inflated model
- Rootograms
- poisson regression model 
- Logit Model, poisson regression, Multinomial logistic Regression:
- Regression for ordinal and non-ordinal multicategorical outcomes.
- Learning how to build models for ordered (ordinal) categorical outcomes
- How to interpret proportional odds logistic regression models.
- lrm works good with ordinary logistic regression as well - may I should stick to lrm whenever I run logistic regression.
- regression on multi categorical outcome
- How to make models for Multi-categorical variables.
- Analyzing Literary Styles with Multinomial Logistic Regression

### What question(s) about the course are uppermost in your mind now? (not yet edited, first 21 responses)

- will we show our project1 in our presentation?
- I wonder if I can use some other machine learning models that are not covered in class on my project, because it is on real data from my lab and I want to try my best using every possible model I can access. Thank you.
- When using gridExtra::grid.arrange() to place plots next to each other, how do you increase the space between the plots?
- excited to learn survival analysis!
- n/a
- I want to learn more methods of data visualization for a lay audience
- Feeling a bit unsettled by the complete freedom for Project 2. Is there anything specific you want to see? How complex should the research questions be? I am nervous about having something too simple...
- None
- Is there ever a case where we could use either a Poisson OR an ordinal logistic regression? When does "counts" turn into "ordered categories" or vice versa?
- If you have an outcome like a percentage that has a definite upper and lower limit is it always better to deal with it as a count outcome even if the distribution looks relatively normally distributed and without big walls and ceilings?
- I don't have a lot of zero outcome. Can I still use zero inflated probit model?
- Survival analysis
- Is the outcome of Poisson regression model Poisson distribution?
- what are the common peeking behaviors?
- Will the survival analysis section of this course help me to better understand what's going on in my survival analysis course?
- Not much in particular. Still trying to find out how to export spline functions on logistic regressions (and beyond) but that may be more of a personal issue...
- I am curious about different types of graphics that can be used to demonstrate data to the reader.
- What would be the best way to choose the reference variable when we have more than 3 ordinary variables, is it the highest proportion? the most common in the sense of the study question? the most effective variable on the outcome?
- can we use regression on multi categorical outcome when we have asymmetric presentations of the outcome?
- How to make a good project 2?

## Remaining Deliverables This Semester

The [Schedule](https://github.com/THOMASELOVE/432-2018/blob/master/SCHEDULE.md) page is always the final word, if you are confused.

- [Homework 6](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw6) is due at 1 PM on **Friday 2018-04-13**. Submit to [Canvas](https://canvas.case.edu/).
- The Minute Paper after Class 24 will become available 2018-04-12 and is due at **10 AM Monday 2018-04-16**.
- [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) Registration and Scheduling [Google Form](https://goo.gl/forms/Zfgnq5pyAAzAlmUm1) is due at 5 PM on **Tuesday 2018-04-17**.
    - You can see the status (and title) of proposals that have been reviewed and approved [by visiting this link](https://github.com/THOMASELOVE/432-2018/blob/master/projects/project2/APPROVED.md).
- [Homework 7](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw7) is due at 5 PM on **Tuesday 2018-04-24**. Submit to [Canvas](https://canvas.case.edu/).
- [Quiz 2](https://github.com/THOMASELOVE/432-2018/tree/master/quizzes/quiz2) will go out after class on 2018-04-26, and is due at Noon on **Tuesday 2018-05-01**.
- [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) Final Portfolio materials are due 3 hours prior to your Presentation to me. Submit to [Canvas](https://canvas.case.edu/).
- [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) Presentations are on **2018-05-03**, **2018-05-07** and **2018-05-08**, and will be scheduled by 2018-04-19.
- [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) Revisions are due at Noon on **Wednesday 2018-05-09**. Whether you'll need to revise will be determined at your presentation.

## Tweet of the Day

To come.
