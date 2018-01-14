# Topics by Section

The course is divided into several sections. See [the Schedule](https://github.com/THOMASELOVE/432-2018/blob/master/SCHEDULE.md) for more details on the timing of these sections.

## Section 1. Linear Regression

The material we'll present on linear regression includes:

- Review of the Fundamentals
- Building a Linear Regression Model to Make Accurate Predictions
- Building a Linear Regression Model to Describe an Association Accurately
- Building a Linear Regression Model for Risk Adjustment
- Proper use of a Spearman Rho-Squared plot
- Incorporating Predictor Transformations in a Regression Model
- Variable Selection with Cp, AIC, BIC and adjusted R^2
    - Best Subsets approaches to Variable Selection
- Two-Way Analysis of Variance, with and without interaction
- Analysis of Covariance
- Multi-factor ANOVA, designing experiments
- K-Fold Cross-Validation in a Regression Model
- Dealing with Missing Data
    - Incorporating Simple Imputation in a Regression Model
    - Incorporating Multiple Imputation in a Regression Model
- Weighted Linear Regression
- Robust Linear Regression

### Maybe we'll also include...

- Machine learning methods like the lasso and elastic net 
- What you should do inferentially with matched groups larger than pairs (liked matched trios) in analyzing quantitative outcomes.

## Section 2. Logistic Regression

The material we'll present on logistic regression includes:

- fundamentals of the models (link function, interpretation, etc.)
- models for binary outcomes
- models for proportions
- discrimination through C statistics, etc.
- calibration of logistic regression models
- building risk adjustment models

## Section 3. Generalized Linear Models

The material we'll present on generalized linear models (of which linear and logistic regression are subsets) includes:

- Models for count outcomes, and this will include: 
    - Poisson regression 
    - Negative Binomial regression
    - Zero-inflated approaches
    - Dealing with overdispersion
    - Hurdle models
- Models for Multi-categorical outcomes
    - Ordered logistic regression
    - Nominal multi-categorical models

## Section 4. The Statistical (Replicability) Crisis in Science

To be determined, but I'll clearly pull a lot of materials from [Andrew Gelman's blog](http://andrewgelman.com/) and from Jeff Leek's [How to be a Modern Scientist](https://leanpub.com/modernscientist).

- Problems with P values, Garden of Forking Paths, Registering Your Analyses
- Moving past Post-Hoc Power Calculations

## Section 5. Cluster Analysis

Specifically, I'll present a demonstration or two of principal components analysis to reduce dimensionality in a regression problem.

## Section 6. Survival Analysis

- Kaplan-Meier curve estimation and interpretation
- Cox proportional hazards regression models

## Sections 7 and beyond. To be determined

- We will determine what else we will discuss as the semester progresses.
- I will spend one session near the end of the course talking about estimating **causal effects** which is the main focus of my **PQHS 500** course on Observational Studies.

# Potential 432 Topics So Far

This post was developed during 431. I have placed it here for ease of reference as I craft the course. I do not guarantee to stick to this.

Topic | Covered in 432?
-----------------------------------------------------------------------: | :---------------:
Two Projects, Short(er) Quizzes, [Minute Papers](http://oncourseworkshop.com/self-awareness/one-minute-paper/), Statistics in Action, Live R demos, Working in Pairs, 431-help, Teaching Assistants, Love-boost as an R package | Definitely the plan.
Better Distribution of Work Throughout the Term | A major goal.
Audio-recording of lectures | Yes, I believe so.
Jeff Leek's "[How To Be a Modern Scientist](https://leanpub.com/modernscientist)" | Yes, we'll read it all.
Building a Decent Table 1 without going nuts | Class 1
Transforming predictors, polynomial regression, restricted cubic splines | Section 1
Approaches other than stepwise AIC and hypothesis tests for variable selection | Section 1
C_p and Best Subsets Regression | Section 1
Multi-factor ANOVA, designing experiments | Section 1
Imputation and analysis with missing values | Section 1
Weighted Linear Regression and Robust Linear Regression | Section 1
[Cross Validation](https://www.youtube.com/watch?v=OwPQHmiJURI) to avoid [Overfitting](https://www.youtube.com/watch?v=CmEqvD_ov2o) | Section 1
How many observations do I need to fit [a linear](https://www.sciencedirect.com/science/article/pii/S0895435615000141) or [a logistic model](https://twitter.com/f2harrell/status/936230071219707913) reasonably? | Sections 1,2
Logistic Regression | Section 2
Regression models for count data (Poisson, Negative Binomial) | Section 3
Regression models for multi-categorical outcomes | Section 3
P values, Garden of Forking Paths, Registering Your Analyses | Section 4
ASA Statement on P values | Section 4
[Beyond Power Calculations](http://www.stat.columbia.edu/~gelman/research/published/retropower_final.pdf): Gelman's retrodesign function to assess an inference after the fact | Section 4
Cluster Analysis, Principal Components Analysis | Section 5
Kaplan-Meier estimator, Cox proportional hazards models | Section 6
Causal Effects | Just enough to encourage you to take 500
Data Management: Wrangling/Rectangling using the Tidyverse and [R for Data Science](http://r4ds.had.co.nz/) | Projects, Homework
Merging Data Sets, and the notion of Split-Apply-Combine | Projects, Homework
Communicating the Results of Statistical Models Well | Projects, Homework
Reading and Critiquing the Code of Other People, Reproducible Examples | Projects, Homework
Building a Web-Based Presentation of Your Work | Projects, I hope
Pulling data from the web | Homework

## Other Things I Hope to get to but cannot yet promise

- Using GitHub and [Happy Git with R](http://happygitwithr.com/) for more than we did in 431
- Learning [a little Shiny](https://shiny.rstudio.com/)
- Log-Linear Models for Contingency Tables 
- Classification and Regression Trees
- Building a Quantile Regression Model
- Mixed Effect Models 
- Hierarchical Linear Models
- Machine learning methods like the lasso and elastic net
- Sensitivity, Specificity, ROC analysis 
- BART
