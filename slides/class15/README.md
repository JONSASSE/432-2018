# 432 Class 15: 2018-03-06

### Key Materials

- [The slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class15) will be posted as they become available.
- The [audio files](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class15) will be posted as they become available.

In today's class, we'll demonstrate five different robust linear regression modeling approaches, including bounded influence regression, penalized least squares and quantile regression. We'll also discuss Quiz 1.

## Announcements before class.

1. We will meet in Room E321-323 for the rest of the semester, **except for** April 5, when we'll meet in E301 again. Sorry about last Thursday. We're still not sure what happened.

2. I've posted the Homework 5 [grading rubric](https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw5/hw5rubric.md), as well as the Homework 5 [answer sketch in PDF](https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw5/hw5sketch.pdf), and [in R Markdown](https://raw.githubusercontent.com/THOMASELOVE/432-2018/master/assignments/hw5/hw5sketch.Rmd) and in an [HTML file you can preview](http://htmlpreview.github.io/?https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw5/hw5sketch.html). We'll get the grades to you as soon as possible.
    - The original sketch imputed using all other variables, but the revised sketch adheres to the recommendation within the assignment that you only use two specific variables to impute. It has no meaningful effect on conclusions, and how you did the imputation is not part of the grading rubric.

3. You may be interested in this list of [50 `ggplot2` Visualizations (with R code)](http://r-statistics.co/Top50-Ggplot2-Visualizations-MasterList-R-Code.html) which also links to some more introductory materials. If you want to build a waffle chart, dumbbell chart, slope chart, show clusters, build maps, or many more things, this is a nice resource. Some of the tools it uses come from the `ggExtra` package.

4. On Learning SQL, Python, GitHub, etc.
    - If you are interested in getting a job as a data scientist, I don't think you can without a reasonable understanding of GitHub and R. But most people will also want to see that you have some ability to work with SQL, and some will want to know if you can code in Python. Time spent on learning those things could certainly be useful, but I am an expert only in R, personally.
    - That said, what I do know is that the appeal of these things is that you can dip your toes in the water without spending any money.
    - With regard to SQL, for instance, you might want to look at R Studio's [thoughts on data bases](https://db.rstudio.com/), and perhaps explore the dbplyr package. MySQL is available in [a free version](https://dev.mysql.com/downloads/mysql/), and [SQLite is an excellent option](https://www.sqlite.org/index.html) which is also free. The [RMariaDB package](https://github.com/r-dbi/RMariaDB) can help you read SQL files well.
    - With regard to GitHub, I am mostly familiar with Jenny Bryan's [Happy Git with R](http://happygitwithr.com/) as a starting place.
    - And with regard to Python, what I know mostly about it is that people I know who are more connected to engineering, or who are more connected to doing work with data coming from apps on the internet, find Python more helpful. Despite my fondness for Monty Python, I've never used Python to do anything meaningful.
