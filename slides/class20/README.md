# 432 Class 20: 2018-03-29

## Key Materials

- The [slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class20) are posted.
- The [audio files](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class20) will appear when available.

Today's class will address building regression models for count outcomes, in particular zero-inflated and hurdle models. We may also get to tobit models. See [Chapter 18 of the Course Notes](https://thomaselove.github.io/432-notes/modeling-a-count-outcome-in-ohio-smart.html#where-to-read-this-chapter-1) for more on regression for count outcomes.

## A Special Note on the `countreg` package

To build rootograms to visualize the results of regression models on count outcomes, I will occasionally use the `countreg` package, which is currently available **on R-Forge only**.

To install `countreg`, type `install.packages("countreg", repos="http://R-Forge.R-project.org")` into the R Console within R Studio. If that doesn't work today (and it might not) then wait a day, and try again. I believe an update will happen on 2018-03-30 at R-Forge that might address the problem. If not, I'll try to find a workaround.

## Announcements

1. There are **substantial** changes in the schedule of remaining deliverables:
    - [Homework 6](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw6) will now be due at 1 PM on **Friday** 2018-04-13, rather than on 2018-04-06. 
        - Note that I also adjusted the wording of Question 5 in Homework 6 rather substantially on 2018-03-28.
    - [Homework 7](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw7) will now be due at 5 PM on **Tuesday** 2018-04-26, rather than on 2018-04-13.
    - [Quiz 2](https://github.com/THOMASELOVE/432-2018/tree/master/quizzes/quiz2) will now be made available at the end of our final class, on 2018-04-26, and will be due on Tuesday 2018-05-01 at Noon.
    - The [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) deadlines are unaffected, and remain:
        1. 2018-04-17 5 PM Project 2 Registration and Scheduling Form due
        2. Three Hours Before Your Presentation: Project 2 Portfolio for Presentation due
        3. Portfolio Presentation will be on 2018-05-03, 2018-05-07 or 2018-05-08.
        4. Final Portfolio Deadline (after making necessary changes determined during presentation) is 2018-05-09 at noon.

As always, the [Schedule page](https://github.com/THOMASELOVE/432-2018/blob/master/SCHEDULE.md) is always the final word, if you are confused.

2. [This is a nice cheat sheet](http://www.cookbook-r.com/Manipulating_data/Converting_data_between_wide_and_long_format/) to help in converting data from wide to long format. I can never get `gather()` and `spread()` right without thinking about it, probably because I learned other methods first. Take a look.

These data are arranged in **wide** format:

```
subject sex control cond1 cond2
       1   M     7.9  12.3  10.7
       2   F     6.3  10.6  11.1
```

And these are the same data in **long** format:

```
subject sex condition measurement
       1   M   control         7.9
       1   M     cond1        12.3
       1   M     cond2        10.7
       2   F   control         6.3
       2   F     cond1        10.6
       2   F     cond2        11.1
```
