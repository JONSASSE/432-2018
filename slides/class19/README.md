# 432 Class 19: 2018-03-27

### Key Materials

- The [slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class19) and [audio files](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class19) will appear as they become available.

Today's class will address:

- my comments on Project 1 and on the minute papers after Class 18
- instructions for Project 2
- building regression models for count outcomes, in particular zero-inflated and hurdle models. We may also get to tobit models.

See [Chapter 18 of the Course Notes](https://thomaselove.github.io/432-notes/modeling-a-count-outcome-in-ohio-smart.html#where-to-read-this-chapter-1) for more on regression for count outcomes.

## Announcements at the start of class

1. Feedback on Project 1 is [available on this feedback page](https://github.com/THOMASELOVE/432-2018/blob/master/projects/project1/FEEDBACK.md) in addition to my specific comments to you on Canvas. You should have also received an email from me with your grade breakdown on Project 1.

2. An HTML file of the [instructions for Project 2](https://htmlpreview.github.io/?https://github.com/THOMASELOVE/432-2018/blob/master/projects/project2/project2-instructions-432-2018.html) is available, and there's a [README file with more details](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2), too. 

3. Kasia Kulma presents these [Prime Hints for Running a Data Project in R](https://kkulma.github.io/2018-03-18-Prime-Hints-for-Running-a-data-project-in-R/), and I think they're terrific.

4. [This workshop on data mining by Dick De Veaux on April 13](http://www.bio.ri.ccf.org/ASA/cspring.html) is absolutely going to be worth your time. You would need to register by April 2, and the cost for students is now $80. If you're in a PQHS program and interested / going, talk to me for a minute after class.

5. You may be interested in the new [reticulate package from R Studio](https://blog.rstudio.com/2018/03/26/reticulate-r-interface-to-python/) which is billed as "a comprehensive set of tools for interoperability between Python and R."

6. The next assignment is [Homework 6](https://github.com/THOMASELOVE/432-2018/tree/master/assignments), which is currently due at 1 PM on 2018-04-06. We'll see how far I get today. It may be that we'll wind up moving that deadline to a later date.

## Minute Papers after Class 18 (comments edited, a lot)

*Thank you for responding!*

### How satisfied are you with the quality of your Project 1?

Completely dissatisfied (1) | 2 | 3 | 4 | 5 | 6 | Completely satisfied (7) | n | mean 
--------------------: | ---: | ---: | ---: | ---: | ---: | ----- | ---: | ---:
1 | 2 | 1 | 8 | 17 | 7 | 2 | 38 | 4.76

The Pearson correlation of "score on Project 1" and "satisfaction with Project 1" is .34

### What is the most important thing you've learned in the past two weeks from the course? 

- Deciding what should and should not go into the presentation of a project
- Building an analytic plan, and making analytic decisions when building linear and logistic regression models
- Poisson regression and dealing with overdispersion
- Robust linear regression 
- Models for count outcomes
- Interpreting effect sizes (the "note" from Class 16 about effect sizes and how to estimate them, in particular)
- How easy it is to overfit a model, Cross validation and its importance

### What was the most difficult challenge you faced in doing your Project 1? 

- By far, the most common response was something about **what do I keep**?
    - How I should trim down my results? 
    - How should I choose which analyses are more important / necessary and which aren't?
    - How should I organize my results / interpretations / modeling?
    - In what order should I present these analyses?
    - Fear / paranoia that led me to include everything under the sun vs. containing the scope.
- The second most common response related to understanding the notion of "spending degrees of freedom".
    - Having a small data set, so that spending df was important.
    - How do I count the df I have spent?
- The third most common was dealing with potential non-linearity
    - Interpreting a Spearman plot
    - When should I use a Spearman plot
    - Choosing the number of knots to use in a restricted cubic spline (lots of people wanted to make plots to decide...)
    - Determining whether an interaction term is helpful before building a model
    - What is the role of a Box-Cox plot?
    - What is the role of a scatterplot matrix?

Other challenges listed included:

- Choosing a model from among a series of candidates.
- Variable selection in logistic regression.
- Selecting a data set that gave me fits.
- Trying to estimate BMI using weight (among other things) - an inappropriate predictor.
- Tidying the data sufficiently to let the modeling be straightforward
- Dealing with imputation
- R troubleshooting, fixing coding mistakes
- Something that worked in `glm` but didn't seem to work in `lrm` or vice versa.
- Dealing with having weak relationships between outcome and predictors.
- Generating an ROC curve.
- Time management. Working to a deadline.
- Life outside of the classroom / academic program.

### What question(s) about the course are uppermost in your mind now?

- What is coming in Project 2?
- What is the best way to present a model like the ones we created to an audience of non-statisticians? 
- Are there pros and cons to using cross-validation vs separating into test/training sample (and model generating on just the training sample)?  Which is generally more popular in actual research?  Or do people use both simultaneously to test their models?
- Can scales (e.g. Depression scale from 0-27) be considered as a count variable? 
- What's the best way to do model selection in logistic regression?
- Creation of a somewhat simple table that summarizes the models to use for the different types of outcome formats. 
- How do I save the course notes for future reference?
    - Actually, that one is straightforward. A PDF version is always available to you - I'll demo, and though the notes will disappear in June or so, you can always get the PDF for 431 and 432 for this year from me by just emailing me.
- For our research question in Project 2, if we know some variables which are directly affecting the outcome variable(let's say smoking for lung cancer), should they be included? Are we looking at them at all? Since we know that there is an association, should they be automatically included in whatever models we make?
- Is it "OK" to use a zero-inflated model in count data if you aren't sure the zeros arise from a different process than the other counts?
- I’m starting to envision the end of the course and not having ready access to Dr. Love for coding issues. Wondering if we are going to talk about how to solve coding issues once out of the course (besides just posting on stack overflow) 
    - My order is usually:
        - Help files / documentation within R
        - Google
        - [R Studio Cheatsheets](https://www.rstudio.com/resources/cheatsheets/) and [R for Data Science](http://r4ds.had.co.nz/)
        - [UCLA's Data Analysis Examples](https://stats.idre.ucla.edu/other/dae/)
        - My previous work / [Recommended Texts](https://github.com/THOMASELOVE/432-2018/tree/master/texts)
        - Talking to Humans / [R Studio Community](https://community.rstudio.com/) / [DataCamp](https://www.datacamp.com/) / Twitter / Github


