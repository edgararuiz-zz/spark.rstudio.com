# `ml_logistic_regression`: Spark ML -- Logistic Regression

## Description


 Perform logistic regression on a Spark DataFrame.


## Usage

```r
ml_logistic_regression(x, response, features, intercept = TRUE, alpha = 0,
  lambda = 0, weights.column = NULL, iter.max = 100L,
  ml.options = ml_options(), ...)
```


## Arguments

Argument      |Description
------------- |----------------
```x```     |     An object coercable to a Spark DataFrame (typically, a `tbl_spark` ).
```response```     |     The name of the response vector (as a length-one character vector), or a formula, giving a symbolic description of the model to be fitted. When `response` is a formula, it is used in preference to other parameters to set the `response` , `features` , and `intercept`  parameters (if available). Currently, only simple linear combinations of existing parameters is supposed; e.g. `response ~ feature1 + feature2 + ...` . The intercept term can be omitted by using `- 1` in the model fit.
```features```     |     The name of features (terms) to use for the model fit.
```intercept```     |     Boolean; should the model be fit with an intercept term?
```alpha, lambda```     |     Parameters controlling loss function penalization (for e.g. lasso, elastic net, and ridge regression). See Details for more information.
```weights.column```     |     The name of the column to use as weights for the model fit.
```iter.max```     |     The maximum number of iterations to use.
```ml.options```     |     Optional arguments, used to affect the model generated. See [`ml_options`](ml_options.html) for more details.
```...```     |     Optional arguments. The `data` argument can be used to specify the data to be used when `x` is a formula; this allows calls of the form `ml_linear_regression(y ~ x, data = tbl)` , and is especially useful in conjunction with [`do`](do.html) .

## Details


 Spark implements for both $L1$ and $L2$ regularization in linear
 regression models. See the preamble in the
 [Spark Classification and Regression](http://spark.apache.org/docs/latest/ml-classification-regression.html) 
 documentation for more details on how the loss function is parameterized.
 
 In particular, with `alpha` set to 1, the parameterization
 is equivalent to a [lasso](https://en.wikipedia.org/wiki/Lasso_(statistics)) 
 model; if `alpha` is set to 0, the parameterization is equivalent to
 a [ridge regression](https://en.wikipedia.org/wiki/Tikhonov_regularization) model.


## Seealso


 Other Spark ML routines: [`ml_als_factorization`](ml_als_factorization.html) ,
  [`ml_decision_tree`](ml_decision_tree.html) ,
  [`ml_generalized_linear_regression`](ml_generalized_linear_regression.html) ,
  [`ml_gradient_boosted_trees`](ml_gradient_boosted_trees.html) ,
  [`ml_kmeans`](ml_kmeans.html) , [`ml_lda`](ml_lda.html) ,
  [`ml_linear_regression`](ml_linear_regression.html) ,
  [`ml_multilayer_perceptron`](ml_multilayer_perceptron.html) ,
  [`ml_naive_bayes`](ml_naive_bayes.html) ,
  [`ml_one_vs_rest`](ml_one_vs_rest.html) , [`ml_pca`](ml_pca.html) ,
  [`ml_random_forest`](ml_random_forest.html) ,
  [`ml_survival_regression`](ml_survival_regression.html) 


