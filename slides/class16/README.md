# 432 Class 16: 2018-03-08

### Key Materials

- [The slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class15) are now available.
- The [audio files](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class15) are now available.

In today's class, we'll demonstrate five different robust linear regression modeling approaches, including bounded influence regression, penalized least squares and quantile regression. We'll also discuss Quiz 1.

## Project 1 Groups for Discussion in Class

Group | Names
------: | -----------------------------------------------------------------------------
1 | Laura Baldassari, Jenny Feng, Maher Kazimi, Satyakam Mishra, Vinh Trinh
2 | Zainab (Albar) Albar, Dongze (Zaza) He, Nik Krieger, Andrew Shan
3 | Andrew Tang, Sneha Vakamudi, Ruipeng Wei, Peter Wilkinson
4 | Gwen Donley, Carli Lehr, Connor Swingle, Frances Wang
5 | Ryan Honomichl, JJ Huang, Xin Xin Yu, Bilal Zonjy
6 | Khaled Alayed, Kedar Mahajan, Preeti Pathak, Sarah Planchon Pope
7 | Estee Cramer, Laura Cremer, Hyun Jo Kim, Roberto Martinez
8 | Abhishek Deshpande, Jack McDonnell, Grace Park, Gabby Rieth
9 | Haimeng Bai, Sophia Cao, Kate Dobbs, Elina Misicka
10 | Vaishali (Vee) Deo, Caroline El Sanadi, Kaylee Sarna, Sandra Silva Camargo

## Announcements before class

1. We will meet in Room E321-323 for the rest of the semester, **except for** April 5, when we'll meet in E301 again. Sorry about last Thursday. We're still not sure what happened.

2. Remember that we do not have class next week. Enjoy the break.

3. **Best Subsets while Forcing in a Variable**. When fitting a **best subsets** approach to a linear regression, suppose you want to force in variable "a" and then let the software decide about variables b, c, d, e and f. So you are asking best subsets to evaluate models that contain an intercept and variable "a" and then 1-5 of the remaining variables b-f. So the k values for such a model would be 3-7. Note that when you force a variable to be in, the output table listing which variables are forced in and forced out may be incorrect (it's a problem in leaps) but the actual models fit should be correct.

4. **Best Subsets for Generalized Linear Models**. It is possible to use R to approach an "all subsets" result via exhaustive search for a logistic regression model, using, for instance, the `bestglm` or `glmulti` packages. There are problems with these approaches, and so I would not recommend you do this for Project 1, but I will try to pull together some materials about this for later in the term. If you want to select predictors in your logistic regression model, I suggest you focus on stepwise methods for Project 1.

