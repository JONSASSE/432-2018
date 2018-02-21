# 432 Class 12: 2018-02-22

### Key Materials

- [The slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class12) above cover logistic regression on the Framingham data, and then linear regression with `ols` in the HERS trial. In the context of that `ols` fit, we'll be running multiple imputation.
- The [audio files](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class12) will be posted as soon as they are available.

## Announcements Before Class 12

1. [Homework 4](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw4) is due at 1 PM on Friday 2018-02-23. 
    - If you read Question 1, it says "After age, sex, socio-economic status and smoking have been controlled for, is there an additional risk associated with keeping a bird as a pet?" That is the question you are to answer. It's an *explanation* question, not a *prediction* question. 
    - I also described some things you need to do, all of which make reference to the **same** model. That suggests that you should be fitting and evaluating one model. Not many models.
    - There are many other ways that I could have used this data to set up a homework assignment, but that are **not** what I actually did. For example, I could have written "Build a really strong prediction model that uses some subset (and perhaps both linear and non-linear representations) of the listed predictors to best discriminate between lung cancer patients and non-lung cancer patients." That would have been a very different homework assignment. 
    - Try to match your response to the question I actually posed, rather than demonstrating that you *can* answer a much more involved question than I asked.

2. Your [project 1 proposal](https://github.com/THOMASELOVE/432-2018/blob/master/projects/project1/README.md#the-proposal) is also due at 1 PM on Friday, 2018-02-23.

3. Chapter 14 in the [Course Notes](https://thomaselove.github.io/432-notes/) is complete. 
    - It builds a pair of logistic regression models to predict the binary `exerany` variable in the BRFSS data we've analyzed earlier.
    - The Chapter includes a complete case logistic regression analysis (to be sure the code runs) and then full logistic regression model analyses, first using simple imputation, and then using multiple imputation.
