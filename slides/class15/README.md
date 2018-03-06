# 432 Class 15: 2018-03-06

### Key Materials

- [The slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class15) are now available.
- The [audio files](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class15) will be posted as they become available.

In today's class, we'll demonstrate five different robust linear regression modeling approaches, including bounded influence regression, penalized least squares and quantile regression. We'll also discuss Quiz 1.

## Announcements before class

1. We will meet in Room E321-323 for the rest of the semester, **except for** April 5, when we'll meet in E301 again. Sorry about last Thursday. We're still not sure what happened.

2. I've posted the Homework 5 [grading rubric](https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw5/hw5rubric.md), as well as the Homework 5 [answer sketch in PDF](https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw5/hw5sketch.pdf), and [in R Markdown](https://raw.githubusercontent.com/THOMASELOVE/432-2018/master/assignments/hw5/hw5sketch.Rmd) and in an [HTML file you can preview](http://htmlpreview.github.io/?https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw5/hw5sketch.html). We'll get the grades to you as soon as possible.
    - The original sketch imputed using all other variables, but the revised sketch adheres to the recommendation within the assignment that you only use two specific variables to impute. It has no meaningful effect on conclusions, and how you did the imputation is not part of the grading rubric.

3. On Learning SQL, Python, GitHub, etc.
    - If you are interested in getting a job as a data scientist, I don't think you can without a reasonable understanding of GitHub and R. But most people will also want to see that you have some ability to work with SQL, and some will want to know if you can code in Python. Time spent on learning those things could certainly be useful, but I am an expert only in R, personally. That said, what I do know is that the appeal of these things is that you can dip your toes in the water without spending any money.
    - With regard to SQL, for instance, you might want to look at R Studio's [thoughts on data bases](https://db.rstudio.com/), and perhaps explore the dbplyr package. MySQL is available in [a free version](https://dev.mysql.com/downloads/mysql/), and [SQLite is an excellent option](https://www.sqlite.org/index.html) which is also free. The [RMariaDB package](https://github.com/r-dbi/RMariaDB) can help you read SQL files well.
    - With regard to GitHub, I am mostly familiar with Jenny Bryan's [Happy Git with R](http://happygitwithr.com/) as a starting place.
    - And with regard to [Python](https://www.python.org/), what I know mostly about it is that people I know who are more connected to engineering, or who are more connected to doing work with data coming from apps on the internet, find Python more helpful. Despite my fondness for Monty Python, I've never used Python to do anything meaningful.

4. Some project advice.
    - As [Brendan Molin](https://twitter.com/bmo_molin/status/969596193692180480?s=11) suggests, don't skimp on the exploratory data analysis.
    - The key to a mind-capturing project is **good visualization** of the data. Show us the data!
        - You may be interested in this list of [50 `ggplot2` Visualizations (with R code)](http://r-statistics.co/Top50-Ggplot2-Visualizations-MasterList-R-Code.html) which also links to some more introductory materials. If you want to build a waffle chart, dumbbell chart, slope chart, show clusters, build maps, or many more things, this is a nice resource. Some of the tools it uses come from the `ggExtra` package.
        - You may also like this [graphics companion from Trafford Data Lab](http://www.trafforddatalab.io/graphics_companion/index.html) which demonstrates a range of useful graphical forms via `ggplot2`.
    - From [Andrew Gelman](http://andrewgelman.com/2018/03/02/audition-fools-explore/): Two important attributes of a good scientist are (a) an openness to being surprised and (b) a willingness to do the hard work to collect data of high enough quality to be able to surprise you.

5. NOVA did a special on February 28 entitled "[Prediction by the Numbers](http://www.pbs.org/wgbh/nova/physics/prediction-numbers.html)". Some people I know were involved.
    - [Rethinking Science's Magic Number](http://www.pbs.org/wgbh/nova/next/body/rethinking-sciences-magic-number/) from Tiffany Dill at NOVA is definitely worth a read.

6. On other topics:
    - For Project 2, you will need some nice data to chew on. One possible source of interesting ideas is the [Data is Plural](https://tinyletter.com/data-is-plural) newsletter of useful/curious data sets.
    - The American Statistical Association has been [celebrating women in statistics and data science](https://www.youtube.com/watch?v=y2udE5N4l_4). There are a lot of terrific [stories here](http://magazine.amstat.org/statisticians-in-history/wis/?utm_content=buffer43082&utm_medium=social&utm_source=twitter.com&utm_campaign=buffer). If you're not interested, then you're probably the target audience.
    - I know a pathetically tiny amount about statistical genomics. But even I know that a solution for working with tidy data in bioinformatics is likely to be useful to some people. Consider [this, from Stuart Lee](https://sa-lee.github.io/plyranges/).
    
## Quiz 1 Results

- 41 people took the quiz. 
- The high score was 99/100, and the median was 85. 
- Grades have been emailed to you, and the [answer sketch is available online](https://github.com/THOMASELOVE/432-2018/tree/master/quizzes/quiz1).

If you have questions about the Quiz or your grade on the Quiz, please email 431-help or Dr. Love.

## Minute Paper after Quiz 1

### How long (in HOURS) did it take you to do Quiz 1?

Here's a little stem-and-leaf plot through the first 38 responses. (n = 38, mean = 6.3, sd = 2.7, median = 5.25)

```
03 | 0057
04 | 00000 00
05 | 00000 00057
06 | 0000
07 | 000
08 | 000
09 |
10 | 0000
11 | 0
12 | 0
13 |
14 |
15 | 0
```

### What was the most difficult question on the Quiz, for you?

Question | Votes | % of Available Points Awarded
---: | ---: | --------------:
Q21 | 13    | a 90%, b 88%, c 85%, d **63%**, e 66%
Q24 | 12.33 | a 76%, b 68%, c 73%, d 66%
Q19 | 7.33  | **39%**
Q01 | 1     | 90%
Q22 | 1     | 98%
Q25 | 1     | 88%
Q28 | 1     | **54%**
Q23 | 0.83  | **22%**
Q18 | 0.5   | 85%
Q15 | 0     | **59%**
Q29 | 0     | **63%**

## Project 1 Groups for Discussion in Class on Thursday

Group 1 has 5 members, the rest have 4 each.

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

You need to submit your project as it currently stands to Canvas for review by your colleagues in your group on Thursday. Submit your work before class begins, please.
