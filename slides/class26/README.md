# 432 Class 26: 2018-04-19

## Key Materials

- The posted [slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class26) now only cover what I actually discussed. The slides for Class 27 pick up the rest.
- The [audio files](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class26) are now posted.

Today's class included:

1. data visualization ideas from [your work on HW 6](https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw6/NICEVIZ.md) and from [flowingdata.com](http://flowingdata.com/)
2. some clarifying comments on spending degrees of freedom, the Spearman rho-squared plot, and how regression models should be built
3. some specific issues related to logistic regression model selection and classification assessment

There is no Minute Paper today.

## Announcements at the start of class

1. The Schedule of Project 2 Presentations (and some logistical information) [is now available](https://github.com/THOMASELOVE/432-2018/blob/master/projects/project2/PRESENTATIONS.md). Please take a look now, to verify that the time you're scheduled for works.

2. I posted a hint for question 3 on [Homework 7](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw7). 
    - When you have a time-to-event outcome, you just use the survival time, and not the whole survival object (i.e. you ignore the censoring) in building a Spearman rho-squared plot.

3. Speaking of using Spearman rho-squared plots, just being sure this is clear...
    - When you're fitting non-linear terms (based on a Spearman rho-squared plot) if the variable you're considering adding non-linearity to is quantitative, you might consider a restricted cubic spline, a polynomial function, or an interaction between the quantitative variable and a nearby categorical one.
    - But if the variable is categorical, your only option is an interaction term. Splines and polynomials make no sense with categorical variables.

4. The version of Chapters 22 and 23 where all images appear is [available in HTML here](https://htmlpreview.github.io/?https://github.com/THOMASELOVE/432-2018/blob/master/slides/class24/chapters_22_and_23_draft.html), and also [in R Markdown](https://raw.githubusercontent.com/THOMASELOVE/432-2018/master/slides/class24/chapters_22_and_23_draft.Rmd).

5. Those of you interested in Python probably already know that [PyCon 2018 is in Cleveland](https://us.pycon.org/2018/about/) May 9-17. Registration is $125 for students.
  
## Making Project 2 A Little Easier 

**This note is now section 6.19 of the [Project 2 Instructions](https://htmlpreview.github.io/?https://github.com/THOMASELOVE/432-2018/blob/master/projects/project2/project2-instructions-432-2018.html)**

While you can fit a model including up to the complete set of predictors I approved in your proposal, I strongly recommend you restrain yourself to **no more than 8 actual predictors** in a final model regardless of your sample size. Anything more than that will be difficult to interpret at best.

- If your number of main effects (predictors) that you want to include in your final model exceeds the number of degrees of freedom specified below, then don't add any non-linear terms.
- If you do decide to include non-linear terms as determined based on a Spearman rho-squared plot, then adhere closely to the maximum degrees of freedom specified in the table below. These df limits include the intercept term(s).

1. If you are fitting a regression to a **quantitative or count** outcome, let *n* = sample size. For this count and all of the counts here, do not include any data points where the outcome is missing.
2. If you are fitting a regression to a **categorical** outcome, let *n* = # of observations in the category with the smallest sample size.
3. If you are fitting a regression to a **time-to-event** outcome, let *n* = # of observations where the event occurred (was not censored).

Value of *n* | 10-100 | 101-250 | 251-500 | 501-999 | 1000+
-----------: | -----: | ------: | ------: | ------: | --------:
Maximum *df* | 6 | 9 | 12 | 16 | 20

- **For project 2**, don't worry about penalizing yourself for "peeking" at the data by running automated selection procedures or scatterplot matrices. 
- If you are running either a linear regression or a (binary) logistic regression, you should run some sort of model validation, ideally one that generates estimated root mean squared prediction errors and mean absolute prediction errors comparing two or more models, but if not, at least validations of the summary statistics.

## Remaining Deliverables This Semester

The [Schedule](https://github.com/THOMASELOVE/432-2018/blob/master/SCHEDULE.md) page is always the final word, if you are confused.

1. [Homework 7](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw7) is due at 5 PM on **Tuesday 2018-04-24**. Submit to [Canvas](https://canvas.case.edu/).
2. [Quiz 2](https://github.com/THOMASELOVE/432-2018/tree/master/quizzes/quiz2) will go out after class on 2018-04-26, and is due at Noon on **Tuesday 2018-05-01**.
3. [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) Final Portfolio materials are due 3 hours prior to your Presentation to me. Submit to [Canvas](https://canvas.case.edu/).
4. [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) Presentations are on **2018-05-03**, **2018-05-07** and **2018-05-08**, and the [complete schedule is here](https://github.com/THOMASELOVE/432-2018/blob/master/projects/project2/PRESENTATIONS.md).
5. [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) Revisions are due at Noon on **Wednesday 2018-05-09**. Whether you'll need to revise will be determined at your presentation.

## Today's Data Visualizations

- While the rest of Homework 6 isn't yet graded, we have looked at Question 1, and identified a few of [your visualizations of the County Health Data that caught our eye](https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw6/NICEVIZ.md).
- We're touring some of the interesting work at [flowingdata.com](http://flowingdata.com/), specifically Nathan's thoughts on
    - [Visualizing Differences](https://flowingdata.com/2018/04/17/visualizing-differences/)
        - [Relationships: The First Time...](http://flowingdata.com/2017/02/23/the-first-time/)
    - [Visualizing Outliers](https://flowingdata.com/2018/03/07/visualizing-outliers/)
        - [Why People Visit The Emergency Room](http://flowingdata.com/2016/02/09/why-people-visit-the-emergency-room/)

## Project Presentation Order and Time Slot, Sorted by Student's Last Name

The complete presentation order [is available here](https://github.com/THOMASELOVE/432-2018/blob/master/projects/project2/PRESENTATIONS.md), arranged by time slot. Below, I rearrange, by student last name.

Student     |     Presentation Order and Time Slot
-------------: | :---------------------------------------
Khaled Alayed |	32: Tue 05-08 12:20 PM to 12:40 PM
Zainab Albar |	21: Mon 05-07 1:30 PM to 1:50 PM
Haimeng Bai	| 22: Mon 05-07 1:55 PM to 2:15 PM
Laura Baldassari |	01: Tue 05-01 3:00 PM to 3:20 PM
Shufen Cao	| 37: Tue 05-08 2:35 PM to 2:55 PM
Estee Cramer | 	34: Tue 05-08 1:10 PM to 1:30 PM
Laura Cremer |	 27: Mon 05-07 4:10 PM to 4:30 PM
Vaishali Deo |	18: Mon 05-07 11:20 AM to 11:40 AM
Abhishek Deshpande |	28: Mon 05-07 4:35 PM to 4:55 PM
Katherine Dobbs |	03: Thu 05-03 9:20 AM to 9:40 AM
Gwendolyn Donley |	05: Thu 05-03 10:20 AM to 10:40 AM
Caroline El Sanadi |	02: Thu 05-03 8:55 AM to 9:15 AM
Jenny Feng	| 36: Tue 05-08 2:10 PM to 2:30 PM
Dongze He	| 04: Thu 05-03 9:45 AM to 10:05 AM
Ryan Honomichl	| 08: Thu 05-03 1:30 PM to 1:50 PM
Jiajian Huang	| 26: Mon 05-07 3:45 PM to 4:05 PM
Maher Kazimi |	09: Thu 05-03 1:55 PM to 2:15 PM
Hyun Jo Kim	| 12: Thu 05-03 4:10 PM to 4:30 PM
Nikolas Krieger | 	11: Thu 05-03 2:45 PM to 3:05 PM
Carli Lehr	| 10: Thu 05-03 2:20 PM to 2:40 PM
Kedar Mahajan	| 20: Mon 05-07 12:10 PM to 12:30 PM
Roberto Martinez	| 15: Mon 05-07 9:55 AM to 10:15 AM
John McDonnell |	30: Tue 05-08 11:30 AM to 11:50 AM
Satyakam Mishra	| 23: Mon 05-07 2:20 PM to 2:40 PM
Elina Misicka	| 17: Mon 05-07 10:45 AM to 11:05 AM
Haeun Park	| 06: Thu 05-03 10:45 AM to 11:05 AM
Preeti Pathak	| 24: Mon 05-07 2:45 PM to 3:05 PM
Sarah Planchon Pope	| 01: Tue 05-01 3:00 PM to 3:20 PM
Gabrielle Rieth	| 29: Mon 05-07 5:00 PM to 5:20 PM
Kaylee Sarna |	25: Mon 05-07 3:20 PM to 3:40 PM
Andrew Shan	| 04: Thu 05-03 9:45 AM to 10:05 AM
Sandra Silva Camargo |	28: Mon 05-07 4:35 PM to 4:55 PM
Connor Swingle |	33: Tue 05-08 12:45 PM to 1:05 PM
Andrew Tang	| 14: Mon 05-07 9:30 AM to 9:50 AM
Vinh Trinh | 35: Tue 05-08 1:45 PM to 2:05 PM
Sneha Vakamudi |	16: Mon 05-07 10:20 AM to 10:40 AM
Frances Wang |	07: Thu 05-03 11:10 AM to 11:30 AM
Ruipeng Wei	| 31: Tue 05-08 11:55 AM to 12:15 PM
Peter Wilkinson |	19: Mon 05-07 11:45 AM to 12:05 PM
Xin Xin Yu |	36: Tue 05-08 2:10 PM to 2:30 PM
Bilal Zonjy	| 13: Thu 05-03 4:35 PM to 4:55 PM

