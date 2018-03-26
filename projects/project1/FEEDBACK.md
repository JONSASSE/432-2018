# Post-Project 1 Feedback from Dr. Love

The projects, on the whole, were very good. A few were excellent, and very few had many serious problems. 

## Comments on the Projects

Detailed comments specific to your project are available to you on Canvas.

### On Overfitting

The most common project problem in Tasks 10 (linear regression) and 11 (logistic regression) was overfitting (in terms of including more parameters in a model than can be reliably fit) and thus an overly optimistic summary of the quality of the models fit. Overfitting means more than just "the R-square looks much worse when we look at the index-corrected version from `validate` than it does when you first fit the model."

- Lots of people fit many, many models in a situation where doing so could not possibly lead to a reliable result.
    - Suppose, for instance, that you are building a logistic regression model, and you have 800 subjects in your data, with 200 subjects in the smaller of your two outcome categories.
        - How large a model can you fit?
        - Technically, you can have a degree of freedom for the intercept and probably 1 more for a single main effect of a quantitative or binary variable. So variable selection is very hard to justify.
        - I had people in this setting fitting models with splines, and interaction terms, and stepwise procedures, etc. but then not really looking at any sort of cross-validation. That's a big problem.
- You should make the decision about whether or not you'll spend any df on non-linearity before you run a Spearman rho-squared plot, which doesn't tell you if you should spend them, but does make useful suggestions as to how you should spend them. 
    - No Spearman plot says anything like "there is a significant nonlinearity involved" or even "there is nonlinearity we need to address" nor can it. 
    - There's no test of significance here, and the plot doesn't even indicate that nonlinearity is present in the data. It tells you NOTHING about whether there actually are any nonlinear effects. 
    - What it tells you is which variables have large enough main effects that if they also truly include non-linear elements, the non-linearity has a better chance of being large enough to be worth modeling.
- The primary problem is "peeking" at the relationship between outcome and predictors to make modeling decisions. When you do this, validation becomes essential, and even with validation you run a serious risk of overstating the accuracy of the model or the significance of predictors, and magnitude of summary statistics. 
    - Building scatterplots of individual predictors against the outcome to try to decide how many knots to put in a spline, for example, is peeking at the outcome-predictor relationship in an especially bad way. All of this EDA (exploratory data analysis) work is attractive and interesting, but it's peeking at the outcome over and over again, in ways that affect your ability to trust the final results, so validation is imperative.
    - The question you should be trying to answer in a real problem isn't just whether the outcome variable has a loess smooth when you look at a single predictor that bends, because that leaves out the multivariate impact of all other predictors.
    - I clearly need to discuss how many df you spend in real examples by doing things like the lasso, or best subsets, etc. (For instance, the lasso and best subsets in the same problem spend the same number of df.)
- People wanted to show their facility with variable selection via best subsets, the lasso, stepwise procedures, significance testing and other things, and I understand why, but the follow-up in terms of understanding the likely consequences of dredging the data for significant or large findings of this way was (generally) weak.
    - Lots of confusion on Spearman rho-squared and best subsets. Not clear why you would present both Spearman rho-squared and best subsets in the same analysis. You really shouldn't, practically. The only case where I might think that was appropriate would be if I was building three separate random samples, running Spearman rho-squared on one, best subsets on another, and comparing the two resulting models in a third.
        - You use Spearman rho-squared when you want to make decisions about including non-linear terms for a set of predictors in ways that will not bias your results (much) - it's an excellent choice when you want to be able to interpret the model in terms of explaining the data you have now without bias, but don't care much about prediction. Spearman rho-squared is most appropriate when [a] you have the predictors you want to include settled (so you're not going to add or subtract main effects from your model and [b] you need help thinking about which ones are the best candidates for non-linear or interaction terms in explaining the data you have in an unbiased way. By the way, the Spearman plot doesn't really mean that the interaction of variables with larger rho-squared values is in some way more likely to test out as significant or anything like that, but it does point you towards variables that (if they interact) look like they will have a bigger impact on the model as a whole. Also, the Spearman plot isn't used to drop variables from the model. It's used to help decide on non-linear terms. So if you use a Spearman rho-squared plot, you are committing yourself to the model you get from it, including the non-linear terms.
        - You use best subsets when you actively want to use the data to make decisions about which predictors to include in a model - it's an excellent choice if you don't need to be able to interpret the model you fit at face value, but care a lot about prediction. Best subsets is most appropriate when [a] the set of predictors (main effects) is larger than you think you need, and you want to whittle it down to the most important subset or two, and [b] you plan to use the model to predict new data, so validation is really important. ANOVA alone after best subsets isn't sufficient.
    - If you are going to use a more algorithmic or statistical approach to help you make decisions about subtler questions like whether a non-linear treatment of some information will be helpful in building a predictive model, you want to make use of multiple and modern tools to help you do so, rather than relying on p values or summaries like R square or even stepwise or best subsets approaches generated for the original data, without cross-validating your results.
- Many people indicated in Task 12 (conclusions/reflections) that they were confused about spending degrees of freedom, and about what should and should not be included in the final product. 
- I appreciate that you did a lot of work to build models and evaluate them, but you needed to edit that down considerably, and build a path to make this more than just a data mining activity.

In project 2, you should be justifying your choice of variables using some combination of LTE - that's logic, theory and prior empirical evidence. In thinking about which of your available variables to collect, or include in modeling, there is no good substitute for logic, theory and prior empirical evidence, and making these decisions without reference to those concerns would be disastrous. Whenever possible, logic, theory and prior empirical evidence should play the most important role in developing prediction models or models for causal inference. It is rare that those concerns alone will be sufficient in complex real-world scenarios, but they are always necessary.

**I need to provide more guidance on this subject, as I've clearly confused everyone**. I will work on something and provide it as soon as I can, so as to help you get an understanding of what we'll be looking for in Project 2, at the least.

### Some Specific Issues

1. **Using best subsets with logistic regression models.** Best subsets with the `leaps` package only applies to quantitative outcomes and linear regression. It is not appropriate for generalized linear models. 
2. **Using the lasso.** The lasso as we've seen it is only designed for quantitative outcomes. The `cv.glmnet` approach may be a good place to start in thinking more about this with non-quantitative outcomes. 
    - Also, the lasso requires categorical predictors to be treated as numbers. That doesn't mean you should use a lasso only on non-categorical predictors.
3. **Comparing models with and without imputation.** I was hoping you'd use multiple imputation. Doing a statistical test (like an ANOVA or AIC comparison) to compare a model fit with imputation to one fit without imputation doesn't make sense. We'd always prefer the model with imputation, regardless of what such a test suggests.
4. **Cross-validation in linear regression.** When you apply cross-validation in a linear regression or other model for a quantitative outcome, and then calculate prediction errors for comparison in a table or graph, you should show predictions from each model on the **scale of the original variable**, not the variable after transformation.
5. **Cross-validation in logistic regression.** This didn't go so well for people who tried to do more than just validate summary statistics like C and Nagelkerke R^2^. I need to provide additional guidance, I think.
6. **Scatterplot matrices were under-used.** I was surprised by how many people didn't show a scatterplot matrix. Doing so provides a grounding that many projects were missing. 
    - Including more than about 10 variables in such a matrix becomes overwhelming, but of course, the idea was for you to work with relatively small pools of variables so that such a plot would be helpful. 
    - At least in the linear regression setting, I would include a scatterplot matrix more often than not.
7. **Calibration plots.** Calibration of OLS models with the `calibrate` tool in `ols` does not currently work, at least not consistently. That's why I left it out of the course. 

## Some Project 1 Formatting / Minor Things

- **Task 3. (Listing a Tibble)** Task 3 was meant to be a listing of the tibble, although I was OK with you instead providing a glimpse of the tibble. I prefer a listing, in most cases, because that's how I know for sure that you have a tibble and not a data frame.
- **Sanity checks** are an important part of your programming, but they don't belong in your final presentation. Neither do false starts, and explorations that don't lead anywhere.
- **Fiddly things in the `rms` package.** Dealing with categorical variables, in particular, can be very tricky. Sometimes you need to specify that someting is a nominal or ordinal factor, and sometimes you can use `*` to define an interaction, and sometimes you need `%ia%`. I know this is confusing.
- **ROC curves.** Sometimes, the ROC curve with `geom_ribbon` that I demonstrated doesn't handle missing values well.

## Last Year's Notes

Last year, I compiled some notes on those projects. Some still apply, in particular the following ...

### TASKS 1-9 ISSUES THAT HOLD UP

- In Tasks 7 and 8, you need to clarify why a particular model (or set of predictors) is your focus. In Project 2, pay attention to this, and be sure that you have a clear transition in your thinking and your writing between your research question(s) and the initial list of predictors you will use in any models you build. You need to make those connections explicitly.
- Use NA or a blank cell in your imported csv file, not na or anything else, to indicate missing values. Otherwise, you'll have problems. na isn't the same as NA, and dots are particularly bad choices for NA.
- Generally, people who provided more detailed descriptions and motivations for their data management decisions were rewarded with simpler problems on the modeling side.
- If you create a factor in R with lots of levels, and later filter the data so that only some of the levels are still relevant, you can use the droplevels function to deal with this problem. Worth putting in your arsenal.
- If you are modeling a continuous outcome that must be positive (like, cost, or sales) and is right skewed, then it would be a bit of a surprise if a log transformation was not used.

### LINEAR AND LOGISTIC REGRESSION ISSUES THAT HOLD UP

- If you decide to transform an outcome, you should probably make that clear in subsequent work, giving it a meaningful name, or referring to, for example, the square root of your original outcome in your writing.
- If you have a C statistic or an R-squared of 0, or of 1, or very close to those numbers, then something is wrong.
- You should really describe a calibration plot in terms of the actual values, more so than the predicted ones.
- If you're going to show a p value, do so cautiously and with an explanation. p < 0.0000 or p = 0.0000 isn't anything. It might be meaningful to write that p < 0.0001, but it shouldn't be presented as equal to 0 or 1.

### COMMENTARY ISSUES THAT HOLD UP

- If you are going to submit a nomogram, you also need to describe the results and perhaps demonstrate what the model actually does. This is critical if you have meaningful interaction or non-linear terms, so you might focus on those predictors.
- If you send thomas dot love at case dot edu an email with the subject line reading extra point and the single word tukey in the actual message before the end of April, I will take that as a clear indication that you've read through all of this material, and give you a point on your class participation grade as thanks. Telling your colleagues directly about this is inappropriate. Encouraging them to read through the feedback page is an excellent idea, though.
- If you're only going to do a single imputation at the start, then you really need (as a sensitivity analysis) to do another one at the end (with a different seed) to identify how much (if at all) your key conclusions change about your models.
- Showing me everything you did, and making no effort to distinguish what is important, is more or less useless. All you've done is demonstrate the ability to mimic the modeling you've seen in class in some new data - the whole point of this is for you to pick elements of the results that are most important, and highlight their importance. Highlighting their importance is a part of your commentary, or it should be.
- An excellent comment from a student related to this was "it is still hard for me to have a whole picture of what I should do and what an organized analysis procedure should be." That is, in fact, the hard part, and it is why Project 2 will be harder than Project 1 in some important ways. Good luck.

### Project 2 "Changes" as a result of Project 1

1. In project 2, restrict yourself to understandable transformations, and don't be a slave to the Box-Cox approach. The reasonable transformations to consider are 1/y, log y, sqrt y, and y^2. Anything more complicated than that should suggest that you consider a different modeling approach or revision to your outcome.
2. In project 2, if you're fitting an interaction term between variables a and b, where a is quantitative and b is categorical, while also fitting a spline for a, then you must, in project 2, restrict the interaction to a linear interaction a %ia% b, and not an interaction on the whole spline with `a*b`. These interactions that include all the spline elements are just too complex.
3. The use of `echo = FALSE` is prohibited in Project 2. Everyone will use code-folding, so that the HTML can show or hide code as the reader desires.
4. In Project 2, you shouldn't need a scrolling box to display your code in the HTML file at any time in Project 2.
    - Use spaces and (especially) the ENTER key while coding to solve this problem and keep the width of your code below the character limit of your output.
    - If you're using the pipe, this is especially helpful advice - it makes your code much more readable to hit enter after every time you type `%>%`
    - This happens a lot in setting up a spearman rho-squared plot, but such a thing can be built up in multiple lines.
5. Use the `fig.height` command in an R chunk name to increase the height of the nomogram you build so that it will be legible. Sometimes this is important in building residual plots, too.
6. If you're using best subsets in a linear regression model, please do so only to identify multiple candidate models and then compare them not just with ANOVA or other significance tests in sample, but with validation in an outside sample, or at least cross-validation.
    - Also, in best subsets, use the more recent graphical approach for best subsets, as described in Section 8.4 of the course notes, instead of the old "arrows" method.
7. If you're building a scatterplot matrix (and you probably should) use `GGally::ggpairs` especially if you have categorical predictors, rather than the old `pairs` method. 
8. Adding the `sessionInfo()` command at the end of your work might be a good idea. I was pleased to see a couple of folks do this. Take a look, if you haven't, at what this produces. Why might it be useful?
9. In Project 2, you don't need to present everything in Project 1's Tasks 1-9, and you're not even required to format any of it in that way, but I would think you'd want to have most of that information at your fingertips in a presentation, so think carefully about what to keep and what to drop. Clearly, what is in Tasks 7 and 8 in Project 1 will need to be emulated using descriptions of your data (I doubt you can get away with not having a codebook) and your research questions to justify your modeling decisions.
10. For most projects, it would have helped to provide some pre-analytic insight into the expected direction of outcome-predictor relationships. This is certainly something to do in Project 2.
11. Give your models helpful names, and be consistent about it. If you want to avoid creativity, then call things Model 1 and Model 2, by all means, but do that in both the text descriptions and in your code. Don't call the same thing Model 1 (or my first model) in your text, but mod.6 in your code, as an example.
12. I was absolutely delighted by the few people who brought their conclusions back to proposed research questions explicitly. In Project 2, that should be something everyone does.

Mimicking what I did in my project 1 example is not a sign that you engaged with the materials. A lot of people ran a kitchen sink model and then best subsets, in many cases using the same language I used in the project example. That's not what I mean by showing that you've thought hard about what to do. The example could have been better in this regard, and many others, but I won't build a new one for Project 2, specifically because I want to help equip you to think through the issues on your own.

## Topics TEL is trying to write more about, when he can find the time...

1. Overfitting and how to think about spending degrees of freedom, including what the Spearman rho-squared plot does and does not do.
2. Cross-validation in linear regression models (including prediction errors on the scale of the original response, backing out of a transformation.)
3. Cross-validation in logistic regression, beyond the use of `validate`.
4. Multiple imputation procedures when `aregImpute` is not available.

## On Grades

The mean score on Project 1 was just over 85%, and the median was also just over 85%. 

- The ceiling was a little lower than I'd hoped, but the floor was much higher than I'd feared. The grades reflect this, as the standard deviation was quite low, at about 4.5 percentage points. Nearly 3/4 of the projects scored in the 80s.
- Scores between 70 and 86 seemed like "B" projects to me, and about 5/8 of the class fell in this range.
- Scores of 88 to 92 (note: no one scored 87) seemed like "A" projects to me. 
- 92 was the highest score on Project 1.

### Your grade on Project 1 is a percentage, based on the following elements, on which there were 120 available points:

- up to 20 points for work prior to the final portfolio, which includes the proposal and drafts for the working groups
    - Everyone got 20/20
- up to 5 points for meeting the deadline for the final portfolio
    - Most got 5/5
- up to 20 points for tasks 1-9 in your final portfolio
- up to 20 points for task 10 (linear regression) in your final portfolio
- up to 20 points for task 11 (logistic regression) in your final portfolio
- up to 20 points for task 12 (conclusions and reflection) in your final portfolio
    - For tasks 1-9, 10, 11 and 12, a project with nothing especially strong or weak and no serious problems got 17/20.
    - Most grades in each section fell between 14 and 18. No one scored 20 on any section, but there were a few 19s.
- up to 15 points for the quality of the project portfolio's HTML presentation
    - Statistics is a details business. Everyone had something that was a problem, some small, some not small.
    - A presentation with no problems at all - meaning a completely clean description of everything that was needed, including only the necessary code and output, without extraneous materials, spelling or grammatical errors, etc. - would have gotten 15/15. 
    - There were no 15s, and only one or two 14s. Most grades on this metric were between 10 and 13.

Add up those points and divide by 1.2 to get your score on the project.

