# `ml_pca`: Spark ML -- Principal Components Analysis

## Description


 Perform principal components analysis on a Spark DataFrame.


## Usage

```r
ml_pca(x, features = tbl_vars(x), ml.options = ml_options(), ...)
```


## Arguments

Argument      |Description
------------- |----------------
```x```     |     An object coercable to a Spark DataFrame (typically, a `tbl_spark` ).
```features```     |     The columns to use in the principal components analysis. Defaults to all columns in `x` .
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
  [`ml_naive_bayes`](ml_naive_bayes.html) ,
  [`ml_one_vs_rest`](ml_one_vs_rest.html) ,
  [`ml_random_forest`](ml_random_forest.html) ,
  [`ml_survival_regression`](ml_survival_regression.html) 


