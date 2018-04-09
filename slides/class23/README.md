# 432 Class 23: 2018-04-10

## Key Materials

- The [slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class23) will be posted as soon as they are available.
- The [audio files](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class23) will be posted as soon as they are available.

Today's class will begin with discussion of animated data visualizations, and then we'll discuss methods for exploring time-to-event, or survival data. The survival data ideas discussed today are (mostly) covered in [Chapter 21 of the Course Notes](https://thomaselove.github.io/432-notes/). 

Links to the visualizations we'll discuss today:

- [Income Mobility Charts for Girls, Asian-Americans and Other Groups. Or Make Your Own](https://www.nytimes.com/interactive/2018/03/27/upshot/make-your-own-mobility-animation.html) (*New York Times* 2018-03-27)
- [What's Warming the World?](https://www.bloomberg.com/graphics/2015-whats-warming-the-world/) (Bloomberg.com 2015)

## Announcements prior to class

1. Chapter 21 of the [Course Notes](https://thomaselove.github.io/432-notes/) is now available. It describes some of the fundamental ideas in dealing with time-to-event (survival) data, including survival functions, hazard functions, censoring and Kaplan-Meier estimates, and it demonstrates R code to complete some of these explorations.

2. Chapter 22 of the [Course Notes](https://thomaselove.github.io/432-notes/) is also available. It describes the main ideas behind Cox proportional hazards regression models incorporating covariates that do not change over time. We will discuss this material starting in Class 24, and (I expect) continuing into Class 25.

3. Need some help with using R's sometimes inscrutable Help pages? Check out this Appendix from [Kieran Healy's book on Data Visualization](http://socviz.co/appendix.html#a-little-more-about-r). Actually, the whole Appendix is well-designed and contains lots of useful tips for using R better, and doing things like managing projects, making maps, and a lot of other good stuff. I encourage you to look over [the whole book](http://socviz.co/index.html#preface). This summer, that'll be something I hope to do more closely.

4. Speaking of visualizations, the `ggridges` package just got a substantial upgrade, and can now do [lots of new things](https://twitter.com/ClausWilke/status/981884867196669952). [Check it out](https://cran.r-project.org/package=ggridges).

5. A hint for [Homework 6](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw6) (and for your Project, potentially):

`polr` and several of the other modeling pieces we've worked on recently are finicky, at least in comparison to OLS. Sometimes, you'll get to the point where it seems like the model won't run, or won't summarize properly, or you have some extremely large or extremely small coefficient estimates or standard errors. Should this happen to you, the first thing I would do is try to identify which of your predictors is causing this problem, by running the model first with one predictor, then two, etc. until you figure out which predictors cause problems. Reasons why you could be having a problem include:

1. a predictor has values that completely identify the category of your outcome variable, perfectly (e.g., one category's predictor values are inevitably lower than all of another category's predictor values, with no overlap)
2. the scales of the predictors are wildly different, for instance one predictor has extremely large or extremely small values, causing the estimated standard errors to explode, which should cause you to think about reducing the impact of that, perhaps by changing the units, say from $s to $1000s or by standardizing the predictors
3. intense collinearity between two or more of your predictors
4. coding issues in setting up one or more of the variables.

For example, some people tried to use `median_income` in their models in Homework 6 along with other variables that have much smaller scales (ranges). I would try rescaling those variables with large ranges to have similar magnitudes to the other predictors, perhaps simply by expressing the median income in thousands of dollars (by dividing the raw data by 1000) rather than on its original scale, or perhaps by standardizing all of the coefficients.

As another example, some people tried using age-adjusted mortality to predict years lost rate, but if you divide the years lost rate into several ordinal categories, it's not hard to wind up in a situation where age-adjusted mortality is perfectly separated, so that if you know the mortality, it automatically specifies the years lost rate category in these data.

6. I corrected a few errors on slide 52 of the [Class 20 Slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class20), where I had switched the coefficients for the truncated Poisson and logistic regression models, and where I had used min, when I meant max.

7. Remember that the Project 2 Registration (and Scheduling) [Google Form](https://goo.gl/forms/Zfgnq5pyAAzAlmUm1) is due 2018-04-17, but the sooner the better. A few people have completed it successfully, and others need to revise and resubmit (which you can do by editing the form using the link that is automatically emailed to you when you submit the form.) 
    - I've added some text to the questions on the form to make it a little clearer in terms of what I need in order to approve your work. In particular, I need more details about the data (particularly if it isn't freely available to me online) than some folks provided on their first try. 
    - In the Minute Papers, some people worried about whether their proposed research questions were too simple. That seems unlikely. Most people try to do too much, rather than too little. But, to frame the idea, you're looking for one or two questions that are amenable to building a prediction or regression model using a clear outcome and a clear set of predictors, perhaps with one key predictor (the "exposure" or "intervention" of interest) and several secondary predictors. If you have something like that in mind, good.
    - Approved projects are summarized at [this link](https://github.com/THOMASELOVE/432-2018/blob/master/projects/project2/APPROVED.md).
    - If you have questions about Project 2, **PLEASE** ask them at 431-help, or at Office Hours, or after class or in minute papers. **WE WANT TO HELP YOU**.

8. I've added four more papers to our [texts material](https://github.com/THOMASELOVE/432-2018/tree/master/texts), written by Peter Austin and colleagues. These include
    - a look at the [number of subjects required to build a linear regression model](https://github.com/THOMASELOVE/432-2018/blob/master/texts/Austin%20Steyerberg%202015%20Subjects%20required%20in%20linear%20regression.pdf) which suggests that as few as two subjects per variable can be sufficient to guarantee unbiased estimation of coefficients and adjusted R^2^ values, but larger numbers for adequate statistical power and variable selection. (Good estimates for survival analysis are 10+ events per variable, and for logistic regression, at least 10 EPV for prediction and 50 for reliable variable selection where the events are the smaller of the (# of yes, # of no) in the binary outcome.)
    - a look at the [calibration of logistic regression models using loess smooths](https://github.com/THOMASELOVE/432-2018/blob/master/texts/Austin%20Steyerberg%202013%20Calibration%20of%20Logistic%20Regression%20with%20loess.pdf) which encourages the increased usage of loess methods to identify a lack of calibration in external validation samples.
    - a look at the use of [regression trees in predicting mortality in cardiovascular disease](https://github.com/THOMASELOVE/432-2018/blob/master/texts/Austin%20Lee%20Steyerberg%20Tu%202012%20Regression%20trees%20for%20predicting%20mortality%20in%20CVD.pdf), where trees and ensemble methods didn't really show meaningful improvement over logistic regression, and
    - a look at [using data mining / machine learning technologies for disease classification](https://github.com/THOMASELOVE/432-2018/blob/master/texts/Austin%20Tu%20Ho%20Levy%20Lee%202013%20Using%20data%20mining%20and%20machine%20learning%20for%20disease%20classification%20in%20HF.pdf) where trees did well, but not much better than logistic regression.

## Discussion of the Minute Paper after Class 22

Thank you to the 38/41 who completed the Minute Paper. I really appreciate the feedback.

### Have you looked at Homework 6 in a meaningful way yet?

Count | Response
----: | -------------------------------------------------------
15 (40%) | Yes, and I've made some progress towards completing it.
14 (37%) | Yes, I've looked at it, but not yet made any progress.
9  (24%) | No. I better get on that.

### Project 2 "nudges"

Count | **Do you plan to work alone or in a team of two for Project 2?**
----: | --------------------------------------------------------------
20 (53%) | I will definitely work alone.
13 (34%) | I don't know for sure, but I expect to work alone.
1 (3%) | I don't know for sure, but I expect to work with a partner.
4 (11%) | I will definitely work with a partner.

Count | **Have you read (carefully) the general Post-Project 1 Feedback?**
----: | ------------------------------------------------------------------
34 (90%) | Yes, I've read it carefully.
4 (11%) | No, I haven't read it carefully. I should do that, too.

Count | **Do you know what data you will use for Project 2?**
----: | -----------------------------------------------------
17 (45%) | Yes, I have a definite plan for what data I will use.
16 (42%) | Maybe, I have an idea about what I will do, but haven't settled on the details yet.
5 (13%) | No, I haven't gotten to that point yet in my thinking about Project 2.

### What is the most important thing you've learned recently from the course? (edited)

- Developing and using a rootogram to assess the fit of a model for a count outcome to data.
- The prediction of count outcomes with a wide variety of models based on Poisson and Negative Binomial regression.
    - The notion of a "zero-inflated" model to account for a particular kind of overdispersion.
- The prediction of ordinal multi-categorical outcomes with proportional odds logistic regression models.
- The prediction of nominal multi-categorical outcomes with multinomial logistic regression models.
- Converting data from "wide" format to "long" format.
- "Joining" commands to combine multiple data sets.
- Graphing and tabulating multi-categorical data.

### What question(s) about the course are uppermost in your mind now? (not yet edited, first 38 responses)

#### Questions About Project 2, Specifically

- Will we discuss our Project 2 work in small groups like we did with Project 1?
    - I don't know. It would have to be on April 24 or 26. The main problems I see are that (a) students would have to have some sort of draft material in place quickly, when there are other things due and (b) what I could "cover" in lecture would be reduced a bit. But neither of those problems is serious to me. Let's do an instant poll. [What do you folks prefer?](https://goo.gl/forms/OhSDhLCrlmSUoLZ32)
- My biggest concern is just making sure I pick a data set that actually aligns with the goals of my data analysis. 
    - Good. That is a good thing to be focusing on. Developing a set of 1-2 research questions that can be addressed well with the data at hand is the most important thing. "[90% of directing a play/movie is casting](http://noamkroll.com/90-of-directing-is-casting-heres-why-you-need-to-prioritize-your-talent/)."
- Is our presentation about Project 1 **and** Project 2, or just Project 2? 
    - Just Project 2.
- Can I use "this method not taught in 431 or 432" in my Project 2? 
    - In your conclusions/discussion section, it's fine to bring up some other ideas that you'll follow up on in the future, but otherwise, no. Demonstrate what you can do with the tools taught in this course. Especially because not many "machine learning" methods actually beat well-tuned logistic regression or OLS models.
- Is there anything specific you want to see in Project 2? 
    1. Sure. There are about a dozen things. I want to see a clear statement of one or two research questions, preceded by an appropriate (but not at all lengthy) background section motivating those questions.
    2. a clear description of the data to be used, with careful attention to cleaning the data to make the follow-up analyses as straightforward as possible.
    3. the use of techniques from the 431-432 sequence for every stage of the data science process, from data ingest and tidying through the cycle of transformation, visualization and modeling, and then finally a careful communication of the end result.
    4. the use of regression methods (which can include OLS, logistic models, and the more recently discussed methods for count, multi-categorical and (soon) survival outcomes) that are directly applicable to the research questions you posed at the start
    5. the use of appropriate tools for diagnosing the quality of those models, including visualizations and summary statistics
    6. identification and comparison of candidate models to address your research question(s) if there are real choices to be made (if you have a clear model in mind at the start, there's no need to use "best subsets" or something just to artificially create a competitor)
    7. validation of your models in an appropriate way if prediction is relevant to your research question(s), as I expect it will be
    8. clear evidence that you have thought hard, and well, about what pieces of output, specifically, think in terms of creating meaningful annotations for every single scrap of output that you generate and present: if you cannot think of anything to say about a piece of output easily, why are you including it?
    9. a clear re-statement of the research questions you asked at the start, now with conclusions that answer those questions
    10. a clear statement of the limitations of your approach, and
    11. a clear statement about useful next steps that you would like to try on the data, moving forward
    12. an extremely well-organized presentation of the portfolio, well-labeled, with good headings used throughout and making good use of the technology to create a table of contents that helps guide us to specific elements of your work quickly.
    13. I've added all of these thoughts to the [Project 2 Instructions](https://htmlpreview.github.io/?https://github.com/THOMASELOVE/432-2018/blob/master/projects/project2/project2-instructions-432-2018.html) document, which now includes section 4.1 entitled "What Dr. Love Wants to See" and section 4.2 entitled "A List of 12 Things I Definitely Want To See in Project 2" which, combined, say the same things in at least two different ways. Good luck!
    
#### More General Questions About Using The Tools We've Learned

- Do we graph model response probabilities for interpretive purposes or just for our own internal help with interpretation?  
    - Both, and more. What helps you helps the person for whom you're doing the analysis too, right? Some people are reluctant to accept the idea that some things are better done with visualization than with numerical summaries. Try not to be one of those people. I have a PhD in this stuff, and 30 years of practical experience. Graphs are great.
- When using gridExtra::grid.arrange() to place plots next to each other, how do you increase the space between the plots? 
    - This can be tricky. In my research work, I have started to use the `plot_grid` function in [the `cowplot` package](https://cran.r-project.org/web/packages/cowplot/vignettes/introduction.html) in this setting, to gain more control.
- Is there ever a case where we could use either a Poisson or an ordinal logistic regression? When does "counts" turn into "ordered categories" or vice versa?
    - There is certainly some potential for overlap. If the outcome is actually a count of something, it makes sense to run a model for a count outcome, otherwise not. Ordered categories include many things that aren't counts.
- If you have an outcome like a percentage that has a definite upper and lower limit is it always better to deal with it as a count outcome even if the distribution looks relatively normally distributed and without big walls and ceilings?
    - No. OLS is a perfectly reasonable way to deal with data that have theoretical but rarely reached boundaries. 
- What would be the best way to choose the reference group when we have multiple (nominal) categories?
    - It doesn't matter from a "how the model is fit" standpoint. R selects the first level in the factor. It is useful to think about how you want to interpret the results more than anything else. I usually use as the referent group the group that best describes the current "status quo" when such a thing exists.
- For count outcomes, should I build ZIP, ZINB, Poisson, Hurdle etc every time to determine the best fit model?
    - Certainly not. I'd start with a graph of the counts. If you have a clear floor at 0 with lots of 0 observations, then skip right ahead to a zero-inflated approach. If you don't, then try a Poisson model and check for overdispersion. If you see meaningful overdispersion, try a Negative Binomial model. Hurdle models are a last resort unless you really have an important ceiling and floor, because they're usually not a lot more effective than something like a ZINB. Tobit models are something beyond a last resort. You should usually be able to find a useful model (if there is one) in two fits.

## Individual Responses Required

- I don't have a lot of zero outcome. Can I still use zero inflated probit model? 
- Is the outcome of Poisson regression model Poisson distribution?
- Will the survival analysis section of this course help me to better understand what's going on in my survival analysis course?
- Still trying to find out how to export spline functions on logistic regressions (and beyond) but that may be more of a personal issue...
- Can we use regression on multi categorical outcome when we have asymmetric presentations of the outcome? 

```
what are the common peeking behaviors? 
I am curious about different types of graphics that can be used to demonstrate data to the reader.
In multinomial regression or ordinal categorical regression. How do we count the number of degrees of freedom available to us? What are the rules? are they the same rule (1:20 or 1:100) for linear and logistic regression respectively? 
Will we have similar small group discussion on project 2 as project 1? 
none
```

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
