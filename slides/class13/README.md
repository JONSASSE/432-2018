# 432 Class 13: 2018-02-27

### Key Materials

- [The slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class13) above cover ridge regression and the lasso.
- The [audio files](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class13) will be posted as soon as they are available.

In today's class, we'll discuss ridge regression and the lasso, amplifying on what you'll find in [Chapter 11 of the Course Notes](https://thomaselove.github.io/432-notes/other-variable-selection-strategies.html).

## Announcements Before Class 13

1. [Answer Sketch and Grading Rubric](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw4) are up for Assignment 4.

2. All Project 1 Proposals have been reviewed by Dr. Love.
    + If your grade on Canvas is 10/10, you're done.
    + If it isn't 10/10, you need to fix the issues I described in my note on Canvas, and resubmit.

3. [Assignment 5](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw5) is due this Friday, 2018-03-02 at 1 PM.

4. Quiz 1 will be made available to you by noon on Friday 2018-03-02. It is due at noon on Monday 2018-03-05.

5. `lrm` and `ols` and `rms` functions in general, are usually looking for categorical data to be included using **numerical codes**. 
    - If, for instance, you try to do something after you've included a sex variable that has the values M/F, rather than something like female = 1/0, you may get error messages like **Error: Can't use matrix or array for column indexing**. That's an indication that R is looking for a numeric variable and not finding it for some categorical data. 
    - This comes up, for instance, when plotting an ROC curve from an `rms`-based fit. But it's not an issue with `glm` or `lm`. Just another reason to know both approaches.




