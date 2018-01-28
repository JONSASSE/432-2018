# 432 Homework 3 for Spring 2018

Submit your response via [canvas.case.edu](https://canvas.case.edu/) no later than **1 PM on Friday 2018-02-09**. Your response should include an R Markdown file and an HTML document that is the result of applying your R Markdown file. 

Start a separate R Project for Homework 3 as your first step, and place all of your work in that project's directory.

## Question 1. (20 points)

Consider the `hbp330` data used in Homeworks 1 and 2. In question 4 of HW2, you built a model for the prediction of body-mass index, considering the following 14 predictors: `practice`, `age`, `race`, `eth_hisp`, `sex`, `insurance`, `income`, `hsgrad`, `tobacco`, `depdiag`, `sbp`, `dbp`, `statin` and `bpmed`. Your task now is to fit a Spearman rho-squared plot to identify the candidate variables on which you might most reasonably try to address non-linearity in a model predicting body-mass index, now making use of as much of the data set that missing data allow. Show the plot, and provide a written explanation of your conclusions about it, and specify the variables that are most appealing for non-linear augmentations, all in complete sentences. Which variables are most appealing candidates to add non-linear evaluations to a linear fit to the complete set of 14 predictors, and why? 

Note that you do not need to perform any analyses of potential models here, simply build and interpret a single plot.

## Question 2. (80 points)

There are eight "tasks" within this question, and number 8 is the most important one. We suggest you read through all 8 tasks before getting started. 

1. Bring the `gapminder` data in by loading the `gapminder` package. Characterize the data. For instance, how many rows and variables are in the data frame? What do the rows describe? You might want to visit  [this link](http://simplystatistics.org/2014/06/13/what-i-do-when-i-get-a-new-data-set-as-told-through-tweets/) if you like, to get some ideas about what other people do when exposed to a new data set. 

2. Pick at least one quantitative and one categorical (factor) variable to explore. What are the possible values? What is a typical value? What is the spread? What is the shape of the distribution, for quantitative variables. What are the levels, for factors? Tailor your results to the variables you have selected.

3. Build a plot of a quantitative variable, and another plot of a quantitative and a categorical variable, for one or more subsets of the data that interest you. 
    + These should be attractive, well-labeled plots using `ggplot2` of variables you chose to characterize numerically. 
    + Use `filter()`, `select()` and `%>%` (and perhaps other `dplyr` functions) to create a data subset or two that you want to plot. 
    + It's fine to filter down to a small handful of countries or dates, for example. 
    + Explore more than one plot type, and try to use more than one `geom` in your work.

4. Now, make a scatterplot which shows the relationship between two quantitative variables, either for a clearly specified subset of interest, or for the data as a whole. Include a regression line in the plot. Make an active choice as to which variable should be the predictor and which the outcome.

5. Specify the regression equation fitted for Task 4, and evaluate it using summary statistics like R^2^ or the residual standard deviation, as well as through assessments of the direction and size of the coefficient estimates.

6. Now, augment your scatterplot from Task 4 by incorporating a categorical variable as well as a predictor. Show the new predictor in a useful way as part of the plot, and show the regression model incorporating the predictor as part of the plot.

7. Specify the regression equation from Task 6, and describe the nature of the relationship between the predictors, and their impact on your outcome of interest through useful summaries.

Note that Tasks 1-7 are for you. You should retain the useful pieces in your answer set, and try to resolve difficulties. Provide as much annotation for these Tasks in your Markdown file as you feel you need to explain the results well.

8. Now, report on your process. Write a brief essay (at least 100 words but probably not much more than 250) reflecting on what was hard/easy, problems you solved, helpful tutorials you read, etc. What things were hard, even though you saw them in class? What was easy (or sort of easy) even though we haven't done it in class?

### How Will Question 2's Many Parts Be Evaluated?

We'll steal from the great work of Jenny Bryan...

- Truly excellent work (receiving 75 or more points on Question 2) will include some creativity, with diverse `ggplot2` figures, an especially well-organized presentation, a Markdown file that runs properly, and use of `dplyr` tools that goes beyond `filter()` and `select()`. Really great stuff will teach us something new that we can incorporate in our own work. The process response (Task 8) will be both clear and insightful.
- Good work (receiving 68-74 points on Question 2) will have no obvious mistakes, and be pleasant to read, without heroic detective work required to evaluate the results. The process response will be clearly written and speak to the rest of the document.
- Poor work (receiving less than 60 points on Question 2) will include some troubling mistakes or omissions, like missing plots, or lack of subsetting via `filter()` or `select()`. It's hard to figure out what we're looking at, and we're confused about what you're trying to describe in your process response.
- Scores of 60-67 points on Question 2 (which will likely be VERY common) will indicate work that falls in between these "Good" and "Poor" labels, perhaps with some elements of each.

