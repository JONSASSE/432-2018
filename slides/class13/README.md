# 432 Class 13: 2018-02-27

### Key Materials

- [The slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class13) above cover ridge regression and the lasso.
- The [audio files](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class13) are now available.

In today's class, we'll discuss ridge regression and the lasso, amplifying on what you'll find in [Chapter 11 of the Course Notes](https://thomaselove.github.io/432-notes/other-variable-selection-strategies.html).

But first, we'll discuss a few of my thoughts on the project proposals, which I'll boil down to these three notions:

1. The most challenging and rewarding place to put your effort is in obtaining good data that can actually speak to an issue of interest. Such data are very, very hard to find, even in our data-centric times. From [Sean Taylor](https://twitter.com/seanjtaylor/status/968147593845813250?ref_src=twcamp%5Eshare%7Ctwsrc%5Eios%7Ctwgr%5Eemail%7Ctwcon%5E7100%7Ctwterm%5E1) "Unpopular advice: if OLS doesn't work then you should give up and get better data.
2. An essential part of any statistical activity is how you communicate what you did, and what the findings are. The number one issue is clarity. Writing/speaking/presenting clearly takes time, and effort. 
3. Statistics in particular and Science more generally is a details business. You need to get all of the details right. This means spelling, grammar, syntax, capitalization, formatting, labels, fonts, outlining, everything. Everything matters.

As a quick example, to what extent did you allow yourself the time to ensure that the HTML output you created was edited in such a way as to make your key points clearly, without the distraction of errors, mislabeled materials, problematic formatting, and so forth?

## Announcements Before Class 13

1. [Answer Sketch and Grading Rubric](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw4) are up for Assignment 4. I've also posted grades for HW1 - HW3 on [Canvas](https://canvas.case.edu/). If you see an error in those posted grades, please let me know.

2. [Assignment 5](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw5) is due this Friday, 2018-03-02 at 1 PM.

3. [Quiz 1](https://github.com/THOMASELOVE/432-2018/tree/master/quizzes/quiz1) will be made available to you by noon on Friday 2018-03-02. It is due at noon on Monday 2018-03-05. 
    - The data you'll need to do the quiz is now [available for download](https://github.com/THOMASELOVE/432-2018/tree/master/quizzes/quiz1).
    - Quiz 1 is taken on a Google Form (like our Minute Papers), requires you to log into Google via CWRU, contains 32 questions, and covers:
        - material discussed in Chapters 1-15 of the Course Notes, and 
        - material in the [required readings](https://github.com/THOMASELOVE/432-2018/blob/master/SCHEDULE.md) from [How to be a Modern Scientist](https://github.com/THOMASELOVE/432-2018/tree/master/texts) and [R for Data Science](http://r4ds.had.co.nz/), and 
        - material discussed in class through Class 14, 
        - with the single exception being that I promise that ridge regression and the lasso will not appear on Quiz 1.

4. Chapter 15 of the [Course Notes](https://thomaselove.github.io/432-notes/) is now posted. It recapitulates the material we discussed in Class 12 on using `ols` to fit linear models.

5. `lrm` and `ols` and `rms` functions in general, are usually looking for categorical data to be included using **numerical codes**. 
    - If, for instance, you try to do something after you've included a sex variable that has the values M/F, rather than something like female = 1/0, you may get error messages like **Error: Can't use matrix or array for column indexing**. That's an indication that R is looking for a numeric variable and not finding it for some categorical data. 
    - This comes up, for instance, when plotting an ROC curve from an `rms`-based fit. But it's not an issue with `glm` or `lm`. Just another reason to know both approaches.
    
6. You may be interested in [this online learning community](https://www.jessemaegan.com/post/r4ds-march-challenge-participate-in-a-viewing-party/), which is working its way through R for Data Science, and holding a viewing party as its March challenge. Here's [more on the community and how to join](https://www.jessemaegan.com/post/join-the-r-for-data-science-online-learning-community/).

7. I added [several new packages](https://github.com/THOMASELOVE/432-2018/blob/master/data-and-code/PACKAGES.MD) to the list we want you to install. These packages, specifically `robustbase`, `quantreg`, `lmtest`, `sandwich` and `boot` will be used in Class 14's discussion of robust linear regression models.

## Project Proposals

All Project 1 Proposals have been reviewed by Dr. Love, as have all revisions to date.  All students have now completed this task.

The list of proposals [is now here](https://github.com/THOMASELOVE/432-2018/blob/master/projects/project1/projects2018.md).

