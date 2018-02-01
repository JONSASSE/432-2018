# 432 Class 07: 2018-02-06

### Key Materials

[The slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class07) and the [audio files](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class07) will be posted as soon as they are available.

In today's class, we'll discuss the incorporation of non-linear terms in a linear regression model. 

## Announcements Before Class 07

1. I've made some meaningful edits to Section 8 of the Course Notes, and I'll be streamlining and amplifying that some more after HW 2 is complete. In particular, I added some material in a section 8.3.2 (and at the end of 8.3.1) to clarify the calculation of *uncorrected* AIC, and how it (a) differs from bias-corrected AIC, (b) provides no new information beyond what we get from Mallows' Cp in the linear regression setting, and so we don't plot it and (c) is only defined up to an additive constant, so `extractAIC` and `AIC` give different results when applied to a single model, but when comparing two models, either can be used.
