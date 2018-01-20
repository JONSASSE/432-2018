# 432 Class 03: 2018-01-23

### Key Materials

As they become available, [the slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class03) and the [audio files](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class03) will be posted above.

In today's class, we'll focus on:
+ Analysis of Variance and related topics from Chapter 3 of the Course Notes
+ Validation of a linear regression model

## Announcements Before Class 03

1. **Taking Notes?** A student in the class requires the help of a note-taker. If you are willing to provide a copy of your accurate and legible in-class notes to a fellow student (and receive a small stipend for this service) then please contact ESS Disability Resources by calling 216.368.5230 to schedule a brief interview and get some more information. You'll need to provide them with:
    + your name, 
    + the name of the course (PQHS 432/CRSP 432) and 
    + the instructor's name (Thomas Love). **Thank you!**

2. Stuck on how to build categories in **Homework 1**?
    + You might try the `cut2` function from the `Hmisc` package, or
    + You might try using `case_when` as demonstrated in Chapter 3 of the [Course Notes](https://thomaselove.github.io/432-notes/).

## **Minute Papers** after Class 02 (edited responses)

1. What was the most important thing you learned during the 432 class so far?
    - Building Table 1. (x15)
    - How a response with a "floor" and a "ceiling" can adversely affect a linear model (x7)
    - Interaction terms / product terms and how to evaluate them (x6)
    - Data Sample Summary methods, including using `skew`, `count` and `table` functions. (x3)
    - The process of choosing an appropriate linear regression model. (x2)
    - Look at the data carefully before launching into modeling. (x2)
    - Cleaning up data is time-consuming and not trivial but worthwhile.
    - You need to "listen fast" in this course. It moves quickly.
    
2. What question(s) remain uppermost in your mind at this point? (roughly from more common to less common)
    - How do you fit a model to describe a response that has a floor and a ceiling? A hurdle model?
    - How do you select the best variables to include in a regression model?
    - How do you interpret interaction terms in a model? Is this a "multiplicative interaction"?
    - What do we learn from the ANOVA as opposed to the summary of a linear model?
    - Why do we need to use R to build a Table 1 instead of Excel?
    - How do I deal with missing data without ignoring it? How much missingness can we ignore, safely?
    - What do we do about reporting missing values in Table 1? Should we impute in building Table 1?
    - How do you customize the HTML appearance of a Markdown, like with the Project 1 template?
    - What is the difference between linear and logistic regression analysis?
    - Why do I need a GitHub account?
    - Are you going to discuss **this thing I care about a lot** this semester?

3. How confident are you about your ability to successfully complete Homework 1, due Friday 2018-01-26?

Very confident | Somewhat confident | Not confident | I don't know yet | Responses | Enrolled Students
:-------------: | :-------------: | :-------------: | :-------------: | :-------------: | :-------------:
9 | 20 | 2 | 7 | 38 | 44


## Announcements After Class 03
