# 432 Homework 2 for Spring 2018

Submit your response via [canvas.case.edu](https://canvas.case.edu/) no later than **1 PM on Friday 2018-02-02**. Your response should include an R Markdown file and an HTML document that is the result of applying your R Markdown file. 

Start a separate R Project for Homework 2, as your first step, and place all of your work in that project's directory.

## Question 1. (30 points)

Consider the `hbp330` data used in Homework 1. Fit and interpret an ANOVA model to evaluate the effect of `race` on `income`. What conclusions can you draw? In developing an answer, please decide whether collapsing the `race` factor into a smaller number of levels would be sensible in this case. You'll also want to assess the role of missingness in this work, and consider removing the cases with missing values if they include only a small fraction of the total sample. Be sure to provide a written explanation of your findings, in complete sentences.

## Question 2. (20 points)

Now fit a two-factor ANOVA model to evaluate the effects of `race` (either collapsed or uncollapsed, as you decide) and `sex` on `income`. What can you conclude? Be sure to provide a written explanation of your findings, in complete sentences.

## Question 3. (20 points)

Now attempt to fit a two-factor ANOVA model to evaluate the effect of `race` and `insurance` on `income`. A problem should occur when you fit this `race` and `insurance` model, that doesn't happen, for instance, when you evaluate the effects of both `race` and `sex` on `income`. So what happens when you fit the `race`-`insurance` model, exactly, and why does it happen?

## Question 4. (30 points)

Again, consider the `hbp330` data used in Homework 1. Build your best model for the prediction of body-mass index, considering the following 14 predictors: `practice`, `age`, `race`, `eth_hisp`, `sex`, `insurance`, `income`, `hsgrad`, `tobacco`, `depdiag`, `sbp`, `dbp`, `statin` and `bpmed`. Limit your investigation to models containing no more than seven of these candidate predictors, and do not transform any variables. 

Use an appropriate best subsets procedure to aid in your search, and use a cross-validation strategy (like partitioning the data into training and test samples prior to fitting models) to assess and compare potential models. Be sure to provide a written explanation of your conclusions and specify the variables in your final model, in complete sentences.
