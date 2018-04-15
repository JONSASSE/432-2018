# 432 Class 25: 2018-04-17

## Key Materials

- The [slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class25) will be posted as soon as they are available.
- The [audio files](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class25) will be posted as soon as they are available.

Today's class will conclude our discussion of Cox proportional hazards regression models. As a reminder, Chapters 22 and 23 of the [Course Notes](https://thomaselove.github.io/432-notes/) describe the main ideas behind Cox proportional hazards regression models incorporating covariates that do not change over time.

Links to the data visualization we'll discuss today:

- Noah Veltman's [NFL Player Size](https://noahveltman.com/nflplayers/) visualization.
- If you want to learn Shiny, the best place to start is [this tutorial page at R Studio](http://shiny.rstudio.com/tutorial/), which guides you to lots of great resources.
- A few basic Shiny apps to learn from:
    - [Old Faithful](https://shiny.rstudio.com/gallery/faithful.html)
    - [K-Means Clustering in the Iris data](https://shiny.rstudio.com/gallery/kmeans-example.html)
    - [Inline output as part of a Markdown-based Notebook](https://shiny.rstudio.com/gallery/inline-output.html)
- I expect that some people in this class will be really interested in [this ICGC pancreatic cancer (ductal adenocarcinoma) genome browser, created using Shiny](https://shiny.rstudio.com/gallery/genome-browser.html). 

## Announcements at the start of class

1. The Homework 6 Answer Sketch and Grading Rubric is now posted as an [HTML document you can view](http://htmlpreview.github.io/?https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw6/hw6sketch.html), and as an [R Markdown file you can download](https://raw.githubusercontent.com/THOMASELOVE/432-2018/master/assignments/hw6/hw6sketch.Rmd).

2. Remember that a draft version of both Chapters 22 and 23 where all images appear is available. See [the HTML here](https://htmlpreview.github.io/?https://github.com/THOMASELOVE/432-2018/blob/master/slides/class24/chapters_22_and_23_draft.html), and [the R Markdown here](https://raw.githubusercontent.com/THOMASELOVE/432-2018/master/slides/class24/chapters_22_and_23_draft.Rmd).

3. **Project 2 Tip**: Most students should wind up using between 4 and 10 R packages in the project. 
    - Everyone, I think, will need to load `skimr`, `broom`, `rms` and the `tidyverse`. 
    - It's OK to load more, but **don't** load something else unless you actually need it. Don't just load everything we've used this semester. 
    - Remember that `tidyverse` loads `forcats`, so you shouldn't load `forcats` if you're loading `tidyverse`. Similarly, `rms` loads `Hmisc`, so you don't need to load that separately. 
    - There's really no reason for you to source in `Love-boost.R`, unless you actually need it to do something specific.

4. If you are interested in reading 32 pages of PDF notes I wrote in Spring 2016 on **longitudinal data analysis**, specifically about spaghetti plots, response feature analysis, repeated measures ANOVA, and the basics of generalized estimating equations (GEE), well, [here it is](https://github.com/THOMASELOVE/432-2018/blob/master/texts/432_notes_from_2016_on_longitudinal_data.pdf). No warranties, but you're welcome to it.

## Minute Paper after Class 24 (first 24 responses, several questions not yet edited)

### Please describe your current Project 2 progress 

Count (%) | Response
----------: | --------------------------------------------------------------------
8 (33) | I have submitted a proposal and it's been approved and I've starting working with the data to produce the portfolio.
5 (21) | I have submitted a proposal and it's been approved but that's it.  
0 (-) | I have submitted a proposal and it's not yet approved.
10 (42) | I am working on my proposal, and am nearing the point where I can submit it.
1 (4) | I haven't really gotten rolling on the proposal yet.

### What is the most important thing you've learned recently from the course?

- Survival Analysis / Cox Proportional Hazards Models / Kaplan-Meier Estimation for time-to-event responses
- Proportional odds logistic regression for ordered multi-categorical responses
- Multinomial logistic regression for unordered multi-categorical responses
- Zero inflated Poisson Regression / Poisson Regression and other methods for count outcomes
- Data Visualization

### Do you have any advice for prospective students in next year's 431-432 sequence?

- Pay attention to interpretations of models.
- Google and Dr. Love's notes/powerpoints are your best friends!  Never hesitate to google something that is sending you an error because chances are someone has asked about it (and risked getting flamed at) on StackOverflow.  Good luck-learn lots and have fun! 
- Definitely take the Intro to R course. I had not coded anything (beyond simple basic in 9th grade--1982-83) before I took that class last summer. Without it, I think 431 would have killed me. Understanding a bit about what the code is trying to do was INCREDIBLY helpful! 
- Taking 406 in the summer prior to starting the course so that you are familiar with R is extremely helpful. 
- I would maybe provide students some of the "required reading" ahead of time--they may not do it, but I found the R4DS readings to be really helpful and they probably would provide some orientation at the beginning of the class.
- start assignments and project early. 
- Tell them it couldn't hurt if they learned the basics of base R (how it stores data, the different kinds of objects, etc.) and maybe Rmarkdown as well. Obviously, many wouldn't know where to start, but some eager beavers may benefit from this.
- Utilize office hours and 431 help as much as you can!
- I would recommend they do the easy (and free) "Introduction to R" at datacamp.  Learning how to use R is the hardest part of the course, and arguably the most important.  
- I would advise them to do some basic R tutorials before the course starts. I hadn't had any experience with R and it made the first few assignments much more difficult, purely because of the software basics I didn't understand.
- My advice would be not to procrastinate on the projects (especially for 431, since things were very busy towards the end of the semester). It was very advantageous to have them done earlier than the due date to help with time management for other things that were due (homework, quiz, etc). 
- It's really an amazing course, thanks so much
- They are very useful coursers and they will spend you some time to complete. If you are busy with other things, you may reschedule your plan. 
- read the notes more
- The course is very labor intensive and you learn a lot. You must go through the notes thoroughly before and after each class. It helps. 
- let them know that it's a time consuming series- probably more than the rest of the other classes combined (while taking 2-3 other classes, 1 being a seminar)...but that it's well worth the time and effort 
- I would recommend looking at resources online about how to simply tidy data. So much time and energy could have been saved by knowing - more basic data tidying concepts for me.
- Taking 480 helps getting the basic mathematical background for the applications in 431 and 432 (mostly 431)
- To start working on the assignments with enough time ahead. Use all the resources available to clarify doubs even if you think they are silly, getting familiar with R is challenging.
- Starting to learn R before they get into the course would be very helpful. Particularly base R coding, not just using particular - packages. 
- Just to follow you exactly, specially readme files, then notes and lectures.
- The introduction to R programming course offered in the summer term was very helpful in preparing for 431/432. I think I would have really struggled if I hadn't taken it. 
- Read the notes carefully. 

### What question(s) about the course are uppermost in your mind now?

1. How do we build the fancy moving plots we saw in class like the one from *Huffington Post*? Is it possible in R shiny or are the graphics too fancy for it?
2. Can visualizations that have moving graphics be shown in html documents such as the income mobility example from class 23?
3. Will we get some practice using shiny?
    - If you want to learn Shiny, the best place to start is [this tutorial page at R Studio](http://shiny.rstudio.com/tutorial/), which guides you to lots of great resources.
    - Another tool that might be of interest to you is [flexdashboard](https://rmarkdown.rstudio.com/flexdashboard/) which lets you build interactive dashboards with help from R Markdown.
4. I am planning to use NHANES data for project 2. I will analyze a subpopulation (specific age range, had both interview and exam performed, and had a specific lab test performed). Do I need to incorporate sample weights into my analysis? If so, is there a good example/tutorial that you know of for doing this in R?
    - For project 2, the answer is no, you don't have to include sample weights, and I would recommend that you not do this as a first pass, but focus instead on topics we've covered more thoroughly. 
    - Now, you may still want to include the weights at some point. Incorporating survey weights in a linear or logistic regression model depends on the kind of weights available - you may just be doing a weighted linear regression or weighted logistic regression, and lm, glm, ols and lrm all can take weights, although they do so in slightly different ways. 
    - But what people usually do instead is use the survey package, and some details on this are available at https://stats.idre.ucla.edu/r/faq/how-can-i-do-regression-estimation-with-survey-data/ - this doesn't play so well with the rms packages, but can be used with lm and glm approaches in a pretty straightforward way. 
    - The gold mine in this area (if there is one) appears to be http://asdfree.com/ - if you go there, you'll see an obsessively crafted book called **Analyze Survey Data for Free** edited by Anthony Joseph Damico. In there, you'll find, among other things, detailed instructions on using survey data from NHANES. I'm not sure how complete it is, but there's a lot of stuff available.
5. How will our final projects be weighted in comparison to the rest of our assignments?
    - [The syllabus](https://thomaselove.github.io/432-syllabus/deliverables-and-grading.html#grading) is your friend here.
6. Which functions allow the creation of nomograms, etc. I know some play well and others do not...
    - Nomograms are built with the `rms` package, and work with models fit using `ols`, `lrm`, and `cph` that we've studied.


- I would still like a little more clarity on when it is justified to peek at the relationship between a predictor and outcome before fitting a model, two by two tables, scatterplot matrices, other graphical exploration?
- How should I proceed if my covariates turn out to be more significant than my main predictor in my model? Should I then retain the main predictor or drop it from the final model?
- Just mildly curious as to whether or not we're going to end up having those meetings with other students during class time or not.
- how to tidy up real world data and make it survival analysis-friendly
- What do we do if PH assumptions are not met for survival analysis? 
- In censoring, are there specific tests that can be done to compare the censored sample to the rest of the sample in the study. 

## Remaining Deliverables This Semester

The [Schedule](https://github.com/THOMASELOVE/432-2018/blob/master/SCHEDULE.md) page is always the final word, if you are confused.

- [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) Registration and Scheduling [Google Form](https://goo.gl/forms/Zfgnq5pyAAzAlmUm1) is due at 5 PM **today**. 
    - You can see the status (and title) of proposals that have been reviewed and approved [by visiting this link](https://github.com/THOMASELOVE/432-2018/blob/master/projects/project2/APPROVED.md).
- [Homework 7](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw7) is due at 5 PM on **Tuesday 2018-04-24**. Submit to [Canvas](https://canvas.case.edu/).
- [Quiz 2](https://github.com/THOMASELOVE/432-2018/tree/master/quizzes/quiz2) will go out after class on 2018-04-26, and is due at Noon on **Tuesday 2018-05-01**.
- [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) Final Portfolio materials are due 3 hours prior to your Presentation to me. Submit to [Canvas](https://canvas.case.edu/).
- [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) Presentations are on **2018-05-03**, **2018-05-07** and **2018-05-08**, and will be scheduled by 2018-04-19.
- [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) Revisions are due at Noon on **Wednesday 2018-05-09**. Whether you'll need to revise will be determined at your presentation.
