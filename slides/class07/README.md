# 432 Class 07: 2018-02-06

### Key Materials

[The slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class07) and the [audio files](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class07) will be posted as soon as they are available.

In today's class, we'll discuss the incorporation of non-linear terms in a linear regression model, and discuss the use of `ols` to fit and evaluate linear models. That material is in Chapters 9-10 of our Course Notes.

## Announcements Before Class 07

1. Homework 2 Answer Sketch is available in [R Markdown](https://raw.githubusercontent.com/THOMASELOVE/432-2018/master/assignments/hw2/hw2sketch.Rmd), or [HTML](http://htmlpreview.github.io/?https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw2/hw2sketch.html), or [PDF](https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw2/hw2sketch.pdf).

2. We'll spend a few minutes reminding you about [Course Project 1](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project1) during Class 08 on Thursday. 
    - Your [project 1 proposal](https://github.com/THOMASELOVE/432-2018/blob/master/projects/project1/README.md#the-proposal) is due on 2018-02-19.

3. Updates in the [Course Notes](https://thomaselove.github.io/432-notes/) over the weekend
    - I've made a few small edits in Chapters 1-7, especially 1 and 5. 
    - I've made some meaningful edits to Chapter 8. 
        - In particular, I added some material to clarify the calculation of *uncorrected* AIC, and how it (a) differs from bias-corrected AIC, (b) provides no new information beyond what we get from Mallows' Cp in the linear regression setting, and so we don't plot it and (c) is only defined up to an additive constant, so `extractAIC` and `AIC` give different results when applied to a single model, but when comparing two models, either can be used. 
        - I also dropped the non-ggplot2 approach to plotting, and 
        - I added some material on interaction terms, and on the limitations of best subsets regarding the development of best subsets work with multicategorical variables.
    - New Chapters:
        - 9 (on incorporating non-linearity in a linear regression model, particularly polynomial regression and spline models), 
        - 10 (on using `ols` to fit and evaluate linear models), 
        - 11 (which provides brief demonstrations of the use of ridge regression and the lasso), 
        - 12 (introduction to logistic regression ideas)
        - 13 (a first detailed example of logistic regression, including both `glm` and `lrm` approaches to fit and evaluate models)
    - The next chapters on my "to do" list involve (a) another, more complex logistic regression example, including some material on probit regression, and (b) the use of multiple imputation procedures, in some order.

4. **What's coming up?** (A tentative plan)
    - Class 07: discuss materials in Chapters 9 and (some of) 10 on linear regression
    - Class 08 and likely 09 and maybe also 10: discuss materials in Chapters 12 and 13 on logistic regression
    - After that: return to linear regression and finish things from Chapters 10 (if needed) and 11
    - And then: more logistic regression, probit regression, and multiple imputation
    - I may wind up reordering the Course Notes at some point.
    
## Comments on the Minute Papers after Class 06

### What was the most important thing you learned related to 432 this week? 

The most popular answers, overwhelmingly, were:

- Using the "best subsets" idea to select candidate sets of predictor variables in a linear regression model
    - This includes things like learning how to consider Mallows Cp, bias-corrected AIC, BIC and adjusted R^2^.
- Using cross-validation to select a sensible choice of prediction model from a set of candidates.
    - This includes things like learning how to consider both out-of-sample and in-sample performance in model evaluation.   
- The general realization that no one model is perfect. 
    - Some models are useful. Some aren't. It's usually better to accept multiple models are similarly attractive for real data.
    - It will be rare that one model will be the best in all ways, in all settings and for answering all questions.

Other things people mentioned included:

- Methods for comparing models that do and don't work when the models are *unnested*, in the sense that neither is a proper subset of the other.
- Simple imputation approaches
- Jeff Leek's lessons about data sharing and contextualizing them in current academic culture
- Our [Project 1 proposal](https://github.com/THOMASELOVE/432-2018/blob/master/projects/project1/README.md#the-proposal) is due on February 19. That's less than two weeks away.

### Have you given any serious thought to Project 1 yet? 

Count (%)  | Response
---------: | ---------------------------------------------------------------------------------------------
2 (6%) | Yes, and I have a data set in hand that I can use that is shareable with the world, of appropriate size.
4 (11%) | Yes, and I have a data set in mind, but I don't have the data in my hands yet.
15 (42%) | Yes, I've thought about it, but I don't yet have a data set in mind. I need to get going on that.
15 (42%) | No, but I will soon look over the Project 1 instructions on our web site so I can get up to speed.

If you're in those bottom two categories, it's time to get moving. Your [Project 1 proposal](https://github.com/THOMASELOVE/432-2018/blob/master/projects/project1/README.md#the-proposal) is due on 2018-02-19.

### What question(s) about the course are uppermost in your mind now?

1. Logistic Regression
    - which we'll begin to talk about on Thursday of this week.
2. Is there such a thing as a "true" model, or a "correct" model. Or are models just relatively better or worse, in most cases?
    - Models simplify reality. No useful model fit to meaningful real data explains perfectly everything that happens.
    - All models understate the complexity of the world around us. Some of them do so in ways that allow us to make scientific progress better than others, so we aim for those.
    - Sometimes our goal is excellent prediction in new data based on a model. Then it's easy to see that many models might be helpful, to varying degrees.
    - At other times, our goal isn't really prediction, but instead it is trying to identify causal effects, or explain how the world actually works. That's much harder, and the best strategies involve moving away from binary decisions (yes, this is important and significant vs. no it isn't) and towards embracing uncertainty and complexity.
3. A related question to that one was "When adjusted R, Cp, AIC, and BIC all say differently, what should I go with, in terms of choosing the best subset?" Another was "When should I use one stepwise procedure instead of another? (Forward vs. Backward vs. Allen-Cady, for example.)
    - The answer is don't make binary choices about good/bad methods or summaries if you're interested in prediction. At the least, select a set of candidate models based on those methods, and evaluate them in a model test sample or through cross-validation.
    - And if you're interested less in prediction, but rather in estimating causal effects or trying to replicate the work of others, then you probably won't want to put any real emphasis on reducing the size of your models. I'm not sure best subsets (or stepwise approaches) are particularly helpful at all in those settings, where deleting an important variable is way, way more problematic than is including one that doesn't help much.
    - The Allen-Cady method is just one of many ways to try to incorporate subject matter information into an "automated" statistical procedure. This is almost always (a) difficult to do well and (b) extremely important to do.
4. If all of the R^2 values are small, should I still use linear regression models to predict the outcome?
    - It depends on the question you're trying to answer, and the alternative modeling strategy you have in mind. Some phenomena are inherently harder to predict than others. Some data lend themselves to linear models that approximate reality more effectively than others.
5. How do you know if you need to transform a predictor variable?
    - The best times are when you have a meaningful leg to stand on before fitting a model, be it clinical/biological or mathematical insight about how the world works that implies a particular non-linear relationship. This is more often true for establishing the importance of an interaction (in my experience) than a particular type of curved relationship.
    - The tougher times are when you have to try to estimate a model without that sort of background knowledge, and are stuck with using the model development data to make transformation decisions. There are a number of ways in which even modern methods can get you into trouble in such a setting.
    - It takes a team (including subject matter experts, people focused on gathering the data, and people experienced in a range of model-building strategies) to build a good, useful prediction model for a phenomenon that is actually interesting.
6. I don’t have a great understanding of degrees of freedom and how these are important to our models. 
    - Think of degrees of freedom as an index of the amount of data available to you in a model. You spend degrees of freedom every time you estimate something. And give yourself some time to let the ideas sink in, as you gain experience.
    - Modern biostatistical work takes degrees of freedom to be an especially scarce resource, and tries to spend them wisely, without biasing the eventual results.
7. What is the best way to deal with a ANOVA when one of the category levels has a zero sample size, perhaps in an interaction.
    - Stop thinking you can describe that category or interaction effectively in the data you have.
    - Collapsing categories is dangerous business. There are lots of ways to get in trouble, and sound advice in most settings is to keep things as granular as you can. This often means you can only make reasonable estimates for some of your data, not for all of it.
8. Does one ever get to the point where they can enter in R code without having to "crib" other people's code?
    - R is a language. There is a substantial amount of time you need to invest to do things well. Hadley Wickham googles things every day, even about code he wrote. We all make mistakes, constantly.
    - I found that if I didn't use it for a few days, then R pre-tidyverse was very slow for me to recall, and I made many, many mistakes. Now, with the tidyverse, I learn more about data quickly, and the tools get out of my way more frequently. But I still have to solve problems about how to move forward regularly, and I reuse my own code (tweaking details) daily.
    - As to the general point, so what? When would you ever be in a situation where tweaking someone else's code to do something routine couldn't happen? And if it's not routine, the whole point of R is that someone else has probably worked on it.
9. What does it mean to over-fit or under-fit a model?
    - In a perfect world, all of our models would be neither over- or under-fit. They would include everything important, and nothing more.
    - Overfitting in our context means including more predictors than are needed to reflect the structure behind the data, so you're including predictors that don't include much "signal" but just add "noise". 
    - Underfitting refers to missing too much of the "signal" in an effort to make the model more parsimonious, and happens when you leave out important features of the data, thus missing some attainable "signal" for your predictions. 
10. If you think sex interacts with both race and treatment in predicting an outcome, how could you fit a model to indicate that?
    - Try something like `lm(outcome ~ age + sex*race + sex*treatment + age + other variables, data = dataset)`
    - In a related matter, I essentially never look at three-way interactions in practical work unless I've got biology and logic which demand them. If I'm exploring, I tend to focus on other ways of looking at more complex relationships, like stratification, weighting, and matching in the context of estimating causal effects.
11. In cross-validation of a linear regression model, what do you recommend in terms of the number of folds for our validation? (In other words, what do you recommend we use for k in k-fold cross validation?)
    - The most common choice in gene expression data appears to be 10. Recommendations from Hastie & Tibshriani appear to be 5 or 10.
12. Do you anticipate the leaps package eventually being absorbed into the tidyverse?
    - No idea. It's more likely that something along the lines of `modelr` would be built to help with some key model selection tasks. But I don't think `modelr` is really on the front burner for R Studio.
13. When is centering and rescaling most often called for?
    - I [answered this last week](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class05) in response to a Minute Paper question.
14. Is it possible to work on Project 1 or Project 2 for 432 with a partner?
    - For Project 2, yes, definitely. For Project 1, make a proposal to me about why it's worth doing well in advance of the deadline, and I'll listen. But I'm less inclined for Project 1 because I want you all to be coding, and working on helping others in a small group improve their code, as part of that Project.
15. Will you help me find a data set for Project 1 or 2?
    - Nope. Read [this description of the characteristics of an acceptable Project 1 data set](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project1#characteristics-of-an-acceptable-data-set) which has some advice.
16. What do you recommend I read to learn more about how to most effectively do "type of analysis X" or how to choose between "approach A and approach B" in doing "type of analysis X"?
    - There are lots of good resources in the world. Three excellent books on regression analysis are listed below, but I don't recommend you **read** anything, really. Instead, I recommend you develop a project with data you care about where such an analysis seems likely to be appropriate, and do the work, then look to see what happens when you make different decisions. That's the best way to start actually gaining useful experience.
        - Frank Harrell's stuff is intimidating but great at http://www.fharrell.com/#links, and his Regression Modeling Strategies materials are especially relevant to our course.
        - Julian Faraway's two books *Linear Models with R* and *Extening the Linear Model with R* are great, too.
        - Eric Vittinghoff et al. have a great book called "Regression Methods in Biostatistics: Linear, Logistic, Survival, and Repeated Measures Models" but they use STATA rather than R.
        - In a few years, I expect the best book on regression and many related matters is likely to be the new two-volume epic coming from Andrew Gelman and colleagues. But that doesn't yet have a release date. Gelman's book with Jennifer Hill entitled "Data Analysis using Regression and Multilevel/Hierarchical Models" is outstanding, and uses R, but I've never been able to figure out how to teach the multilevel material well in two semesters. 
        - Another book anyone interested in data mining and machine learning should read is Hastie and Tibshriani's [Elements of Statistical Learning](https://web.stanford.edu/~hastie/Papers/ESLII.pdf) I regret never making my way all the way through the book, but I've read at it dozens of times.
