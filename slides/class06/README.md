# 432 Class 06: 2018-02-01

### Key Materials

[The slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class06) and the [audio files](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class06) are now available.

In today's class, we'll continue to focus on linear regression model selection and cross-validation. 

## Announcements Before Class 06

1. Please don't forget to complete [Homework 2](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw2) by 1 PM Friday. Office Hours continue this afternoon from 2:30 - 4:30 and Friday from 12:15 to 1 PM.

2. There is a [minute paper Google Form](https://goo.gl/forms/uylKCzjUMAMeim0w2) for you to complete after Class 06, and before 10 AM on Monday 2018-02-05. Thanks! 

3. [Grades on Homework 1](https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw1/hw1grades.pdf) are now posted, by HW-ID number (Check your email for your HW-ID number.) 
    - If you have a concern/question about the assignment, let us know via 431-help or in office hours.
    - If you have a concern/question about **grading**, [follow the instructions here](https://github.com/THOMASELOVE/432-2018/tree/master/assignments#want-to-request-a-regrade-of-a-homework-assignment) to submit a regrade request. Thanks.

4. I've decided not to discuss stepwise regression meaningfully in today's slide presentation, but you can read about it further in the [Class Notes](https://thomaselove.github.io/432-notes/), Chapter 7. So let me just give you the idea for the Allen-Cady approach (described in detail in section 7.6) now.
    - Suppose you have a pre-specified ranking of predictors from "most important" to "least important" from a subject-matter perspective. Force into the model anything in the "most important" group.
    - Then starting from a kitchen sink model, let the computer try to delete predictors in order of ascending importance (checking the "least important" first) and stop when it either cannot improve the model by deleting further.
    - For instance, suppose you start with 8 predictors you don't want to force to be in, and rank them 1 (least important) to 8 (most important), run backwards stepwise regression on the kitchen sink, and at the first step check to see if variable 1 can be removed without damaging the AIC. If it can, drop it and check to see if variable 2 can then be removed without damaging the AIC. If at some point, the next variable (in terms of ascending subject-matter importance) cannot be dropped, then stop deleting and you have your candidate model.

5. There's a small edit in Section 3.2.2 of the Course Notes adding a footnote, which I made this morning in response to some student confusion. ANOVA works better when the data within each group being compared is well-approximated by a Normal distribution. Within each group, then, we'd hope the means and medians are similar. Across groups, they may be quite different, of course.

6. The `leaps` package, and in particular the `regsubsets` function, does not handle variables of "character" class. They must all be factors. 
    - For instance, in doing HW2, if you run `hbp330 <- read.csv("hbp330.csv") %>% tbl_df`, this will work in question 4 while `hbp330 <- read_csv("hbp330.csv")` will not. 
    - This is because `read_csv` assigns the character class to all variables with letters in the data, while the `read.csv` then `tbl_df` workflow doesn't do this. 
    - Or you can do `read_csv` and then apply `df %>% mutate_if(is.character, factor)` to change all of the character variables in `df` to factor variables. 
    - This is another "[strings as factors](https://simplystatistics.org/2015/07/24/stringsasfactors-an-unauthorized-biography/)" problem. 
