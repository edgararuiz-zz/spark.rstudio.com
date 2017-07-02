# `ml_naive_bayes`: Spark ML -- Naive-Bayes

## Description


 Perform regression or classification using naive bayes.


## Usage

```r
ml_naive_bayes(x, response, features, lambda = 0, ml.options = ml_options(),
  ...)
```


## Arguments

Argument      |Description
------------- |----------------
```x```     |     An object coercable to a Spark DataFrame (typically, a `tbl_spark` ).
```response```     |     The name of the response vector (as a length-one character vector), or a formula, giving a symbolic description of the model to be fitted. When `response` is a formula, it is used in preference to other parameters to set the `response` , `features` , and `intercept`  parameters (if available). Currently, only simple linear combinations of existing parameters is supposed; e.g. `response ~ feature1 + feature2 + ...` . The intercept term can be omitted by using `- 1` in the model fit.
```features```     |     The name of features (terms) to use for the model fit.
```lambda```     |     The (Laplace) smoothing parameter. Defaults to zero.
```ml.options```     |     Optional arguments, used to affect the model generated. See [`ml_options`](ml_options.html) for more details.
```...```     |     Optional arguments. The `data` argument can be used to specify the data to be used when `x` is a formula; this allows calls of the form `ml_linear_regression(y ~ x, data = tbl)` , and is especially useful in conjunction with [`do`](do.html) .

## Seealso


 Other Spark ML routines: [`ml_als_factorization`](ml_als_factorization.html) ,
  [`ml_decision_tree`](ml_decision_tree.html) ,
  [`ml_generalized_linear_regression`](ml_generalized_linear_regression.html) ,
  [`ml_gradient_boosted_trees`](ml_gradient_boosted_trees.html) ,
  [`ml_kmeans`](ml_kmeans.html) , [`ml_lda`](ml_lda.html) ,
  [`ml_linear_regression`](ml_linear_regression.html) ,
  [`ml_logistic_regression`](ml_logistic_regression.html) ,
  [`ml_multilayer_perceptron`](ml_multilayer_perceptron.html) ,
  [`ml_one_vs_rest`](ml_one_vs_rest.html) , [`ml_pca`](ml_pca.html) ,
  [`ml_random_forest`](ml_random_forest.html) ,
  [`ml_survival_regression`](ml_survival_regression.html) 


