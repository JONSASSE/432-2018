# 432 Class 24: 2018-04-12

## Key Materials

- The [slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class24) are now posted.
- The [audio files](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class24) will be posted as soon as they are available.

Today's class will begin with discussion of two more animated data visualizations, and then we'll discuss methods for exploring time-to-event / survival data with Cox proportional hazards regression models. Chapters 22 and 23 of the [Course Notes](https://thomaselove.github.io/432-notes/) describe the main ideas behind Cox proportional hazards regression models incorporating covariates that do not change over time.

Links to the visualizations we'll discuss today:

- [Baby Name Voyager](http://www.babynamewizard.com/voyager)
- Better Health Partnership's [Social Determinants and Children's Health](http://betterhealthpartnership.org/members/chiToolWeightBP.asp) tool

## Announcements at the start of class

1. There is a [Minute Paper after today's class](https://goo.gl/forms/blYi0wADJLUALvV03). Please complete the form by Monday at 10 AM.

2. I ran an insta-poll during last class. Thank you all for participating. The results were, well, inconclusive...

![](https://raw.githubusercontent.com/THOMASELOVE/432-2018/master/slides/class24/poll_result.png)

3. 431 materials are moving, in preparation for their disappearance in June. Most things are now linked from https://github.com/THOMASELOVE/431-2017. If you have trouble finding something you need, email 431-help.

4. As mentioned last time, Chapter 23 of the Course Notes is meant to have some images that aren't showing up yet in the Course Notes. Since I've yet to figure out the problem, I'm providing a draft version of both Chapters 22 and 23 where the images appear. See [the HTML here](https://htmlpreview.github.io/?https://github.com/THOMASELOVE/432-2018/blob/master/slides/class24/chapters_22_and_23_draft.html), and [the R Markdown here](https://raw.githubusercontent.com/THOMASELOVE/432-2018/master/slides/class24/chapters_22_and_23_draft.Rmd).

## Remaining Deliverables This Semester

The [Schedule](https://github.com/THOMASELOVE/432-2018/blob/master/SCHEDULE.md) page is always the final word, if you are confused.

- [Homework 6](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw6) is due at 1 PM on **Friday 2018-04-13** (tomorrow). Submit to [Canvas](https://canvas.case.edu/).
- [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) Registration and Scheduling [Google Form](https://goo.gl/forms/Zfgnq5pyAAzAlmUm1) is due at 5 PM on **Tuesday 2018-04-17**.
    - You can see the status (and title) of proposals that have been reviewed and approved [by visiting this link](https://github.com/THOMASELOVE/432-2018/blob/master/projects/project2/APPROVED.md).
- [Homework 7](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw7) is due at 5 PM on **Tuesday 2018-04-24**. Submit to [Canvas](https://canvas.case.edu/).
- [Quiz 2](https://github.com/THOMASELOVE/432-2018/tree/master/quizzes/quiz2) will go out after class on 2018-04-26, and is due at Noon on **Tuesday 2018-05-01**.
- [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) Final Portfolio materials are due 3 hours prior to your Presentation to me. Submit to [Canvas](https://canvas.case.edu/).
- [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) Presentations are on **2018-05-03**, **2018-05-07** and **2018-05-08**, and will be scheduled by 2018-04-19.
- [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) Revisions are due at Noon on **Wednesday 2018-05-09**. Whether you'll need to revise will be determined at your presentation.
