# 432 Class 26: 2018-04-19

## Key Materials

- The [slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class26) will be posted as soon as possible.
- The [audio files](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class26) will be posted as soon as possible.

Today's class will include:

1. data visualization ideas from [flowingdata.com](http://flowingdata.com/)
2. some specific issues related to logistic regression model selection and classification assessment
3. some clarifying comments on spending degrees of freedom, the Spearman rho-squared plot, and how regression models should be built
4. some discussion of retrospective power, Type S and Type M errors
5. some discussion of broader issues in scientific replicability and statistical significance

which may continue on into Class 27. There is no Minute Paper today.

## Announcements at the start of class

1. The Schedule of Project 2 Presentations (and some logistical information) [is now available](https://github.com/THOMASELOVE/432-2018/blob/master/projects/project2/PRESENTATIONS.md). Please take a look now, to verify that the time you're scheduled for works.

2. I posted a hint for question 3 on [Homework 7](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw7). 
    - When you have a time-to-event outcome, you just use the survival time, and not the whole survival object (i.e. you ignore the censoring) in building a Spearman rho-squared plot.

3. The version of Chapters 22 and 23 where all images appear is [available in HTML here](https://htmlpreview.github.io/?https://github.com/THOMASELOVE/432-2018/blob/master/slides/class24/chapters_22_and_23_draft.html), and also [in R Markdown](https://raw.githubusercontent.com/THOMASELOVE/432-2018/master/slides/class24/chapters_22_and_23_draft.Rmd).

4. Those of you interested in Python probably already know that [PyCon 2018 is in Cleveland](https://us.pycon.org/2018/about/) May 9-17. Registration is $125 for students.

## Remaining Deliverables This Semester

The [Schedule](https://github.com/THOMASELOVE/432-2018/blob/master/SCHEDULE.md) page is always the final word, if you are confused.

1. [Homework 7](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw7) is due at 5 PM on **Tuesday 2018-04-24**. Submit to [Canvas](https://canvas.case.edu/).
2. [Quiz 2](https://github.com/THOMASELOVE/432-2018/tree/master/quizzes/quiz2) will go out after class on 2018-04-26, and is due at Noon on **Tuesday 2018-05-01**.
3. [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) Final Portfolio materials are due 3 hours prior to your Presentation to me. Submit to [Canvas](https://canvas.case.edu/).
4. [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) Presentations are on **2018-05-03**, **2018-05-07** and **2018-05-08**, and the [complete schedule is here](https://github.com/THOMASELOVE/432-2018/blob/master/projects/project2/PRESENTATIONS.md).
5. [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) Revisions are due at Noon on **Wednesday 2018-05-09**. Whether you'll need to revise will be determined at your presentation.

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

