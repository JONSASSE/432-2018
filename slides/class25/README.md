# 432 Class 25: 2018-04-17

## Key Materials

- The [slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class25) will be posted as soon as they are available.
- The [audio files](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class25) will be posted as soon as they are available.

Today's class will conclude our discussion of Cox proportional hazards regression models. As a reminder, Chapters 22 and 23 of the [Course Notes](https://thomaselove.github.io/432-notes/) describe the main ideas behind Cox proportional hazards regression models incorporating covariates that do not change over time.

Links to the data visualization we'll discuss today are coming soon.

## Announcements at the start of class

1. The Homework 6 Answer Sketch and Grading Rubric is now posted as an [HTML document you can view](http://htmlpreview.github.io/?https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw6/hw6sketch.html), and as an [R Markdown file you can download](https://raw.githubusercontent.com/THOMASELOVE/432-2018/master/assignments/hw6/hw6sketch.Rmd).

2. Remember that a draft version of both Chapters 22 and 23 where all images appear is available. See [the HTML here](https://htmlpreview.github.io/?https://github.com/THOMASELOVE/432-2018/blob/master/slides/class24/chapters_22_and_23_draft.html), and [the R Markdown here](https://raw.githubusercontent.com/THOMASELOVE/432-2018/master/slides/class24/chapters_22_and_23_draft.Rmd).

3. **Project 2 Tip**: Most students should wind up using between 4 and 10 R packages in the project. 

- Everyone, I think, will need to load `skimr`, `broom`, `rms` and the `tidyverse`. 
- It's OK to load more, but **don't** load something else unless you actually need it. Don't just load everything we've used this semester. 
- Remember that `tidyverse` loads `forcats`, so you shouldn't load `forcats` if you're loading `tidyverse`. Similarly, `rms` loads `Hmisc`, so you don't need to load that separately. 
- There's really no reason for you to source in `Love-boost.R`, unless you actually need it to do something specific.

4. I expect that some people in this class will be really interested in [this genome browser, created using Shiny](https://shiny.rstudio.com/gallery/genome-browser.html).

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

- What do we do if PH assumptions are not met for survival analysis? (Feel like we will be covering that in the next class) 
- How do we build the fancy moving plots we saw in class like the one from Huffington Post? 
    - Is it possible in R shiny or are the graphics too fancy for it?
- Making a bit of sense of the different ways to test the strength of the many different models we have learned recently. 
    - Which functions allow the creation of nomograms, calibration charts, etc. I know some play well and others do not...
- I would still like a little more clarity on when it is justified to peek at the relationship between a predictor and outcome before fitting a model, two by two tables, scatterplot matrices, other graphical exploration?
- Just mildly curious as to whether or not we're going to end up having those meetings with other students during class time or not. 
- How will our final projects be weighted in comparison to the rest of our assignments?
- nothing at the moment
- Will we get some practice using shiny?
- how to tidy up real world data and make it survival analysis-friendly (but this is likely best answered by taking the separate survival analysis course)
- I am not so satisfied with my current grades for 432. Is there any other extra task that I can improve my grades?
- gee model in R
- How should I proceed if my covariates turn out to be more significant than my main predictor in my model? Should I then retain the main predictor or drop it from the final model?
more clarity about the structure of the next quiz 
- Can visualizations that have moving graphics be shown in html documents such as the income mobility example from class 23?
- Do we have requirements as to number of quantitative/categorical predictor of the model for project 2 (like we did for project 1) ?
none
- In censoring, are there specific tests that can be done to compare the censored sample to the rest of the sample in the study. 
- survival analysis not yet clear to me, but with more examples in next lecture I will be fine. Thank you.
- I am planning to use NHANES data for project 2. I will analyze a subpopulation (specific age range, had both interview and exam performed, and had a specific lab test performed). Do I need to incorporate sample weights into my analysis? If so, is there a good example/tutorial that you know of for doing this in R?
- How much R2 important in Poisson model?  

## Remaining Deliverables This Semester

The [Schedule](https://github.com/THOMASELOVE/432-2018/blob/master/SCHEDULE.md) page is always the final word, if you are confused.

- [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) Registration and Scheduling [Google Form](https://goo.gl/forms/Zfgnq5pyAAzAlmUm1) is due at 5 PM **today**. 
    - You can see the status (and title) of proposals that have been reviewed and approved [by visiting this link](https://github.com/THOMASELOVE/432-2018/blob/master/projects/project2/APPROVED.md).
- [Homework 7](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw7) is due at 5 PM on **Tuesday 2018-04-24**. Submit to [Canvas](https://canvas.case.edu/).
- [Quiz 2](https://github.com/THOMASELOVE/432-2018/tree/master/quizzes/quiz2) will go out after class on 2018-04-26, and is due at Noon on **Tuesday 2018-05-01**.
- [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) Final Portfolio materials are due 3 hours prior to your Presentation to me. Submit to [Canvas](https://canvas.case.edu/).
- [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) Presentations are on **2018-05-03**, **2018-05-07** and **2018-05-08**, and will be scheduled by 2018-04-19.
- [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) Revisions are due at Noon on **Wednesday 2018-05-09**. Whether you'll need to revise will be determined at your presentation.
