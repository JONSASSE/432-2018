# 432 Class 06: 2018-02-01

### Key Materials

[The slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class06) are posted, and the [audio files](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class06) will appear as they become available.

In today's class, we'll continue to focus on linear regression model selection and cross-validation. 

## Announcements Before Class 06

1. Please don't forget to complete [Homework 2](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw2) by 1 PM Friday. Office Hours continue this afternoon from 2:30 - 4:30 and Friday from 12:15 to 1 PM.

2. There is a [minute paper Google Form](https://goo.gl/forms/uylKCzjUMAMeim0w2) for you to complete after Class 06, and before 10 AM on Monday 2018-02-05. Thanks! 

3. I've decided not to discuss stepwise regression any further today, but you can read about it further in the [Class Notes](https://thomaselove.github.io/432-notes/), Chapter 7.

4. The `leaps` package, and in particular the `regsubsets` function, does not handle variables of "character" class. They must all be factors. For instance, in doing HW2, if you run `hbp330 <- read.csv("hbp330.csv") %>% tbl_df` in HW2, this will work better than if you use `hbp330 <- read_csv("hbp330.csv")` because `read_csv` assigns the character class to all variables with letters in the data, while the `read.csv` then `tbl_df` workflow doesn't do this. Or you can do `read_csv` and then apply `df %>% mutate_if(is.character, factor)` to change all of the character variables in `df` to factor variables. This is another "[strings as factors](https://simplystatistics.org/2015/07/24/stringsasfactors-an-unauthorized-biography/)" problem. 
