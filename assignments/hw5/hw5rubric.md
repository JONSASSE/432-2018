# Assignment 5 Rubric

# Question 1 (25 points)

Award 25 points for an essay that is:

1. focused and responsive to all parts of the prompt
2. says something interesting and thoughtful about the topic
3. is completely clear to you as a reader
4. contains an actual example from the writer's experience that helps explain their idea
5. contains no typographical, syntax or grammar errors
6. 5-12 sentences long

- If an essay fails to meet standard 1, 2, 3, or 4, it should lose 
    + lose 5 points for each such standard that is badly missed (for instance, there is no focus to the essay, or the whole thing is unclear.)
    + lose 3 points for each standard that is partially missed (for instance, a part of the essay is unclear, but most of it is clear, or if part of the prompt is not well covered by the response.)
- Deduct 4 points if the essay is less than 5 sentences long, or 1 point for each sentence beyond 12.
- Deduct a point for any minor errors in English, and 2-3 points for more egregious errors.

Most students should receive scores between 16 and 20, likely losing points related to clarity, focus or including a meaningful example. I expect no more than 4-5 essays will meet the "25" standard.

TAs, please provide brief comments indicating strong/weak points on **all** essays. Thank you.

# Question 2 (5 points)

- 5 points for answering 1570 subjects. No partial credit, but the TAs will try to figure out why you gave a different answer if you did.

# Question 3 (10 points)

- Award 7 points for creating a correct 2 by 2 table, including ordering the table levels properly. Award 5 points if they have the right data and label it correctly, but set up the wrong odds ratio because they have Male above Female or No to the left of Yes. Award no more than 3 points for an actually incorrect table, where the labels don't match the actual values.
- Award 3 additional points for concluding that the cross-product odds ratio is 1.288, with 95% CI (0.990, 1.676), and two decimal places is sufficient.
- If they fail to create the correct table because they have, for instance, males above females, but get the odds ratio and confidence interval right anyway, award 8/10 points.

# Question 4 (5 points)

For Questions 4-9, the student answers will depend on how they impute the missing `INDFMPIR` data. So you need to allow for that a bit in looking at the coefficients and standard errors.

- Award 4 points for creating the correct model.
    - This means that they predicted the log odds of whether the subject HAD ever been told they had asthma, and not the opposite of that. If they predict the opposite, but otherwise do things correctly, award 2 points
    - This also means that have included all four predictors in a sensible way. If they included binary pieces other than 1/0, ok, but that may cause trouble later.
    - If they forgot to run a logistic regression model, perhaps by leaving off family = binomial in a `glm`, then they get no more than 1 point for this piece.
- Award an additional point for correctly specifying their equation, given their model, even if there is a problem with that model.
- Note that the students do not need to provide any sanity checks or summary looks at the data before and after cleaning, but they do need to have specified how they created their data, especially if variables other than the original ones are (as they should be) used in the model.

# Question 5 (10 points)

- 3 points for specifying the odds ratio correctly given their model.
- An additional 3 points for specifying the confidence interval correctly. 
- An additional 4 points for interpreting the value of the odds ratio in terms of what it actually means. A partially correct interpretation should score no more than 2 points in this section.

I expect most of the trouble to be in the interpretation.

# Question 6 (10 points)

- 10 points for an accurate conclusion about the odds ratios and that each of them indicates no statistically significant effect (assuming that's right for their choice of imputation procedure.)
- No more than 5 points on this question if they aren't correct about what their models imply, or if they don't interpret the result appropriately.

# Question 7 (10 points)

- 4 points for estimating the odds ratio and confidence interval correctly given their choice of model.
- An additional 6 points for interpreting the value of the odds ratio in terms of what it actually means. A partially correct interpretation should score no more than 2 points in this section. I don't care if they use the words "statistically significant" here or not. I do care that they explain what the value is actually referring to, as indicated below:
    - If they used `lrm` they need to express the effect and interval in terms of a move from 4 to 7 (25th to 75th percentile) and not just a move of a single point. If they blow this, then they should get no more than 6/10 on Question 7.
    - If they used `glm`, then the opposite is the case. The odds ratio they get from `exp(coef(model))` describes the odds ratio associated with a 1-day change. If they blow this, then they should get no more than 6/10 on Question 7.

# Question 8 (10 points)

- 10 points for a correct response, given their model.
- No more than 5 points for a response that does not match their model, or isn't calculated correctly, or if their model isn't actually predicting the probability of asthma.

# Question 9 (15 points)

- 8 points for creating two models (one with and one without the interaction term.) 
    - No more than 4/8 on this piece if the models don't correctly create a variable to indicate non-Hispanic White subjects.
- 5 more points for an appropriate comparison of those models, by any of these approaches:
    - a direct look at the coefficient for the product term and its significance
    - an analysis of deviance based comparison of the two models with `anova`
    - a comparison of the AIC and BIC values
    - no more than 2/5 if they don't specify the meaning of the comparison in English (because this is not significant, we can conclude ... or because the AIC is smaller in this model, we can conclude ... is what we want to see.)
- 3 points for specifying the logistic regression equation, including specifying the outcome (log odds of asthma), correctly, given their imputation approach.

# Lateness

The sketch will be posted by 1:10 PM on 2018-03-02. Students turning in the assignment after 2 PM on 2018-03-02 will lose 20 points from their total. TAs shouldn't reduce points, Dr. Love will do that - simply specify that the student turned in the assignment after 2 PM in the comments field in the grading spreadsheet.
