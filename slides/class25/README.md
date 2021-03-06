# 432 Class 25: 2018-04-17

## Key Materials

- The [slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class25) are now posted. Some of the materials on the original slides was not covered, and now appears in the Slides for Class 26.
- The [audio files](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class25) are now posted.

Today's class will conclude our discussion of Cox proportional hazards regression models. As a reminder, Chapters 22 and 23 of the [Course Notes](https://thomaselove.github.io/432-notes/) describe the main ideas behind Cox proportional hazards regression models incorporating covariates that do not change over time.

We'll also look at some data visualizations (before we get to the slides) and address a few loose ends that have been hanging for a while, related to earlier materials in the course, specifically about the purpose of our models, restricted cubic splines, interpreting the fit of a logistic regression and variable selection for logistic regression.

## Announcements at the start of class

1. Don't forget that your Registration and Scheduling form for Project 2 is due TODAY at 5 PM. The [Google Form is here](https://goo.gl/forms/Zfgnq5pyAAzAlmUm1). 
    - You can see the status (and title) of proposals that have been reviewed and approved [by visiting this link](https://github.com/THOMASELOVE/432-2018/blob/master/projects/project2/APPROVED.md).
    - The most consistent problem I'm seeing is that people don't necessarily know how to write a research question.
        - It should be a question, not a statement.
        - It should clearly indicate the way in which you intend to answer it.
        - It should clearly indicate the model you have in mind and how the data could be used to address the question.
        - It should lead to a clear understanding of what it is you are actually going to do, and why.
    - Here are three of the early and good research questions I've seen this year...
        - Do social determinants of health (education, insurance type, disability, cigarette use) impact the severity of pre-transplant illness?
        - How well can measures of hospital staff's ability to communicate with patients predict a hospital's readmission rates after an outpatient procedure?
        - What is the impact of self-reported mental health, specifically anxiety and depression, on neuroperformance measures, specifically walking speed and manual dexterity, in multiple sclerosis?
    - The **Schedule** will be posted before class on Thursday of this week. If you (or your group) are the only people selecting your "first choice" time slot, my proprietary neural network algorithm will give you a strong chance of getting it, so long as you have your project submitted by 5 PM Tuesday and I approve it. 
    - If you want to see the slots that have been popular so far as part of some sort of elaborate ten-dimensional chess strategy, [click here](https://github.com/THOMASELOVE/432-2018/blob/master/projects/project2/APPROVED.md#first-choice-of-time-slot-through-24-scheduling-submissions). 
    - Of course, there are still multiple projects still to come in between now and 5 PM, and the *order* in which my software sifts through your request to fill time slots is determined at random across all submissions which are approved on time.

2. The Homework 6 Answer Sketch and Grading Rubric is now posted as an [HTML document you can view](http://htmlpreview.github.io/?https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw6/hw6sketch.html), and as an [R Markdown file you can download](https://raw.githubusercontent.com/THOMASELOVE/432-2018/master/assignments/hw6/hw6sketch.Rmd).

2. Remember that a draft version of both Chapters 22 and 23 where all images appear is available. See [the HTML here](https://htmlpreview.github.io/?https://github.com/THOMASELOVE/432-2018/blob/master/slides/class24/chapters_22_and_23_draft.html), and [the R Markdown here](https://raw.githubusercontent.com/THOMASELOVE/432-2018/master/slides/class24/chapters_22_and_23_draft.Rmd).

3. **Project 2 Tip**: Most students should wind up using between 4 and 10 R packages in the project. 
    - Everyone, I think, will need to load `skimr`, `broom`, `rms` and the `tidyverse`. 
    - It's OK to load more, but **don't** load something else unless you actually need it. Don't just load everything we've used this semester. 
    - Remember that `tidyverse` loads `forcats`, so you shouldn't load `forcats` if you're loading `tidyverse`. Similarly, `rms` loads `Hmisc`, so you don't need to load that separately. 
    - There's really no reason for you to source in `Love-boost.R`, unless you actually need it to do something specific.

4. If you are interested in reading [32 pages of PDF notes I wrote in Spring 2016 on **longitudinal data analysis**](https://github.com/THOMASELOVE/432-2018/blob/master/texts/432_notes_from_2016_on_longitudinal_data.pdf), specifically about spaghetti plots, response feature analysis, repeated measures ANOVA, and the basics of generalized estimating equations (GEE), well, [I've posted it to our Texts page](https://github.com/THOMASELOVE/432-2018/blob/master/texts/432_notes_from_2016_on_longitudinal_data.pdf). No warranties, but you're welcome to it.

## Minute Paper after Class 24 (n = 40 responses)

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

There were many similar suggestions, which I'll boil down to the following for now, but I'll incorporate more individual pieces in what I provide to new students. Thank you!

- **Workload**
    - The course involves a lot of outside-of-class work. It requires a lot of attention, and some busy people don't have the time to do it without rearranging some things. 
    - You really need to devote some time to this. 
    - Coming to class, or at least listening to the audio is crucial. Lots of things happen in class that you wouldn't get just by reading the notes alone.
    
- **Getting Started Quickly**
    - Becoming familiar with R before the class gets rolling is really helpful, and there are lots of good resources to help you, including courses online and at CWRU that seem valuable.
    - Dr. Love should get as much of the required reading out to students in advance of the class as possible.
    - Students have to not procrastinate, and start all assignments early.

- **Use the available resources**
    - Students need to get comfortable with using office hours and 431-help as much as they can, as opposed to trying to figure everything out on their own at the last minute.
    - The course notes are really helpful. Read them.
    - If you intend to take both courses, make sure you take Dr. Love's section of 431.

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
5. What does a low value of R-square mean, in all of these new settings?
    - A really low value of R-square, be it an OLS R-square, or one of the various estimates available for generalized linear models, is mostly something to worry about because it suggests that there are a lot of "omitted variables" not included in the model that might have an impact. This might well mean that such things were never measured - usually it means that our understanding of the phenomenon the model is describing (or our measurements of it, at least) are weak.
6. How will our final projects be weighted in comparison to the rest of our assignments?
    - [The syllabus](https://thomaselove.github.io/432-syllabus/deliverables-and-grading.html#grading) is your friend here. The projects, together, are 35% of your grade. The second project carries 60% of the weight of the two projects, with the first project carrying the remaining 40%.
7. Which functions allow the creation of nomograms, etc. I know some play well and others do not...
    - Nomograms are built with the `rms` package, and work with models fit using `ols`, `lrm`, and `cph` that we've studied.
8. Is there a way to calculate AIC and BIC for zero-inflated models?
    - I don't know. I use Vuong's test to compare zero-inflated models to their non-zero-inflated counterparts. You could use a likelihood ratio test to compare a zero-inflated Poisson to a zero-inflated negative binomial with the same predictors, since the output does produce the log likelihood estimates.
9. If I have an outcome which is a measurement of time (like, say, length of stay in a hospital) but there's no censoring, should I treat that length of stay as a time to event (and thus use a Cox model) or as a quantitative variable (and fit, for instance, a linear regression?)
    - Just because an outcome is a time to an event doesn't mean you have to fit a Cox model. A Cox model is specifically designed to deal with **censoring**. If there is no censoring, there's no reason to choose a Cox model over the much simpler OLS approach.
10. Are we going to end up having those meetings with other students during class time?
    - No, we're not.
11. Do we get to learn about propensity score matching?
    - Next Tuesday was the day I plan to talk about it, but whether I'll do it Tuesday or Thursday next week depends on how things go this Thursday. Of course, I teach the 500 course every spring, and that's all about propensity score analysis. You'd be welcome to join us. Several students in this year's 432 class are finishing 500 as well now, and they can tell you all about it from the student perspective.
12. In Project 2, do you prefer that we give a Powerpoint presentation?
    - I prefer only that you give me a clear understanding of what you've done, in whatever way works **best for you**. Some people do well working with the results of their HTML exclusively, others prefer to gather their thoughts into a separate presentation. I've seen excellent results with lots of different approaches (HTML, Powerpoint, Prezi, PDF, Keynote, etc. etc.), and I don't want to get in the way of you putting your best foot forward. You do you.
13. What's the format of the Project 2 presentation? What if it's done by two people?
    - In the 20 minutes you're in the room, expect Dr. Love to set a timer for 16 minutes, and let you lead the presentation **on your laptop** in that time while he occasionally asks questions (if there are two of you, one will speak for the first 8 minutes or so, then Dr. Love will switch over to the other speaker.) 
        - Dr. Love will speed you up if he needs to, so you get your primary conclusions in before the time runs out, but you should plan your talk to last about 15 minutes. 
        - Then for the last few minutes, Dr. Love will make some general comments and ask you a couple of specific questions (usually these include how much of your time was spent cleaning vs. analyzing data, and what would you tell yourself now that you wish you'd known when you started the project.)
    - If you're a group of two, then one of you talks for a while, and then the other one talks for a while. **Dr. Love** determines who talks when, so you both need to be prepared to address the whole thing, and Dr. Love will ask questions of each of you at any time, so you can't fall asleep while the other person talks.
14. Quiz 2. What's the plan?
    - Still building it. **When it's done, I'll update this**, but the current plan is roughly 60% linear + (binary) logistic regression and roughly 40% everything else. I don't yet know the combination of "analysis you'll have to do" vs. "analysis I'll do that you'll interpret." I'd like it to be no more taxing than HW 6 was, certainly! The current aim is 40 questions. 40 multiple choice questions, actually, but I don't know if I'll actually be able to do that.

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

- Again, remember that the [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) Registration and Scheduling [Google Form](https://goo.gl/forms/Zfgnq5pyAAzAlmUm1) is due at 5 PM **today**. 
    - As mentioned above, you can see the status (and title) of proposals that have been reviewed and approved [by visiting this link](https://github.com/THOMASELOVE/432-2018/blob/master/projects/project2/APPROVED.md).
- [Homework 7](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw7) is due at 5 PM on **Tuesday 2018-04-24**. Submit to [Canvas](https://canvas.case.edu/).
- [Quiz 2](https://github.com/THOMASELOVE/432-2018/tree/master/quizzes/quiz2) will go out after class on 2018-04-26, and is due at Noon on **Tuesday 2018-05-01**.
- [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) Final Portfolio materials are due 3 hours prior to your Presentation to me. Submit to [Canvas](https://canvas.case.edu/).
- [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) Presentations are on **2018-05-03**, **2018-05-07** and **2018-05-08**, and will be scheduled by 2018-04-19.
- [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) Revisions are due at Noon on **Wednesday 2018-05-09**. Whether you'll need to revise will be determined at your presentation.
