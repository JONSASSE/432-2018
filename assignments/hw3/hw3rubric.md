# 432 Homework 3 Rubric

# Question 1 (20 points)

- Award less than 12 points if the student fails to generate an accurate Spearman rho-squared plot. A plot using either (a) all 330 observations, not accounting for missingness, or (b) the 325 cases after deleting missing values is appropriate. We'll also accept (c) a plot after simple imputation is used to fill in the missing 5 ethnicity and 2 race values.
- Award 12-14 points if the student generates an accurate Spearman rho-squared plot with an obviously incorrect interpretation of the plot.
    + 14 is the maximum score they should receive if their order of importance doesn't start with `sex`.
- Award 15-18 points if the student generates an accurate Spearman rho-squared plot with a flawed but mostly appropriate interpretation of the plot, with fewer points awarded if bigger mistakes are made.  
    + 18 is the score a student should receive if they don't specify that an interaction term is the way in which `sex` could be incorporated in a non-linear way but otherwise get everything right. 
    + 15 is the score a student should receive if they incorrectly state that a spline or polynomial term in `sex` would be appropriate.
- Award 20 points for a complete and correct response, which includes a statement that an interaction term between `sex` and another rational choice of variable, given the plot, would be sensible.

# Question 2 (80 points)

As mentioned, we'll steal from the great work of Jenny Bryan...

- Truly excellent work (receiving 75 or more points on Question 2) will include some creativity, with diverse `ggplot2` figures, an especially well-organized presentation, a Markdown file that runs properly, and use of `dplyr` tools that goes beyond `filter()` and `select()`. Really great stuff will teach us something new that we can incorporate in our own work. The process response (Task 8) will be both clear and insightful.
- Good work (receiving 68-74 points on Question 2) will have no obvious mistakes, and be pleasant to read, without heroic detective work required to evaluate the results. The process response will be clearly written and speak to the rest of the document.
- Poor work (receiving less than 60 points on Question 2) will include some troubling mistakes or omissions, like missing plots, or lack of subsetting via `filter()` or `select()`. It's hard to figure out what we're looking at, and we're confused about what you're trying to describe in your process response.
- Scores of 60-67 points on Question 2 (which will likely be VERY common) will indicate work that falls in between these "Good" and "Poor" labels, perhaps with some elements of each.

