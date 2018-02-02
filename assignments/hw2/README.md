# 432 Homework 2 for Spring 2018

## Links to Post-Deadline Materials will go live as they become available

- Answer Sketch: [Download R Markdown](https://raw.githubusercontent.com/THOMASELOVE/432-2018/master/assignments/hw2/hw2sketch.Rmd), or [View HTML result](http://htmlpreview.github.io/?https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw2/hw2sketch.html), or [Download or View PDF result](https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw2/hw2sketch.pdf)
- Grading Rubric and Grades coming as soon as they are available.

# The Assignment

Submit your response via [canvas.case.edu](https://canvas.case.edu/) no later than **1 PM on Friday 2018-02-02**. Your response should include an R Markdown file and an HTML document that is the result of applying your R Markdown file. 

Start a separate R Project for Homework 2, as your first step, and place all of your work in that project's directory.

## Question 1. (30 points)

Consider the `hbp330` data used in Homework 1. Fit and interpret an ANOVA model to evaluate the effect of `race` on `income`. What conclusions can you draw? In developing an answer, please decide whether collapsing the `race` factor into a smaller number of levels would be sensible in this case. You'll also want to assess the role of missingness in this work, and consider removing the cases with missing values (or imputing them with simple imputation) if they include only a small fraction of the total sample. Be sure to provide a written explanation of your findings, in complete sentences.

## Question 2. (20 points)

Now fit a two-factor ANOVA model to evaluate the effects of `race` (either collapsed or uncollapsed, as you decide) and `sex` on `income`. What can you conclude? Be sure to provide a written explanation of your findings, in complete sentences.

## Question 3. (20 points)

Now attempt to fit a two-factor ANOVA model to evaluate the effect of `race` and `insurance` on `income`. A problem should occur when you fit this `race` and `insurance` model, that doesn't happen, for instance, when you evaluate the effects of both `race` and `sex` on `income`. So what happens when you fit the `race`-`insurance` model, exactly, and why does it happen?

- Here's a hint...
> R may well warn you about "singularities" in your output for Question 3, but we'd like a clearer answer than that from you. To obtain it, consider exploratory data analysis, specifically the value of counting things. In particular, ask yourself questions like "How many people fall into the levels of the product term I've created?" or "What if I build a table, say with race in the rows and insurance in the columns - how many people fall into each cell of that table?" as a way to figure out what the real problem is.

## Question 4. (30 points)

Again, consider the `hbp330` data used in Homework 1. Build your best model for the prediction of body-mass index, considering the following 14 predictors: `practice`, `age`, `race`, `eth_hisp`, `sex`, `insurance`, `income`, `hsgrad`, `tobacco`, `depdiag`, `sbp`, `dbp`, `statin` and `bpmed`. Use an appropriate best subsets procedure to aid in your search, and use a cross-validation strategy to assess and compare potential models.

- Feel free to omit the cases with missing values in the variables you are considering (these 14 predictors, plus the `bmi` outcome) before proceeding. This should not materially affect your sample size very much.
- Use the `nvmax = 7` command within your call to `regsubsets` to limit your investigation to models containing no more than seven of these candidate predictors.
- Do not transform any variables, and consider models with main effects only so that no product terms are used.
- A 5-fold cross-validation strategy would be very appropriate. Another reasonable choice would involve partitioning the data once (prior to fitting any models) into training and test samples, as we did in 431.

Be sure to provide a written explanation of your conclusions and specify the variables in your final model, in complete sentences.
