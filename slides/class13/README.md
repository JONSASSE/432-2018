# 432 Class 13: 2018-02-27

### Key Materials

- [The slides](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class13) above cover ridge regression and the lasso.
- The [audio files](https://github.com/THOMASELOVE/432-2018/tree/master/slides/class13) will be posted as soon as they are available.

In today's class, we'll discuss ridge regression and the lasso, amplifying on what you'll find in [Chapter 11 of the Course Notes](https://thomaselove.github.io/432-notes/other-variable-selection-strategies.html).

## Announcements Before Class 13

1. [Answer Sketch and Grading Rubric](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw4) are up for Assignment 4.

2. [Assignment 5](https://github.com/THOMASELOVE/432-2018/tree/master/assignments/hw5) is due this Friday, 2018-03-02 at 1 PM.

3. Quiz 1 will be made available to you by noon on Friday 2018-03-02. It is due at noon on Monday 2018-03-05.

4. `lrm` and `ols` and `rms` functions in general, are usually looking for categorical data to be included using **numerical codes**. 
    - If, for instance, you try to do something after you've included a sex variable that has the values M/F, rather than something like female = 1/0, you may get error messages like **Error: Can't use matrix or array for column indexing**. That's an indication that R is looking for a numeric variable and not finding it for some categorical data. 
    - This comes up, for instance, when plotting an ROC curve from an `rms`-based fit. But it's not an issue with `glm` or `lm`. Just another reason to know both approaches.

## Project Proposals

1. All Project 1 Proposals have been reviewed by Dr. Love. 
    + If your grade on Canvas is 10/10, you're done.
    + If it isn't 10/10, you need to fix the issues I described in my note on [Canvas](https://canvas.case.edu/), and resubmit.

Here is the current list of accepted proposals. As of 10:45 PM on 2018-02-23, 23 of 41 are accepted.

Name | Project 1 Title
-----------------------------: | -------------------------------------------------------------
Khaled Alayed	| Bug Prediction Using Code Metrics
Haimeng Bai	| Regression Statistical Analysis of NBA Final Champions
Laura Baldassari |	The Effect of Smoking on Vitamin B12 Deficiency
Estee Cramer |	Prediction Models for Extramarital Affairs
Abhishek Deshpande |	Effect of Intravenous Fat Emulsions on Outcomes in Critically Ill Patients
Katherine Dobbs |	Perinatal HIV exposure and child health in the first 24 months of life
Gwendolyn Donley |	Predicting Outpatient Visits and Self-Reported Physical Limitation
Dongze He	| Predicting duration and result of endovascular aortic repair opeartion by disease history and physical indexes.
Ryan Honomichl |	The Role of Problem- and Emotion-Focused Coping in the Prediction of Blood Pressure and Hypertension
Maher Kazimi |	Would health insurance keep your sugar controlled?
Nikolas Krieger |	Predicting Child Povery and Home Ownership in Counties of the Western Continental United States
Carli Lehr |	Pleural Effusions After Lung Transplant and Their Relationship to Acute Cellular Rejection
Kedar Mahajan |	What makes you sad or cognitively impaired?
John McDonnell |	#PureEmotion
Elina Misicka	| Transition of Multiple Sclerosis Patients from Relapsing-Remitting to Secondary Progressive Disease
Haeun Park	| It’s all about women’s hormones
Sarah Planchon Pope	| Effect of Physical, Social, and Economic Factors on Obesity
Kaylee Sarna |	Income Level and how it predicts systolic blood pressure in African Americans Age 25 and older
Sandra Silva Camargo |	Predicting mortality after a prostate cancer diagnosis
Andrew Tang	| Repair, Reconstruct, or Resect: The Fate of the Perforated Esophagus
Sneha Vakamudi	| Does Anticoagulation Prevent Thrombus Formation in Cardiac Amyloidosis?
Frances Wang	| Predicting Development and Time to Onset of Depression in Multiple Sclerosis Patients
Ruipeng Wei	| Relationships in Body Dimensions
