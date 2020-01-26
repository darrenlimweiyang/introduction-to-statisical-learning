# Chapter 2
---
## Outline

- F as an estimator
- Parametric and Non-parametric methods
- Binary decision between interpretability and accuracy
- Supervised vs Unsupervised
- Regression VS Classification
- MSE
- Bias Variance Tradeoff
---

#### F as an estimator
1. At the heart of statistical learning, we aim to find the function f which relates input and output. Unfortunately, we are unable to find the exact form - all we can do is to estimate a relationship based on training data.

#### Parametric and Non-parametric methods
- Parametric methods refers to making an assumption about the form of the function f. (eg. y = b0 + b1x1 + b2x2)
    - In essence, we assume a relationship already and only need to focus on determining the *values* of the parameters (eg. b1)


- For Non-parametric methods, we do not make any assumptions regarding the form. Instead, almost any form can be taken by the relationship between input and output.
    - The downside of non-parametric methods is that huge amounts of input data is required

#### interpretability and accuracy
Ultimately, statistical learning models face this issue of being either one. The reason for this is because as the accuracy of a model increases, the estimator f becomes more complicated, resulting in it becoming harder to interpret.

- Why would I ever select a less accurate model?
    -  This is heavily dependent on one's needs ie. if we prefer inference, then perhaps a more interpretable model is more suitable

One thing to note is that in some cases, a more flexible model will not result in an increase in accuracy. This is due to the possibility of a model overfitting, resulting in a decline in accuracy, when applied on the test set.


#### Supervised VS Unsupervised
In essence, supervised refers to have a target variable y while unsupervised refers to have no target variable y, instead trying to cluster data points and leveraging on logical inference.

Note that for unsupervised learning, it is impossible to visually cluster data points with more than 3 parameters. Instead, automated tools to conduct *cluster analysis* exists.

---

#### Regression VS Classification
- Regression refers to predicting a continuous variable
- Classification refers to predicting a class variable

For input data, it is less important on whether they are continuous, class, or a mixture of both

#### MSE (Mean Squared Error)

MSE = (1/n) * (Σ (y<sub>i</sub> - f(x<sub>i</sub>)) ** 2)

The intuition behind MSE is simply the squared difference of predicted and actual observations, averaged. This generates a value which captures the average squared error.

However, it is important to note that we should aim to focus on the test MSE, and not training MSE as a metric for evaluating models.

- The relationship between test MSE and model flexibility
    - Generally, as model flexibility rises, test MSE declines. However, at a certain point, test MSE begins rising despite continued rise in model flexibility.
    - The reason for this is *overfitting*. Basically, at a certain point, the model becomes too flexible - beginning to account for noise in the training data.
    - So even when training MSE is decreasing, test MSE begins increase.

#### Bias Variance Tradeoff

- What is Bias
    - Bias refers to the error introduced when we attempt to introduce a mathematical relationship to model a real-life situation
    - Eg. Wages and experience are not merely a linear relationship (eg. soft skills) but that is what we aim to do, resulting in bias

- What is Variance
    - Variance refers to the magnitude of which fhat willl change, if a different training dataset is used
    - How specific this relationship is to this one training set

**What is the tradeoff that occurs?**
The tradeoff is that in general, a fall in variance leads to a rise in bias, and vice versa. Achieving a balance between the two is key.

How does it work
- At the start, when we raise the flexibility of a model, the bias decreases - because our fhat gets more complicated and slowly begins to be able to model the actual relationship.
- variance begins to increase slightly - as our model becomes increasingly dataset-specific
    - However, the fall in bias > rise in variance. Hence we continue raising the flexibility of the model

At a certain point, the rate at which bias falls < rate at which variance rises, resulting in overall test MSE rising again. This is when we should stop raising flexibility of the model.
