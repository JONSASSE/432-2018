# 432 Class 18: 2018-03-22

### Key Materials

- The [slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class18) are now available. A typo on slide 4 is now fixed.
- The [audio files](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class18) will appear as they become available.

Today's class will focus on building regression models for count outcomes, in particular Poisson regression models and Negative Binomial regression models. The data set comes from the `HSAUR` package, which I've added to our list of [packages to install](https://github.com/THOMASELOVE/432-2018/blob/master/data-and-code/PACKAGES.MD). 

- See [Chapter 18 of the Course Notes](https://thomaselove.github.io/432-notes/modeling-a-count-outcome-in-ohio-smart.html#where-to-read-this-chapter-1) for more on this topic.

## Announcements at the start of class

1. [Project 1 Final Portfolio](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project1#the-portfolio) is due at **1 PM Friday 2018-03-23**. Submit via Canvas. 
    - Include the following three files (each of which should have your name as part of the filename, please)
        - a .csv file of the data (use the data that your Markdown file works with) 
        - a .Rmd file built on the Project 1 template, and
        - an .html file which is the unedited result of knitting your R Markdown file
    - If you have additional materials you wish to submit, OK, but I must be able to grade your work based on the .html file alone.

2. There is a [Minute Paper after Class 18](https://goo.gl/forms/qagV2F1gEguCgJr53). It's due at **Noon on Monday 2018-03-26**, and it is likely better to finish Project 1 and submit it before doing the Minute Paper, since one of the questions is: *What was the most difficult challenge you faced in doing your Project 1?*

3. Those of you doing the [Bonus Assignment to improve a poor Quiz 1 grade](https://github.com/THOMASELOVE/432-2018/tree/master/quizzes/quiz1/bonus) need to submit that to Canvas by **Noon on Monday 2018-03-26**.

4. The next assignment after Project 1 is [Homework 6](https://github.com/THOMASELOVE/432-2018/tree/master/assignments), which is due at 1 PM on 2018-04-06.

5. We'll discuss [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) in class on Tuesday 2018-03-27. 
    - The first deliverable is the [Registration/Scheduling Form](https://goo.gl/forms/Zfgnq5pyAAzAlmUm1), due at 5 PM on 2018-04-17.
    
6. [Chapter 17 of the Course Notes](https://thomaselove.github.io/432-notes/cleaning-the-brfss-smart-data.html) includes a lot of information on the creation of a tidy data set from the BRFSS SMART data. I encourage you to look that material over on your own time.
    - You can [read the chapter here](http://htmlpreview.github.io/?https://github.com/THOMASELOVE/432-2018/blob/master/data-and-code/SMART/smart.html).
    - This [README file](https://github.com/THOMASELOVE/432-2018/tree/master/data-and-code/SMART) has some additional useful information, and links to the sources.
    - If you're looking for a Project 2 data set and are interested in the BRFSS, you can certainly use data from the BRFSS, or even the Selected Metropolitan/Micropolitan Area Risk Trends of BRFSS that I'm dealing with here, but you'd have to do so including **more locations than just those in the state of Ohio**, since I've looked pretty closely at Ohio.

### Posted After Class

Sorry for the late release on this. All good ideas that are in me somewhere work themselves out eventually, but not always in a timely way. Take this as useful advice for Project 1 if it addresses an issue that's bugging you and that you still have time to do something about, or ignore it for now, and use it as advice for Project 2 if you've moved past this in your head.

#### How do you describe a restricted cubic spline that I've fit in a model? Do I write out that equation with the variablename' and variablename'' in it, or ... ?

Tell me how many knots were involved and show me a graph that depicts the impact of the spline. No one explains splines without a graph. Make a graph and use it is excellent advice for many aspects of your presentation. Sensible graphs to accomplish this task in a multivariate regression model include the ggplot with Predict combination or a nomogram.

#### If I have two models that aren't very far apart in terms of validation, where Model 1 is much simpler but less good in terms of validation than Model 2, which model would you focus on?

If the validation results are at all comparable, then I'd definitely focus on the simpler model.

#### If I have a C statistic, do I need to also plot the ROC curve?

I can't think of a compelling reason to do so. This is one of the few places where the plot isn't much additional help, at least in terms of what we're trying to do in Project 1.

 
