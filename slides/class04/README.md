# 432 Class 04: 2018-01-25

### Key Materials

As they become available, [the slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class04) and the [audio files](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class04) will be posted above.

In today's class, we'll focus on making predictions, centering and rescaling predictors, analysis of variance, and model validation.

## Announcements Before Class 04

1. Don't forget to [submit Homework 1](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw1) by 1 PM on Friday 2018-01-26. Use [Canvas](https://canvas.case.edu) to do so. If you have questions about the homework, please ask them at 431-help at case dot edu, or during [TA office hours](https://github.com/THOMASELOVE/432-2018/blob/master/SCHEDULE.md#teaching-assistant-office-hours).
    - Re: footnotes. I would list the notes as a bulleted list in the Markdown file, and do everything in Markdown, as a result.
    - Re: dealing with missingness. It's not usually appropriate to report results that include imputation in a Table 1, so I expect the best choice is to build a note specifying the amount of missing data.
    - Re: building BMI categories. Try `cut2` from the Hmisc package, or `case_when` in the tidyverse.

2. You'll also have a Minute Paper to do after Class 04. **Details to come.**

3. **Types of Interaction** 
    - The usual definitions of additive and multiplicative interaction in epidemiology refer to risks of binary outcomes, rather than to departures from linear models for quantitative outcomes.
    - In linear regression, the regression coefficient of the product term reflects interaction as departure from additivity. 
    - However, in logistic regression, the product term's coefficient reflects interaction as departure from multiplicativity. 
    - There's a series of [papers by Mirjam Knol and others](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3115067/) on estimating measures of interaction on an additive scale in the context of logistic regression, which is appealing from a population health perspective.

4. **Dr. Love plans to write** 
    - something about why we use 1/0 for indicator variables (like 1 = female, 0 = male) rather than 1/2 (1 = male, 2 = female) and what the impact of doing things the other way would be, practically.
    - something about whether it matters what order you enter predictors into a regression model (or, more accurately, *when* it matters.

Other suggestions or questions? - please email `431-help at case dot edu`

## Announcements After Class 04
