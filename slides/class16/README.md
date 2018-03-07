# 432 Class 16: 2018-03-08

### Key Materials

- [The slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class16) will appear as soon as they are available.
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
4. Make sure everyone in the group can see the current work of everyone else in the group on Canvas by the end of class today. This may require some intervention by Dr. Love. We'll see.
5. Over the break, you'll be finishing up your analyses, and so forth. Submit a revised version of your work on Canvas before our next class, on Tuesday 2018-03-20. At that class, you and your group will have time to discuss and address residual concerns, before the project due date (Friday 2018-03-23 at 1 pm).

## Announcements before class

1. We will meet in Room E321-323 for the rest of the semester, **except for** April 5, when we'll meet in E301 again. 

2. I updated some of the Python advice in the [Class 15 README](https://github.com/THOMASELOVE/432-2018/edit/master/slides/class15/README.md). Thanks to several people for getting me some information there. I also fixed the spelling of Mississippi in the [Class 15 Slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class15).

3. Remember that we do not have class next week. Enjoy the break. Our next class is Tuesday 2018-03-20. 
    - The next major deliverable is your Project 1 final portfolio, which is due at 1 PM on Friday 2018-03-23.

4. Assignment 8 has been eliminated. Assignment 6 is now due on April 6, and Assignment 7 is now due on April 13. The [schedule](https://github.com/THOMASELOVE/432-2018/blob/master/SCHEDULE.md) now reflects these changes.

5. Quiz 2 has been moved. It will now be available to you on April 20 and is due on April 23 at noon. The [schedule](https://github.com/THOMASELOVE/432-2018/blob/master/SCHEDULE.md) now reflects this.

6. There is a Minute Paper to complete after today's class. Please do so by the end of the day on Friday 2018-03-09. Thank you.

## Project 1 Tips

1. I have provided lists of potential analyses for your Project 1. But you should be **choosing wisely** from that list to produce a curated and appropriate final set of analyses in Task 10 and Task 11, not demonstrating your ability to do all of those things.
    - You need to settle on a single model for a quantitative outcome (in Task 10) and a single model for a binary outcome (in Task 11.) Be sure you've done this, clearly.
     There are 13 items listed in the [linear regression model list](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project1#what-should-i-consider-doing-in-developing-linear-models-for-task-10) and you need to decide which 4-8 of these you actually need to show us.
    - There are 12 items listed in the [logistic regression model list](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project1#what-should-i-consider-doing-in-developing-logistic-models-for-task-11) and you need to decide which 4-8 of these you actually need to show us.
    - It's **not** a wise choice to use the Spearman rho-squared plot for anything other than identifying non-linear terms. Using it for variable selection, for instance, is not recommended.
    - It's not smart to show both best subsets and the lasso and stepwise regression for the same outcome, unless there's a reason you're going to evaluate models from each approach.
    - A project receiving an "A" grade will **not** be longer, rather it will be better.
        - It will have more concentrated "useful" stuff throughout.
        - It will show evidence of careful decision-making about what to present in each Task.
        - In Task 12, it will include a thoughtful set of conclusions and reflections that address the process you used, the data you used and the models you developed.
        - Above all, the presentation will be clear and concise. You'll include everything we need to see, and nothing we don't, everything will be appropriately annotated to guide our reading, and our attention will be drawn to the most important material.

2. **Best Subsets while Forcing in a Variable**. When fitting a **best subsets** approach to a linear regression, suppose you want to force in variable "a" and then let the software decide about variables b, c, d, e and f. So you are asking best subsets to evaluate models that contain an intercept and variable "a" and then 1-5 of the remaining variables b-f. So the k values for such a model would be 3-7. Note that when you force a variable to be in, the output table listing which variables are forced in and forced out may be incorrect (it's a problem in leaps) but the actual models fit should be correct.

3. **Best Subsets for Generalized Linear Models**. It is possible to use R to approach an "all subsets" result via exhaustive search for a logistic regression model, using, for instance, the `bestglm` or `glmulti` packages. There are problems with these approaches, and so I would not recommend you do this for Project 1, but I will try to pull together some materials about this for later in the term. If you want to select predictors in your logistic regression model, I suggest you focus on stepwise methods for Project 1.

4. **Fitting an Interaction Term to a Variable Which Includes a Spline**. Suppose you are using a Spearman rho-squared plot to help specify non-linear terms for a model, and variables `a` (quantitative) and `b` (categorical) are at the top of your list. You may be tempted to fit, for example, both a 5-knot restricted cubic spline in `a`, and the interaction of `a` and `b`. To do so, you should fit a model like this: `outcome ~ rcs(a, 5) + b + a %ia% b + ...` so that you are creating the interaction of the linear effect of `a` with `b`. 
    - **Don't** use `outcome ~ rcs(a, 5) * b + ...` which will instead create the interaction of the whole spline in `a` with `b`, which will be essentially uninterpretable outside of a graph, and isn't what we want in Project 1.

5. **Dealing with Missing Data**. In the instructions, I encourage you to consider both "complete case" and "multiple imputation" approaches. I think that's right, although you are welcome to consider "simple imputation" instead of "complete case" if you would prefer. But I would like to see multiple imputation results, at least at the end, once you've selected a model for the data. You should clearly state what the impact of multiple imputation is on the inferences you make from your final model(s), if you had missing data.

6. **Apparently Singular Matrix error in R**. This can occur when running `anova` on an `rms`-generated model, like `ols` or `lrm`. It usually happens when the default tolerance level for flagging an invertible matrix is too low. You can usually fix this with `anova(modelname, tol = 1e-13)`. If that isn't effective, be sure that you don't have any interaction terms with constant values of the outcome. If that doesn't seem to be the problem, try centering and rescaling your predictors before running the `lrm` or `ols` model.

7. **Fitting Categorical Variables in rms, lm or glm** I encourage you to code binary variables as numeric 1/0 variables, with the name indicating what 1 means. I encourage you to code multi-categorical variables as factors with names for the levels. I do this because I think it will be the least confusing approach in modeling.
