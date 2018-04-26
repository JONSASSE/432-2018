# 432 Class 28: 2018-04-24

## Key Materials

- The [slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class28) include some leftover material from Class 27, plus some new things.
- The [audio files](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class28) are now available.

In today's class, I will be talking about retrospective power, Type S and Type M errors, and classification and regression trees. Plus some thoughts on visualization, Quiz 2 and your Project 2 presentations.

## Visualization of the Day

is [this gif by Dana Page Seidel](https://raw.githubusercontent.com/dpseidel/tidytuesday/master/TidyWork/tuition2.gif).

- is based on the data from the Week 1 [Tidy Tuesday](https://github.com/rfordatascience/tidytuesday) project on [Average Tuition and Educational Attainment in the U.S.](https://onlinembapage.com/average-tuition-and-educational-attainment-in-the-united-states/)
- All of the details and code at [Dana Page Seidel](https://github.com/dpseidel/tidytuesday/blob/master/TidyWork/Week1.md)'s repository.

## Announcements at the start of class

1. You should receive a request from the University to fill out a Course Evaluation. **Please** do so.

2. The answer sketch (revised) for [Homework 7](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw7) is available for [viewing in HTML](http://htmlpreview.github.io/?https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw7/hw7_sketch.html) or as a [R Markdown file](https://raw.githubusercontent.com/THOMASELOVE/432-2018/master/assignments/hw7/hw7_sketch.Rmd). 
   - The Homework 7 grading rubric is [available as a PDF](https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw7/hw7_rubric.pdf).
   - The data set and image for our Question 1 visualization [are also available](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw7).
   - [Grades for Homework 6](https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw6/hw6grades.pdf) are now posted.

3. The Schedule of Project 2 Presentations (and some logistical information) [is available](https://github.com/THOMASELOVE/432-2018/blob/master/projects/project2/PRESENTATIONS.md). Please take a look now, to verify that the time you're scheduled for works.

4. [Quiz 2](https://github.com/THOMASELOVE/432-2018/blob/master/quizzes/quiz2/README.md) materials are available. Note that the Quiz now has 34 main questions (1-34) that are required, plus two optional BONUS questions (35-36).

5. A reminder that the ["Rethinking Statistical Significance"](https://github.com/THOMASELOVE/rethink) repository contains some of today's references. 
   - As a follow-up from our discussion on Tuesday, you may be interested in this piece by Steve Luck on [Why I've Lost Faith in p values](https://lucklab.ucdavis.edu/blog/2018/4/19/why-i-lost-faith-in-p-values)

6. `431-help` will be open through May 9 at 11 AM. The last day for TA office hours is Tuesday May 1.

7. **An R Tip**: Suppose you're trying to use `case_when` to help you change a value like `99` to `NA`. As [this note suggests](https://github.com/tidyverse/dplyr/issues/3202), you need to use `99 ~ NA_real_`, rather than `99 ~ NA`.

8. Here's a great post by [David Selby](http://selbydavid.com/) on [Building a Neural Network in R](http://selbydavid.com/2018/01/09/neural-network/).

9. **Recommendations**: At the end of this README are some links to things I recommend.
   
## Remaining Deliverables This Semester

The [Schedule](https://github.com/THOMASELOVE/432-2018/blob/master/SCHEDULE.md) page is always the final word, if you are confused.

1. [Quiz 2](https://github.com/THOMASELOVE/432-2018/tree/master/quizzes/quiz2) will go out after class on 2018-04-26, and is due at Noon on **Tuesday 2018-05-01**.
2. [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) Final Portfolio materials are due 3 hours prior to your Presentation to me. Submit to [Canvas](https://canvas.case.edu/).
3. [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) Presentations are on **2018-05-03**, **2018-05-07** and **2018-05-08**, and the [complete schedule is here](https://github.com/THOMASELOVE/432-2018/blob/master/projects/project2/PRESENTATIONS.md).
4. [Project 2](https://github.com/THOMASELOVE/432-2018/tree/master/projects/project2) Revisions are due at Noon on **Wednesday 2018-05-09**. 
    - Not all Projects require revision. Whether you'll need to revise will be determined at your presentation.

As mentioned, I'd also really appreciate it if you complete the **University Course Evaluation**. Thanks.

## Some Things I Recommend

- [FiveThirtyEight](http://fivethirtyeight.com/)
- [Simply Statistics](https://simplystatistics.org/)
- [Statistical Modeling, Causal Inference and Social Science](http://andrewgelman.com/) (Andrew Gelman)
- [American Statistical Association](http://www.amstat.org/)
- [Statistics Done Wrong](https://www.statisticsdonewrong.com/)
- [STATS at Sense about Science](http://senseaboutscienceusa.org/stats/)
- [New York Times - The Upshot](https://www.nytimes.com/section/upshot)
- [Census Infographics and Visualizations](https://www.census.gov/library/visualizations.html)
- [Gapminder](https://www.gapminder.org/)
- [JunkCharts](http://junkcharts.typepad.com/junk_charts/) and [Numbers Rule Your World](http://junkcharts.typepad.com/numbersruleyourworld/) by Kaiser Fung
- [Flowing Data](https://flowingdata.com/)
- [Statistical Thinking](http://www.fharrell.com/) from Frank Harrell
- [R Studio Community](https://community.rstudio.com/)
- [EdwardTufte.com](https://www.edwardtufte.com/tufte/)
- [David Selby's Tea & Stats](http://selbydavid.com/)

### A few podcasts

- [Not So Standard Deviations podcast](http://nssdeviations.com/)
- [The Effort Report podcast](http://effortreport.libsyn.com/)
- [Freakonomics](http://freakonomics.com/)
- [More or Less: Behind the Stats](https://www.bbc.co.uk/programmes/p02nrss1)
- [Stats + Stories](https://www.npr.org/podcasts/530134710/stats-stories)

### A few Twitter handles

@ThomasELove
@askdrstats
@RLangTip
@rstudiotips
@JennyBryan
@hadleywickham
@StatsbyLopez
@LizStuartDC
