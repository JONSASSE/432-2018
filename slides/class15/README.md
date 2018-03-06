# 432 Class 15: 2018-03-06

### Key Materials

- [The slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class15) are now available.
- The [audio files](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class15) will be posted as they become available.

In today's class, we'll demonstrate five different robust linear regression modeling approaches, including bounded influence regression, penalized least squares and quantile regression. We'll also discuss Quiz 1.

## Project 1 Groups for Discussion in Class on Thursday

Group 1 has 5 members, the rest have 4 each. **As we're getting started, can you arrange to sit near the other members of your group today**, so you can make sure you know each others' names?

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

6. Training Opportunities
    - You may be interested in [Data Days CLE](http://datadayscle.strikingly.com/) April 5-6 downtown. "Data Days is an annual celebration of open data where participants engage, ideate, and learn around the use of data and technology from a civic lens."
    - The Cleveland Chapter of the American Statistical Association is holding its thirty second annual workshop, this year on "[Successful Data Mining in Practice](http://www.bio.ri.ccf.org/ASA/cspring.html)" taught by Dick De Veaux on April 13, 2018 from 8:30 AM to 4:30 PM. I'll be there, as Dick is a leader in this field and one of the best teachers of statistics alive. The price is $50 for full-time students, and $170 for ASA members and $200 for non-members if you register before March 19. From  the course description:
        - "Many of the standard techniques of data mining, including a review of modern model selection strategies for multiple regression such as the lasso, elastic net, etc. will be presented. In addition we'll cover classification and regression trees, neural networks, principal component regression, naive Bayes, bagging, and boosting. The course will be problem solving based, using real case studies from industry to illustrate which methods work well, when and why. We will emphasize problem formulation, the challenges of the data, and the communication back to decision makers in order to effect maximum impact in the organization. No prerequisities other than a knowledge of the basics of regression are assumed."
    - I encourage anyone who is interested to attend the Center for Health Care Research and Policy's weekly Health Services Research Seminars. The next two weeks should be especially interesting:
        - On Friday March 9 from 9 to 10:30 AM, Professor Adam Perzynski will discuss "What are We Going to do about the Social Determinants of Health? Challenges, Opportunities, Dead Ends and Solutions."
        - On Friday March 16 from 9 to 10:30 AM, Professor Thomas Love will discuss "Rethinking Statistical Significance"
        - Both talks are set at a level that will be of interest to graduate students in PQHS, and we encourage you to join us. 
        - PQHS 432 students are welcome at all HSR Seminars. The schedule can be found at chrp.org/events. Seminars are held in room R219, on the second floor of the Rammelkamp Research and Education Building at MetroHealth Medical Center, 2500 MetroHealth Drive, Cleveland OH 44109-1998.

7. On other topics:
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

```
03 | 0057
04 | 00000 000
05 | 00000 00005 7
06 | 0000
07 | 0000
08 | 000
09 |
10 | 0000
11 | 0
12 | 0
13 |
14 |
15 | 0
```

- Note that `03 | 5` means 3.5 hours, and `03 | 7` means 3.75 hours.
- *n* = 41, mean = 6.2, sd = 2.7, median = 5

### What was the most difficult question on the Quiz, for you?

Question | Votes | % of Available Points Awarded
---: | ---: | --------------:
Q21 | 14.33 | a 90%, b 88%, c 85%, d **63%**, e 66%
Q24 | 12.33 | a 76%, b 68%, c 73%, d 66%
Q19 | 8.67  | **39%**
Q23 | 1.17  | **22%**
Q01 | 1     | 90%
Q22 | 1     | 98%
Q25 | 1     | 88%
Q28 | 1     | **54%**
Q18 | 0.5   | 85%
Q15 | 0     | **59%**
Q29 | 0     | **63%**

I'll discuss Questions 15, 19, 21, 23, 24, 28 and 29 in class today.

