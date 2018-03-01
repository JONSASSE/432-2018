# 432 Homework 4 for Spring 2018

## Links to Post-Deadline Materials

- Answer Sketch: [Download R Markdown](https://raw.githubusercontent.com/THOMASELOVE/432-2018/master/assignments/hw4/hw4sketch.Rmd), or [View HTML result](http://htmlpreview.github.io/?https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw4/hw4sketch.html), or [Download or View PDF result](https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw4/hw4sketch.pdf)
- [Grading Rubric](http://htmlpreview.github.io/?https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw4/432-assignment-4-rubric.html) now available.
- [Grades](https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw4/hw4grades.pdf) are also posted.
- We have provided you with a set of [four of the essays we liked from HW 4](https://github.com/THOMASELOVE/432-2018/blob/master/assignments/hw4/hw4_essays_we_liked_2018.pdf) which might help you see what we're looking for. Thanks to the students who wrote these essays for their permission to include them in this list.

## Original Instructions

Submit your response via [canvas.case.edu](https://canvas.case.edu/) no later than **1 PM on Friday 2018-02-23**. Your response should include an R Markdown file and an HTML document that is the result of applying your R Markdown file. 

Start a separate R Project for Homework 4 as your first step, and place all of your work in that project's directory.

# The Data

Use the `bird.csv` file available at the [Data and Code page](https://github.com/THOMASELOVE/432-2018/tree/master/data-and-code) or above.

In 1972-1981, a health survey in The Netherlands discovered an association between keeping pet birds and increased risk of lung cancer. To investigate birdkeeping as a risk factor, researchers conducted a case-control study of patients in 1985 at four hospitals in The Hague (population 450,000). Specifically, Holst et al. (1988) identified 49 cases of lung cancer among the patients who were registered with a general practice, who were age 65 or younger and who had resided in the city since 1965. They also selected 98 controls from a population of residents having the same general age structure. 

The available data are:

Variable  | Description
---------- | --------------------------------------------------------
`subject` | Subject ID #, ranging from 1001 - 1147
`lungc`   | 1 for lung cancer patients, 0 for others.
`sex`     | subject's sex: M or F 
`ses`     | subject's socio-economic status: Low or High
`petbird` | did subject keep a bird: 1 (yes) or 0 (no)
`age`     | subject's age in years 
`smokeyr` | subject's years smoking
`cigs`    | subject's cigarettes smoked per day

### Reference

-  Holst, P.A., Kromhout, D. and Brand, R. (1988). For Debate: Pet Birds as an Independent Risk Factor for Lung Cancer, *British Medical Journal 297*: 13-21.

## Question 1 (60 points)

You will fit a logistic regression model to address the key research question here, which is:

*After age, sex, socio-economic status and smoking have been controlled for, is there an additional risk associated with keeping a bird as a pet?*

You will need to:

1. specify an appropriate model for the data, then 
2. evaluate the quality of that model, appropriately,
3. and then provide an estimate (odds ratio with associated 95\% confidence interval and careful interpretation) that addresses the research question above directly, then state your conclusion about whether this additional risk exists, and if so, how large is it?

Some specific suggestions:

- Use complete English sentences, punctuated by (well-edited) critical statistical output. Include the code used to produce that output in your HTML file.
- Focus your presentation on the things that are *most important* for your reader to see.
- Feel free to fit the simplest possible model that meets the requirements of the question. 
    + Your model will need to include all of the effects that are supposed to be accounted for, but you need not fit complex interaction or other non-linear terms on the right-hand side of the model unless you choose to do so.
- You will have multiple decisions to make about how best to fit and analyze your model. Describe those choices well in your response. 

## Question 2 (40 points)

1. First, in 2-4 complete English sentences, I want you to specify, using your own words and complete English sentences, the most useful and relevant piece of advice you took away from reading Jeff Leek's *How To Be A Modern Scientist*. Please provide a reference to the section of the book that provides this good advice. (For those of you who can more easily find things to gripe about in the book, don't worry - you will get that chance down the line.) 

2. Then, in an essay of 4-8 additional sentences, describe why this particular piece of advice was meaningful or useful for you, personally, and how it will affect the way you move forward. You are encouraged to provide a specific example of a past or current scientific experience of yours that would have been (or is being) helped by this new approach or idea. Why is this idea important and worth sharing?

