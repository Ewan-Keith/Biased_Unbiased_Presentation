---
title       : When Biased Statistical Models Beat Unbiased
subtitle    : 
author      : Ewan Keith
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : mathjax       # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

<style type='text/css'>
img {
    max-height: 560px;
    max-width: 964px;
}
</style>

## When do Biased Models Beat Unbiased?

>* Always
>* ish...

--- .class #id 

## What does 'Beat' mean here?

>* more accurate out of sample prediction.
>* fairly uncontroversial measure of performance.

---

## What does Bias mean in this context?

$$\operatorname{Bias}_\theta[\,\hat\theta\,] = \operatorname{E}_\theta[\,\hat{\theta}\,]-\theta$$

>* Technical statistical definition.
>* *Not* the colloquial definition.
>* Fairly abstract, but underlies a lot of commonly used estimates/models
>* Sample mean, Sample Median, (generalised) linear regression, ANOVA, and more hinge on un-biased estimates.

---

## Why would we bias our estimates?

>* Generally to help deal with excess variance in our estimates.
>* Why not...

--- 

## Regularisation

>* Very large number of predictor variables can cause difficulties.
>* Multiple Comparisons risk unreliable hypothesis tests
>* Complete failure in P > N cases
>* Often increases the risks of co-linearity

--- 

## Regularisation

* Regularisation simply involves adding some penalty on model complexity.
* This can be achieved in various ways, below is an example of the function used to fit a LASSO regression. An upper limit is set on all regression coeficients, limiting complexity.

$$\min_{ \beta_0, \beta } \left\{ \frac{1}{N} \sum_{i=1}^N (y_i - \beta_0 - x_i^T \beta)^2 \right\} \text{ subject to } \sum_{j=1}^p |\beta_j| \leq t.$$

* This shrinks (biases) estimates towards zero, how much bias is introduced is decided using cross-validation.

---

## Regularisation

* What's this look like?



<img src="assets/fig/unnamed-chunk-2-1.png" title="plot of chunk unnamed-chunk-2" alt="plot of chunk unnamed-chunk-2"  />


---

## Regularisation is very useful
>* Efficient variable selection in high dimensions
>* Enables treatment of poorly posed problems
>* As a general rule, provides better fit

---

## When to use regularisation?

>* When there are a large number of predictor variables to be modelled.
>* When the problem is poorly posed; due to multicolinearity, more variables than observations, hard to interpret output, etc.

---

## Hierarchical Modelling

![pooled](pooled sleep.png)

---

## Hierarchical Modelling

![facet](sleep facet.png)

---

## Hierarchical Modelling

>* Halfway between complete pooling and no-pooling.
>* Weighted average between the two.
>* Results in biased, ‘half-way’ estimates.
>* Typically provides better prediction of future data than unbiased estimates.

---

## Hierarchical Modelling

![batting](batting.png)

---

## When to use Hierarchical Modelling

>* When there are a number of groups you wish to measure the same property over, but you've a limited sample size.
>* Particularly when groups are very smallin size.
>* When you have multi-levelled data, e.g. pupils, within classes, within schools, within counties, within...

---

![mrp](mrp.png)


---

## How to use regularisation and hierarchical modelling

>* lots of software now includes these tools.
>* SPSS, SAS, STATA, Pyton.
>* Personally recommend R.










