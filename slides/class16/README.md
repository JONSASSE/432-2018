# 432 Class 16: 2018-03-08

### Key Materials

- No slides today. There's more than enough in this README as it is. 
- At the bottom of this README is a [link to a Note](http://htmlpreview.github.io/?https://github.com/THOMASELOVE/432-2018/blob/master/slides/class16/class16note.html) I wrote to help us discuss the various types of effect estimates we can generate with `lm`, `ols`, `glm` and `lrm` model fits. 
    - I've made the note available in [HTML preview](http://htmlpreview.github.io/?https://github.com/THOMASELOVE/432-2018/blob/master/slides/class16/class16note.html) and in [R Markdown](https://raw.githubusercontent.com/THOMASELOVE/432-2018/master/slides/class16/class16note.Rmd) as well.
- The [audio files](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class16) will appear as soon as they are available.

In today's class, we'll demonstrate five different robust linear regression modeling approaches, including bounded influence regression, penalized least squares and quantile regression. We'll also discuss Quiz 1.

## Project 1 Groups for Discussion in Class

Group | Names
------: | -----------------------------------------------------------------------------
1 | Laura Baldassari, Jenny Feng, Maher Kazimi, Satyakam Mishra, Vinh Trinh
2 | Zainab (Albar) Albar, Dongze (Zaza) He, Nik Krieger, Andrew Shan
3 | Andrew Tang, Sneha Vakamudi, Ruipeng Wei, Peter Wilkinson
4 | Gwen Donley, Carli Lehr, Connor Swingle, Frances Wang
5 | Ryan Honomichl, JJ Huang, Xin Xin Yu, Bilal Zonjy
6 | Khaled Alayed, Kedar Mahajan, Preeti Pathak, Sarah Planchon Pope
7 | Estee Cramer, Laura Cremer, Hyun Jo Kim, Roberto Martinez
8 | Abhishek Deshpande, Jack McDonnell, Grace Park, Gabby Rieth
9 | Haimeng Bai, Sophia Cao, Kate Dobbs, Elina Misicka
10 | Vaishali (Vee) Deo, Caroline El Sanadi, Kaylee Sarna, Sandra Silva Camargo

### Your Group Tasks Today

1. Appoint someone to keep track of time. Try not to spend about 10 minutes of group time on any one project.
2. Everyone should discuss their project with the group for 2-3 minutes, helping the other people to understand what they're trying to do. Everyone should have a question to ask about their project. Be sure that you raise your question when describing your project, so the group has a meaningful place to start its discussions.
3. The group should try to tackle each question that is raised as a group first. If as a group you can't settle on a resolution, and need some "outside" help, let us know, and a TA or Dr. Love will come by and try to be helpful. 
4. Make sure everyone in the group can see the current work of everyone else in the group on Canvas. This may require some intervention by Dr. Love. In the meantime, Dr. Love has posted the HTML files for everyone [at this temporary location](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project1/temp) so you can download and then view them if necessary.
5. Over the break, you'll be finishing up your analyses, in preparation for an additional group discussion at our next class, on Tuesday 2018-03-20, and for your final submission of the project in advance of the deadline, which is Friday 2018-03-23 at 1 pm.

## Announcements before class

1. We will meet in Room E321-323 for the rest of the semester, **except for** April 5, when we'll meet in E301 again. 

2. I updated some of the Python advice in the [Class 15 README](https://github.com/THOMASELOVE/432-2018/edit/master/slides/class15/README.md). Thanks to several people for getting me some information there. I also fixed the spelling of Mississippi in the [Class 15 Slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class15).

3. Remember that we do not have class next week. Enjoy the break. Our next class is Tuesday 2018-03-20. 
    - After today's class, and before 5 PM this Friday, please complete [this Minute Paper](https://goo.gl/forms/kv5GJhm9Pjpcc5y73).
    - By Tuesday 2018-03-20, resubmit your Progress to Date on Project 1 to Canvas to facilitate review by your group.
    - The next major deliverable is your Project 1 final portfolio, which is due at 1 PM on Friday 2018-03-23.

4. **Changes in Deliverables and Deadlines** 
    - Homework 8 is cancelled. 
    - Homework 6 is now due on April 6, and Homework 7 is now due on April 13. 
    - Quiz 2 has been moved. It will now be available to you on April 20 and is due on April 23 at noon.
    - The [schedule](https://github.com/THOMASELOVE/432-2018/blob/master/SCHEDULE.md) and [syllabus](https://thomaselove.github.io/432-syllabus/) now reflect these changes. If you see something different somewhere, please let me know.

5. You will specify your preferred time for your Project 2 Portfolio presentation at the end of March, after complete instructions for Project 2 are available.

6. As mentioned above, there is a [Minute Paper](https://goo.gl/forms/kv5GJhm9Pjpcc5y73) to complete after today's class. Please do so by the end of the day on Friday 2018-03-09. Thank you.

7. The [grades on HW 5](https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw5/hw5grades.pdf) are now posted.

8. I told some people that scored below 80 on Quiz 1 that I would provide them with an opportunity to improve their grade, and that they would receive that today. With the Canvas issue, I haven't done that yet. I will get it to you as soon as I can, probably by this Saturday. This "makeup" task will be due at noon on Monday 2018-03-26.

### Quote of the Day, from Hadley Wickham (as quoted by [Database Hulk](https://twitter.com/DATABASE_HULK/status/971765242425499649))

> 80% of the time, importing data is boring and tedious. And then 20% of the time, it's just endless screaming.

### Tweet of the Day

[Some object lessons](https://twitter.com/coolbutuseless/status/971732818312097792) on testing large format ggplot printing.

## Most Important Tip for Future Homework or Project 1

For the rest of the semester, make it your business to ensure that your HTML file for finished work shows **ZERO WARNINGS and ZERO MESSAGES**. We don't want to see them. 
- You should figure out what to do to avoid the warning or message, when possible. 
- When it's not possible (for instance, when you load packages) you should use `{r , warning = FALSE, message = FALSE}` in your chunk name so that those messages are NOT printed in your HTML.

## Choosing From My Lists in Project 1

I provided lists of potential analyses for [Task 10](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project1#what-should-i-consider-doing-in-developing-linear-models-for-task-10) and for [Task 11](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project1#what-should-i-consider-doing-in-developing-logistic-models-for-task-11) for your Project 1. But you should be **choosing wisely** to produce a curated and appropriate final set of analyses responding to each Task, not demonstrating your ability to do all of those things.

- You need to settle on a single model for a quantitative outcome (in Task 10) and a single model for a binary outcome (in Task 11.) Be sure you've done this, clearly.
     There are 13 items listed in the [linear regression model list](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project1#what-should-i-consider-doing-in-developing-linear-models-for-task-10) and you need to decide which 4-8 of these you actually need to show us.
    - There are 12 items listed in the [logistic regression model list](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project1#what-should-i-consider-doing-in-developing-logistic-models-for-task-11) and you need to decide which 4-8 of these you actually need to show us.
    - It's **not** a wise choice to use the Spearman rho-squared plot for anything other than identifying non-linear terms. Using it for variable selection, for instance, is not recommended.
    - It's not smart to show both best subsets and the lasso and stepwise regression for the same outcome, unless there's a reason you're going to evaluate models from each approach. See my comments on "spending" degrees of freedom below.
    - Your final model in Task 10 and your final model in Task 11 should be validated, somehow. You have several options for doing this validation and any of them are fine, but you should be doing a validation.
- A project receiving an "A" grade will **not** be longer, rather it will be better.
    - It will have more concentrated "useful" stuff throughout than projects receiving a B.
    - It will show evidence of careful decision-making about what to present in each Task.
    - In Task 12, it will include a thoughtful set of conclusions and reflections that address the process you used, the data you used and the models you developed.
    - Above all, the presentation will be clear and concise. You'll include everything we need to see, and nothing we don't, everything will be appropriately annotated to guide our reading, and our attention will be drawn to the most important material.

## On "Spending" Degrees of Freedom in Project 1

The number of degrees of freedom that you are "spending" to fit any particular model is related to the sample size of your data, and the number of coefficients you are fitting in that model.  Paying attention to how you are "spending" degrees of freedom is an important part of fitting any prediction model. If you include more regression coefficients in a model than you can reasonably support with the sample size you have, then you will run into all sorts of problems. In addition, if you fit a whole bunch of models, and compare each in terms of how well it fits to the outcome, then you will definitely run into meaningful problems in terms of the model not performing as well in new data as it appears to perform in your current data. 

The # of degrees of freedom that I want you to spend in Project 1 is small. The choices in fitting models for Project 1 boil down to two related issues:

1. Which predictors will we include in our model?
2. What sort of non-linear terms (and how many of them) will we include in our model?

### Two Distinct Paths I'll Encourage You to Consider

If you're having trouble deciding on the scope of your project, or dealing with the project getting out of control, encourage you to follow either of two paths in doing Project 1. (Focus on A or B, but not both.)

- Path A. If you have a large set of predictors to consider and want to use a statistical procedure to identify which variables should be included in your model, use methods like a kitchen sink approach, stepwise regression, the lasso, best subsets or some combination to identify several different candidate models and then compare their fit using cross-validation, OR
- Path B. If you are settled on which predictors you want to use, use the Spearman rho-squared plot to identify candidate variables for non-linear terms, and add 1-3 such non-linear terms to your model, perhaps comparing the results using cross-validation or through validation of regression summaries like R-square or the C statistic. 
    - If you're going to use A, then the Spearman rho-squared plot can be fit after you complete step A, to indicate what predictors might be worthy of looking for non-linearity if new data arrived, but I wouldn't fit any non-linear terms.
    - If you're going to use B, then I would take your set of predictors as settled and focus on non-linear terms.
    - It's your choice whether to use Path A or B, and you might use one Path in Task 10 and the other in Task 11.

#### For a Linear Regression (Task 10)

- Consider all of the models you are going to fit to your outcome in order to make your final decision. 
- Before you fit any of them, I would verify that your modeling process has not spent more degrees of freedom than you can afford to spend, by the 20:1 rule. 
    - That means that you should count up the number of degrees of freedom that will be used in each model that you fit to your outcome (so if you plan to use best subsets to produce eight different models, then you used all of the degrees of freedom used by each of those eight models or if you fit four different candidate models, each with 4 degrees of freedom used, that's 16.) Call that total number of degrees of freedom P. 
    - Then take your sample size (the number of complete, non-imputed values in your data set used to fit the models) and call that N. N/P should be at least 20, but it's ok to go as low as N/P > 15 if you are cross-validating. 
- With the small sample sizes I've forced on you, this will mean making some tough decisions. What may push you towards approach B above is that it's less costly in terms of degrees of freedom, because you don't need to count using the Spearman plot as using up degrees of freedom. 

#### For a Logistic Regression (Task 11)

For a **logistic** regression, on the other hand, the standards are even higher. There, N/P should really be greater than 100, but I will be OK if yours is as small as 50. This will push you to not consider more than 1-2 non-linear terms if you're following path B, and to fit a fairly small number of predictors (4-8 in most cases) if you're following path A.

### On Non-Linear Terms

As for what type of non-linear terms you should consider in Project 1, look at the Spearman rho-squared plot and identify the predictor with the largest Spearman rho-squared (at the top of the plot, furthest to the right.) 

- If the (apparently strongest - furthest to the right) predictor is quantitative, you should be thinking first about a restricted cubic spline with 4 knots, maybe 5 if it won't be a problem for your sample size. 
- If the largest rho-square is associated with a binary or a multi-categorical predictor, create an interaction term with the second-largest rho-squared predictor. 

If you still have degrees of freedom you're willing to spend after this, proceed down to the second largest predictor in terms of rho-squared, and proceed similarly to the third largest after that, if you like, but I would not include more than 3 non-linear terms in Project 1, no matter how large your sample is. Don't fit non-linear terms to predictors outside of the top 2-3 performers in the Spearman plot for Project 1. 

## Comments in response to Student Questions about Project 1

1. **Dealing with Missing Data**. In the instructions, I encourage you to consider both "complete case" and "multiple imputation" approaches. I think that's right, although you are welcome to consider "simple imputation" instead of "complete case" if you would prefer. But I would like to see multiple imputation results, at least at the end, once you've selected a model for the data. You should clearly state what the impact of multiple imputation is on the inferences you make from your final model(s), if you had missing data.

2. **Fitting an Interaction Term to a Variable Which Includes a Spline**. Suppose you are using a Spearman rho-squared plot to help specify non-linear terms for a model, and variables `a` (quantitative) and `b` (categorical) are at the top of your list. You may be tempted to fit, for example, both a 5-knot restricted cubic spline in `a`, and the interaction of `a` and `b`. To do so, you should fit a model like this: `outcome ~ rcs(a, 5) + b + a %ia% b + ...` so that you are creating the interaction of the linear effect of `a` with `b`. 
    - **Don't** use `outcome ~ rcs(a, 5) * b + ...` which will instead create the interaction of the whole spline in `a` with `b`, which will be essentially uninterpretable outside of a graph, and isn't what we want in Project 1.

3. **Fitting Categorical Variables in rms, lm or glm** I encourage you to code binary variables as numeric 1/0 variables, with the name indicating what 1 means. I encourage you to code multi-categorical variables as factors with names for the levels. I do this because I think it will be the least confusing approach in modeling.

4. **Best Subsets while Forcing in a Variable**. When fitting a **best subsets** approach to a linear regression, suppose you want to force in variable "a" and then let the software decide about variables b, c, d, e and f. So you are asking best subsets to evaluate models that contain an intercept and variable "a" and then 1-5 of the remaining variables b-f. So the k values for such a model would be 3-7. Note that when you force a variable to be in, the output table listing which variables are forced in and forced out may be incorrect (it's a problem in leaps) but the actual models fit should be correct.

5. **Best Subsets for Generalized Linear Models**. It is possible to use R to approach an "all subsets" result via exhaustive search for a logistic regression model, using, for instance, the `bestglm` or `glmulti` packages. There are problems with these approaches, and so I would not recommend you do this for Project 1, but I will try to pull together some materials about this for later in the term. If you want to select predictors in your logistic regression model, I suggest you focus on stepwise methods for Project 1.

6. **Apparently Singular Matrix error in R**. This can occur when running `anova` on an `rms`-generated model, like `ols` or `lrm`. It usually happens when the default tolerance level for flagging an invertible matrix is too low. You can usually fix this with `anova(modelname, tol = 1e-13)`. If that isn't effective, be sure that you don't have any interaction terms with constant values of the outcome. If that doesn't seem to be the problem, try centering and rescaling your predictors before running the `lrm` or `ols` model.

7. **Interpreting Effect Sizes Correctly**. I've written up a note that we'll discuss in class. It will help us discuss the various types of effect estimates we can generate with `lm`, `ols`, `glm` and `lrm` model fits, and it makes use of the `small.csv` data set posted [above](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class16).
    - I've made the note available in both an [HTML preview](http://htmlpreview.github.io/?https://github.com/THOMASELOVE/432-2018/blob/master/slides/class16/class16note.html) and in [R Markdown](https://raw.githubusercontent.com/THOMASELOVE/432-2018/master/slides/class16/class16note.Rmd).
