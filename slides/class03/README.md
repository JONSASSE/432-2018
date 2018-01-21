# 432 Class 03: 2018-01-23

### Key Materials

As they become available, [the slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class03) and the [audio files](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class03) will be posted above.

In today's class, we'll focus on:
+ Analysis of Variance and related topics from the Course Notes
+ Validation of a linear regression model

## Announcements Before Class 03

1. **Taking Notes?** A student in the class requires the help of a note-taker. If you are willing to provide a copy of your accurate and legible in-class notes to a fellow student (and receive a small stipend for this service) then **thank you**.
    + Please contact ESS Disability Resources at 216.368.5230 to schedule a brief interview and get more information.
    + You'll need to provide them with your name, the name of the course (PQHS 432/CRSP 432) and the instructor. 

2. Stuck on how to build categories in **Homework 1**?
    + You might try the `cut2` function from the `Hmisc` package, or
    + You might try using `case_when` as demonstrated in the Analysis of Variance chapter in the [Course Notes](https://thomaselove.github.io/432-notes/).

3. Thinking about simple imputation?
    + We'll use the `simputation` package to do this. I've just added this to our [packages to install](https://github.com/THOMASELOVE/432-2018/blob/master/data-and-code/PACKAGES.MD) list.
    + This approach works very well (and is quite flexible) for predicting quantitative variables, as well as categorical variables expressed with numerical codes. Sometimes, we'll impute the numerical code (as an integer variable) and then convert to a factor.
    + I've added a chapter on this in the [Course Notes](https://thomaselove.github.io/432-notes/).

## **Minute Papers** after Class 02 (edited responses)

1. What was the most important thing you learned during the 432 class so far?
    - Building Table 1. (x15)
    - How a response with a "floor" and a "ceiling" can adversely affect a linear model (x7)
    - Interaction terms / product terms and how to evaluate them (x6)
    - Data Sample Summary methods, including using `skew`, `count` and `table` functions. 
    - The process of choosing an appropriate linear regression model.
        + Although don't get the idea that there is one "correct" model in any real setting. "[All models are wrong, some are useful.](https://en.wikipedia.org/wiki/All_models_are_wrong)" - George Box.
    - Look at the data carefully before launching into modeling. 
    - Cleaning up data is time-consuming and not trivial but worthwhile.
    - You need to "listen fast" in this course. It moves quickly.
    
2. What question(s) remain uppermost in your mind at this point?
    1. **How do you fit a model to describe a response that has a floor and a ceiling? A hurdle model?**
        + We'll tackle this later in the semester, as soon as I figure out all of things I need to present first. 
        + A hurdle model is one way of attacking one particular piece of this problem, specifically, when we have a floor.
        + It is a two-part model that specifies one process for zero counts and another process for positive counts. 
            + The idea is that positive counts occur once a threshold is crossed, or put another way, a hurdle is cleared. 
            + If the hurdle is not cleared, then we have a count of 0.
    2. **How do you select the best variables to include in a regression model?**
        + So far, we've learned a stepwise approach to variable selection (in 431.) 
        + We will soon learn a method called "best subsets" that will be of interest here, although it's hardly the only alternative.
    3. **How do you interpret interaction terms in a model?**
        + If there's an interaction term, we interpret that first, making decisions about the inclusion of an interaction based on whether the interaction:
            - has a large effect on the outcome (as seen in a plot or table of the data),
            - accounts for a meaningful percentage of the outcome's variation and/or substantially improves model fit,
            - accounts for statistically significant predictive value
        + If the interaction is largely ignorable on several of those counts, we may wind up instead with a main effects model, excluding the product term. 
            - A main effects model is appealing because we can then study the individual factors more conveniently. 
            - Otherwise, the answer to the question "which level of factor A is better for this outcome" is always "it depends on factor B".
            - But, as we'll see, for interesting real-world problems, product terms often make an important difference in our interpretation of a model, and the quality of its fit.
        + Some of this is covered in the material we'll discuss in class today.
    4. **What do we learn from the ANOVA as opposed to the summary of a linear model?**
        + Several things. They look at different hypothesis tests, for example.
        + The `anova` function in R can be used to compare two nested models, but applied to a single regression model, it instead provides us with a sequential set of hypothesis tests. 
        + Again, this is covered in class today.
    5. **Why do we need to use R to build a Table 1 instead of Excel?**
        1. How would you calculate the summary values to include in the Table in Excel?
        2. **Reproducibility.** What if you built the Table 1 in Excel and then realized that one person in the treatment group was actually in the control group? 
            - If you've done the work in a script or R Markdown, then this will take somewhere between a few seconds and a few minutes to fix. Your work is reproducible, reusable, and shareable.
            - If you've done it in a spreadsheet, you're basically starting over from the beginning.
        - For more on why R vs. Excel, try [this link from the Revolutions blog](http://blog.revolutionanalytics.com/2014/10/why-r-is-better-than-excel.html) or maybe [this one from yhat](http://blog.yhat.com/posts/R-for-excel-users.html) 
    6. **How do I deal with missing data without ignoring it? How much missingness can we ignore, safely?**
        - Imputation is the strategy we'll be using to deal with missing data. As mentioned, the `simputation` package is a pretty good choice for simple imputation, and we'll have several solutions for multiple imputation before the semester is over.
        - There's a new chapter in the [Course Notes](https://thomaselove.github.io/432-notes/) on missing data and single imputation methods.
        - The amount of missingness that can be "ignored" varies substantially from problem to problem.
    7. **What do we do about reporting missing values in Table 1? Should we impute in building Table 1?**
        - Use footnotes to specify the number of people who have missing values.
        - Any Table 1 (not just in this assignment) should show real data, not imputed data.
    8. **How do you customize the HTML appearance of a Markdown, like with the Project 1 template?**
        - Take a look at R Studio's [R Markdown Formats page](http://rmarkdown.rstudio.com/formats.html).
    9. **What is the difference between linear and logistic regression analysis?**
        - Linear regression models are built to describe quantitative outcomes. Logistic regression models are built to describe categorical outcomes: most often, *binary* outcomes. Linear regressions predict *numbers*, logistic models predict the presence or absence of *attributes*.
        - For example, to estimate whether or not a patient presenting at the emergency department will be admitted to the hospital, we'd use a logistic model. To estimate the patient's heart rate at the time they present to the ED, a linear model would be used.
    10. **Why do I need a GitHub account?**
        + We're hoping that before the semester is over, we can figure out a way to facilitate your posting the best and most sharable parts of your project work to GitHub rather than just to Canvas.
    11. **Are you going to discuss *this thing I care about a lot* this semester?**
        + I have no more information for you than I've provided in [the Topics list](https://github.com/THOMASELOVE/432-2018/blob/master/TOPICS.md). 
        + If something you want to see is not there, or not there to your satisfaction yet, then please realize that threats, prayers, entreaties will all lead to me keeping a note in a file, but none of those things will have any immediate effect. Once we get to Spring Break, I'll revisit these issues, but not (much) before, and I can offer no promises.

3. How confident are you about your ability to successfully complete Homework 1, due Friday 2018-01-26?

Very confident | Somewhat confident | Not confident | I don't know yet | Responses | Enrolled Students
:-------------: | :-------------: | :-------------: | :-------------: | :-------------: | :-------------:
9 | 21 | 2 | 7 | 39 | 44


## Announcements After Class 03
