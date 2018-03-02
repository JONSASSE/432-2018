# 432 Class 14: 2018-03-01

### Key Materials

- The slides for Class 14 are [available in PDF](https://github.com/THOMASELOVE/432-2018/blob/master/slides/class14/432_2018_slides14.pdf) or [in R Markdown format](https://raw.githubusercontent.com/THOMASELOVE/432-2018/master/slides/class14/432_2018_slides14.Rmd).
- The [audio files](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class14) are now available.

In today's class, we'll discuss robust estimation of standard errors in linear regression and bootstrapping regression coefficients to deal with outlying values, mostly using an example based on crime rates in the United States.

Next time, in Class 15, we'll demonstrate five different robust linear regression modeling approaches, including bounded influence regression, penalized least squares and quantile regression.

## Announcements Before Class 14

1. [Homework 5](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw5) is due this Friday, 2018-03-02 at 1 PM. 
    + In question 4, there was some confusion regarding my original wording of the question, which I revised Wednesday morning. Our goal is to get you to adjust for (among other variables) sex, ideally incorporated as an indicator variable for female, which you'll have to create from the available information.
    + Please make this deadline. We will post [an answer sketch here](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw5) as soon as the deadline has passed, so we'll have to deduct points for late work that comes in after that sketch is posted.
    + [Grades for Homework 4](https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw4/hw4grades.pdf) are now available.
    + We have provided you with a set of [four of the essays we liked from HW 4](https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw4/hw4_essays_we_liked_2018.pdf) which might help you see what we're looking for. Thanks to the students who wrote these essays for their assent to include them in this list.

2. [Quiz 1](https://github.com/THOMASELOVE/432-2018/tree/master/quizzes/quiz1) will be made available to you by noon on Friday 2018-03-02. It is due at noon on Monday 2018-03-05. 
    - The data you'll need to do the quiz is now [available for download](https://github.com/THOMASELOVE/432-2018/tree/master/quizzes/quiz1).
    - The [link to actually take the Quiz is here](https://goo.gl/forms/eeckOVxyggvWYAN12). It will go live shortly after class 14 concludes. This link is posted [on the Quiz 1 page, as well](https://github.com/THOMASELOVE/432-2018/tree/master/quizzes/quiz1).
    - Quiz 1 is taken on a Google Form (like our Minute Papers), requires you to log into Google via CWRU, contains 32 questions, and covers:
        - material discussed in Chapters 1-10 and 12-15 of the Course Notes, and 
        - material in the [required readings](https://github.com/THOMASELOVE/432-2018/blob/master/SCHEDULE.md) from [How to be a Modern Scientist](https://github.com/THOMASELOVE/432-2018/tree/master/texts) and [R for Data Science](http://r4ds.had.co.nz/), and 
        - material discussed in class through Class 12 (plus a few specific "review" items from Classes 13 and 14, but will not include ridge regression, the lasso or robust linear models.
        
3. All Project 1 Proposals have been reviewed by Dr. Love, and all students have now completed this task. 
    - The list of proposals [is now here](https://github.com/THOMASELOVE/432-2018/blob/master/projects/project1/projects2018.md).
    - Don't forget that you're going to need to share your progress with colleagues one week from today. You'll do so by submitting your work to Canvas. I hope you'll have at least some 

4. If you're having trouble with grammar, syntax or other writing requirements of the class, please consider visiting the [CWRU Writing Resource Center](http://writingcenter.case.edu/).

5. If you're having trouble with typographical errors and misspellings, please consider using the spell check within R Studio. 
    - How can you use this tool in an R Markdown document?
        + A spell check button to the right of the save button (with "ABC" and a check mark).
        + Edit > Check Spelling...
        + The F7 key

