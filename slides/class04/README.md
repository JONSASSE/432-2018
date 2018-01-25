# 432 Class 04: 2018-01-25

### Key Materials

[The slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class04) are online, and the [audio files](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class04) will be posted above when they become available.

In today's class, we'll focus on making predictions, centering and rescaling predictors, analysis of variance, and model validation.

## Announcements Before Class 04

1. Don't forget to [submit Homework 1](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw1) by 1 PM on Friday 2018-01-26. Use [Canvas](https://canvas.case.edu) to do so. If you have questions about the homework, please ask them at 431-help at case dot edu, or during [TA office hours](https://github.com/THOMASELOVE/432-2018/blob/master/SCHEDULE.md#teaching-assistant-office-hours).
    - Re: footnotes. I would list the notes as a bulleted list in the Markdown file, and do everything in Markdown, as a result.
    - Re: dealing with missingness. It's not usually appropriate to report results that include imputation in a Table 1, so I expect the best choice is to build a note specifying the amount of missing data.
    - Re: building BMI categories. Try `cut2` from the Hmisc package, or `case_when` in the tidyverse.
    - Remaining office hours for TAs include 2:30 - 4:30 Thursday and 12:15 - 1 PM on Friday.

2. **Post-Class Minute Paper**. Please fill out [this Google Form](https://goo.gl/forms/N281latgrk3wqJvf1) as soon as possible **after** today's class, for some class participation credit (if you get it in by 9 AM Monday) and to provide us with some feedback about how things are going so far. Thanks so much.

3. **Types of Interaction** 
    - The usual definitions of additive and multiplicative interaction in epidemiology refer to risks of binary outcomes, rather than to departures from linear models for quantitative outcomes.
    - In linear regression, the regression coefficient of the product term reflects interaction as departure from additivity. 
    - However, in logistic regression, the product term's coefficient reflects interaction as departure from multiplicativity. 
    - There's a series of [papers by Mirjam Knol and others](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3115067/) on estimating measures of interaction on an additive scale in the context of logistic regression, which is appealing from a population health perspective.

## Announcements After Class 04
