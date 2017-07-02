# `ml_decision_tree`: Spark ML -- Decision Trees

## Description


 Perform regression or classification using decision trees.


## Usage

```r
ml_decision_tree(x, response, features, max.bins = 32L, max.depth = 5L,
  type = c("auto", "regression", "classification"),
  ml.options = ml_options(), ...)
```


## Arguments

Argument      |Description
------------- |----------------
```x```     |     An object coercable to a Spark DataFrame (typically, a `tbl_spark` ).
```response```     |     The name of the response vector (as a length-one character vector), or a formula, giving a symbolic description of the model to be fitted. When `response` is a formula, it is used in preference to other parameters to set the `response` , `features` , and `intercept`  parameters (if available). Currently, only simple linear combinations of existing parameters is supposed; e.g. `response ~ feature1 + feature2 + ...` . The intercept term can be omitted by using `- 1` in the model fit.
```features```     |     The name of features (terms) to use for the model fit.
```max.bins```     |     The maximum number of bins used for discretizing continuous features and for choosing how to split on features at each node. More bins give higher granularity.
```max.depth```     |     Maximum depth of the tree (>= 0); that is, the maximum number of nodes separating any leaves from the root of the tree.
```type```     |     The type of model to fit. `"regression"` treats the response as a continuous variable, while `"classification"` treats the response as a categorical variable. When `"auto"` is used, the model type is inferred based on the response variable type -- if it is a numeric type, then regression is used; classification otherwise.
```ml.options```     |     Optional arguments, used to affect the model generated. See [`ml_options`](ml_options.html) for more details.
```...```     |     Optional arguments. The `data` argument can be used to specify the data to be used when `x` is a formula; this allows calls of the form `ml_linear_regression(y ~ x, data = tbl)` , and is especially useful in conjunction with [`do`](do.html) .

## Seealso


 Other Spark ML routines: [`ml_als_factorization`](ml_als_factorization.html) ,
  [`ml_generalized_linear_regression`](ml_generalized_linear_regression.html) ,
  [`ml_gradient_boosted_trees`](ml_gradient_boosted_trees.html) ,
  [`ml_kmeans`](ml_kmeans.html) , [`ml_lda`](ml_lda.html) ,
  [`ml_linear_regression`](ml_linear_regression.html) ,
  [`ml_logistic_regression`](ml_logistic_regression.html) ,
  [`ml_multilayer_perceptron`](ml_multilayer_perceptron.html) ,
  [`ml_naive_bayes`](ml_naive_bayes.html) ,
  [`ml_one_vs_rest`](ml_one_vs_rest.html) , [`ml_pca`](ml_pca.html) ,
  [`ml_random_forest`](ml_random_forest.html) ,
  [`ml_survival_regression`](ml_survival_regression.html) 


