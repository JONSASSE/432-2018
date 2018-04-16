# 432 Class 25: 2018-04-17

## Key Materials

- The [slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class25) are now posted.
- The [audio files](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class25) will be posted as soon as they are available.

Today's class will conclude our discussion of Cox proportional hazards regression models. As a reminder, Chapters 22 and 23 of the [Course Notes](https://thomaselove.github.io/432-notes/) describe the main ideas behind Cox proportional hazards regression models incorporating covariates that do not change over time.

We'll also look at some data visualizations (before we get to the slides) and address a few loose ends that have been hanging for a while, related to earlier materials in the course, specifically about the purpose of our models, restricted cubic splines, interpreting the fit of a logistic regression and variable selection for logistic regression.

## Announcements at the start of class

1. The Homework 6 Answer Sketch and Grading Rubric is now posted as an [HTML document you can view](http://htmlpreview.github.io/?https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw6/hw6sketch.html), and as an [R Markdown file you can download](https://raw.githubusercontent.com/THOMASELOVE/432-2018/master/assignments/hw6/hw6sketch.Rmd).

2. Remember that a draft version of both Chapters 22 and 23 where all images appear is available. See [the HTML here](https://htmlpreview.github.io/?https://github.com/THOMASELOVE/432-2018/blob/master/slides/class24/chapters_22_and_23_draft.html), and [the R Markdown here](https://raw.githubusercontent.com/THOMASELOVE/432-2018/master/slides/class24/chapters_22_and_23_draft.Rmd).

3. **Project 2 Tip**: Most students should wind up using between 4 and 10 R packages in the project. 
    - Everyone, I think, will need to load `skimr`, `broom`, `rms` and the `tidyverse`. 
    - It's OK to load more, but **don't** load something else unless you actually need it. Don't just load everything we've used this semester. 
    - Remember that `tidyverse` loads `forcats`, so you shouldn't load `forcats` if you're loading `tidyverse`. Similarly, `rms` loads `Hmisc`, so you don't need to load that separately. 
    - There's really no reason for you to source in `Love-boost.R`, unless you actually need it to do something specific.

4. If you are interested in reading [32 pages of PDF notes I wrote in Spring 2016 on **longitudinal data analysis**](https://github.com/THOMASELOVE/432-2018/blob/master/texts/432_notes_from_2016_on_longitudinal_data.pdf), specifically about spaghetti plots, response feature analysis, repeated measures ANOVA, and the basics of generalized estimating equations (GEE), well, [I've posted it to our Texts page](https://github.com/THOMASELOVE/432-2018/blob/master/texts/432_notes_from_2016_on_longitudinal_data.pdf). No warranties, but you're welcome to it.

## Minute Paper after Class 24 (40 responses, advice for prospective students not yet edited)

### Please describe your current Project 2 progress 

Count `(%)` | Response
----------: | --------------------------------------------------------------------
9 `(22.5)` | Proposal is approved and I've starting working with the data.
5 `(12.5)` | Proposal is approved but that's it.  
1 `(2.5)` | Proposal submitted but not yet approved.
24 `(60.0)` | I am working on my proposal, and am nearing the point where I can submit it.
1 `(2.5)` | I haven't really gotten rolling on the proposal yet.

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
- Read the class notes on the models that we do not use often (e.g. Poisson)
- Focus during classes. Reading the course note is very helpful.
- Allocate at least 4 hours a week for homework, readings, catching up. Attend every class or at least listen to online audio. 
- It needs a lot of studying. 
- Dr. Love is very helpful. His code is useful and he is willing to help with troubleshooting.
- I found the data camp introduction lessons on R functions/basic data management to be very helpful even near the end of the second semester. Providing this resource to students new to R and those who could use refresher before the course begins might be a good idea.
- Focused on everything in the class
- Some kind of an Intro to R course is extremely beneficial before starting 431-432
- Helping them find their data right from the start of the course may ease their burden.
- Get R, RStudio installed, and start working with R as soon as possible. Time and effort is the only thing that helps when it comes to computer Languages. Start with Markdown right away, and soon, at least working with git within RStudio. Roger Peng has a good intro courses in coursera. Jeff Leek also has 2 courses called statistics boot camp that would be good to get the stats frame of mind going.  
- Expect a lot of work outside of class and start projects/assignments early.
- If you intend to take both courses, make sure you take Dr. Love's section of 431
- Have a basic understanding of R will help. 

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
7. Is there a way to calculate AIC and BIC for zero-inflated models?
    - I don't know. I use Vuong's test to compare zero-inflated models to their non-zero-inflated counterparts. You could use a likelihood ratio test to compare a zero-inflated Poisson to a zero-inflated negative binomial with the same predictors, since the output does produce the log likelihood estimates.
8. Just mildly curious as to whether or not we're going to end up having those meetings with other students during class time.
    - No, we're not.
9. Do we get to learn about propensity score matching?
    - Next Tuesday was the day I plan to talk about it, but whether I'll do it Tuesday or Thursday next week depends on how things go this Thursday. Of course, I teach the 500 course every spring, and that's all about propensity score analysis. You'd be welcome to join us. Several students in this year's 432 class are finishing 500 as well now, and they can tell you all about it from the student perspective.
10. In Project 2, do you prefer that we give a Powerpoint presentation?
    - I prefer only that you give me a clear understanding of what you've done, in whatever way works **best for you**. Some people do well working with the results of their HTML exclusively, others prefer to gather their thoughts into a separate presentation. I've seen excellent results with lots of different approaches (HTML, Powerpoint, Prezi, PDF, Keynote, etc. etc.), and I don't want to get in the way of you putting your best foot forward. You do you.
11. What's the format of the Project 2 presentation? What if it's done by two people?
    - In the 20 minutes you're in the room, expect Dr. Love to set a timer for 16 minutes, and let you lead the presentation **on your laptop** in that time while he occasionally asks questions (if there are two of you, one will speak for the first 8 minutes or so, then Dr. Love will switch over to the other speaker.) 
        - Dr. Love will speed you up if he needs to, so you get your primary conclusions in before the time runs out, but you should plan your talk to last about 15 minutes. 
        - Then for the last few minutes, Dr. Love will make some general comments and ask you a couple of specific questions (usually these include how much of your time was spent cleaning vs. analyzing data, and what would you tell yourself now that you wish you'd known when you started the project.)
    - If you're a group of two, then one of you talks for a while, and then the other one talks for a while. **Dr. Love** determines who talks when, so you both need to be prepared to address the whole thing, and Dr. Love will ask questions of each of you at any time, so you can't fall asleep while the other person talks.

## Today's Data Visualizations

- Noah Veltman's [NFL Player Size](https://noahveltman.com/nflplayers/) visualization.
- A few basic Shiny apps to learn from:
    - [Old Faithful](https://shiny.rstudio.com/gallery/faithful.html)
    - [K-Means Clustering in the Iris data](https://shiny.rstudio.com/gallery/kmeans-example.html)
    - [Inline output as part of a Markdown-based Notebook](https://shiny.rstudio.com/gallery/inline-output.html)
- I expect that some people in this class will be really interested in [this ICGC pancreatic cancer (ductal adenocarcinoma) genome browser, created using Shiny](https://shiny.rstudio.com/gallery/genome-browser.html). 
- If you want to learn Shiny, the best place to start is [this tutorial page at R Studio](http://shiny.rstudio.com/tutorial/), which guides you to lots of great resources.

## Remaining Deliverables This Semester

The [Schedule](https://github.com/THOMASELOVE/432-2018/blob/master/SCHEDULE.md) page is always the final word, if you are confused.

- [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) Registration and Scheduling [Google Form](https://goo.gl/forms/Zfgnq5pyAAzAlmUm1) is due at 5 PM **today**. 
    - You can see the status (and title) of proposals that have been reviewed and approved [by visiting this link](https://github.com/THOMASELOVE/432-2018/blob/master/projects/project2/APPROVED.md).
- [Homework 7](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw7) is due at 5 PM on **Tuesday 2018-04-24**. Submit to [Canvas](https://canvas.case.edu/).
- [Quiz 2](https://github.com/THOMASELOVE/432-2018/tree/master/quizzes/quiz2) will go out after class on 2018-04-26, and is due at Noon on **Tuesday 2018-05-01**.
- [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) Final Portfolio materials are due 3 hours prior to your Presentation to me. Submit to [Canvas](https://canvas.case.edu/).
- [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) Presentations are on **2018-05-03**, **2018-05-07** and **2018-05-08**, and will be scheduled by 2018-04-19.
- [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) Revisions are due at Noon on **Wednesday 2018-05-09**. Whether you'll need to revise will be determined at your presentation.