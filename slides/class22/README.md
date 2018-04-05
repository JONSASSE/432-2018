# 432 Class 22: 2018-04-05

## Key Materials

- The [slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class22) are posted.
- The [audio files](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class22) will appear when available.
- We will meet in the auditorium (**E301**) today, down the hall from our usual E321-323.

Today's class will address a famous data visualization from history, and then we'll discuss building regression models for multi-categorical outcomes, using multinomial models. I also have another example available using proportional odds logistic regression at the end of today's slides.

An additional example of fitting a multinomial logistic model to predict a multi-categorical outcome is available in [Chapter 20 of the Course Notes](https://thomaselove.github.io/432-notes/). 

- The example in that Chapter is based on the work of Jeffrey S. Simonoff (2003) Analyzing Categorical Data, in his Chapter 10. Related data and R code are available at http://people.stern.nyu.edu/jsimonof/AnalCatData/Splus/. 
- The data set and analysis are based on the work of Peng RD and Hengartner NW (2002) Quantitative analysis of literary styles, *The American Statistician*, 56, 175-185.

## Announcements prior to class

1. A reproduction of Charles Joseph Minard's map of Napoleon's disastrous losses suffered during the Russian campaign of 1812 that we'll look at today can be found [at this link](https://en.wikipedia.org/wiki/Charles_Joseph_Minard#/media/File:Minard.png), and in the [Minard_large.png file](https://raw.githubusercontent.com/THOMASELOVE/432-2018/master/slides/class22/Minard_large.png) above.

2. A reminder: [This is a nice cheat sheet](http://www.cookbook-r.com/Manipulating_data/Converting_data_between_wide_and_long_format/) to help in converting data from wide to long format.

3. As part of [CWRU's National Public Health Week](http://thedaily.case.edu/national-public-health-week/) Speaker Series, I gave a presentation at noon today. Here's [my repository for that talk](https://github.com/THOMASELOVE/adventures).

4. This set of comments by Rafael Irizarry on the [Draft NIH Strategic Plan for Data Science](https://simplystatistics.org/2018/04/02/input-on-the-draft-nih-strategic-plan-for-data-science/) was illuminating for me.

5. The fastest-growing course in UC Berkeley’s history — Foundations of Data Science — [is being offered free online this spring](http://news.berkeley.edu/2018/03/29/berkeley-offers-its-fastest-growing-course-data-science-online-for-free/). The course teaches lots of useful stuff, all while coding in Python. [Very tempting](https://data.berkeley.edu/education/data-8x).

6. Tidy Tuesday is a [thing you might be interested in](https://github.com/rfordatascience/tidytuesday/blob/master/README.md).

7. On 2018-04-04 I corrected an error in the specification of the *p* value for the overdispersion test in our Class 19 slides, specifically the slides numbered 38-39. 
    - It now is: `cat("p value of overdispersion test: ", pchisq(sum(z^2), n-k, lower.tail=FALSE), "\n")`
    - Section 18.8.1 of [the Course Notes](https://thomaselove.github.io/432-notes/) has now been corrected on this point, too.
    
8. If you are having trouble installing the `countreg` package, first, make sure you've upgraded to **R 3.4.4**, and then [try the approach suggested on our PACKAGES page](https://github.com/THOMASELOVE/432-2018/blob/master/data-and-code/PACKAGES.MD). 
    - If that doesn't work, try [this workaround to put an old version of `countreg` on your machine](https://github.com/THOMASELOVE/432-2018/blob/master/data-and-code/installing_countreg_workaround.pdf). 
    - You'll know it worked if you can successfully generate a rootogram.
    
9. If you don't have data for Project 2 yet, you might look at https://data.europa.eu/. It certainly seems like it might be useful.

10. “This class is supported by [DataCamp](https://www.datacamp.com/), the most intuitive learning platform for data science. Learn R, Python and SQL the way you learn best through a combination of short expert videos and hands-on-the-keyboard exercises. Take over 100+ courses by expert instructors on topics such as importing data, data visualization or machine learning and learn faster through immediate and personalised feedback on every exercise.” **Check your email for an invitation** that will get you access to all of DataCamp until the end of September.

## There IS a minute paper after today's class.

- The [Minute Paper after Class 22](https://goo.gl/forms/uAn6IQcZxT2l6Hbr2) is now available, and is due at **10 AM Monday 2018-04-09**.

## Remaining Deliverables This Semester

The [Schedule](https://github.com/THOMASELOVE/432-2018/blob/master/SCHEDULE.md) page is always the final word, if you are confused.

- [Homework 6](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw6) is due at 1 PM on **Friday 2018-04-13**. Submit to [Canvas](https://canvas.case.edu/).
- The Minute Paper after Class 24 will become available 2018-04-12 and is due at **10 AM Monday 2018-04-16**.
- [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) Registration and Scheduling [Google Form](https://goo.gl/forms/Zfgnq5pyAAzAlmUm1) is due at 5 PM on **Tuesday 2018-04-17**.
    - You can see the status (and title) of proposals that have been reviewed and approved [by visiting this link](https://github.com/THOMASELOVE/432-2018/blob/master/projects/project2/APPROVED.md).
- [Homework 7](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw7) is due at 5 PM on **Tuesday 2018-04-24**. Submit to [Canvas](https://canvas.case.edu/).
- [Quiz 2](https://github.com/THOMASELOVE/432-2018/tree/master/quizzes/quiz2) will go out after class on 2018-04-26, and is due at Noon on **Tuesday 2018-05-01**.
- [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) Final Portfolio materials are due 3 hours prior to your Presentation to me. Submit to [Canvas](https://canvas.case.edu/).
- [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) Presentations are on **2018-05-03**, **2018-05-07** and **2018-05-08**, and will be scheduled by 2018-04-19.
- [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) Revisions are due at Noon on **Wednesday 2018-05-09**. Whether you'll need to revise will be determined at your presentation.

## Tweet of the Day

From Stephen Turner, [a nice tweet](https://twitter.com/strnr/status/787292116607234048) which contains some deep wisdom about how to deal with the task of building a professional visualization in our Homework 6.
