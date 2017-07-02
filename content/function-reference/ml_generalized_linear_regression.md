# `ml_generalized_linear_regression`: Spark ML -- Generalized Linear Regression

## Description


 Perform generalized linear regression on a Spark DataFrame.


## Usage

```r
ml_generalized_linear_regression(x, response, features, intercept = TRUE,
  family = gaussian(link = "identity"), weights.column = NULL,
  iter.max = 100L, ml.options = ml_options(), ...)
```


## Arguments

Argument      |Description
------------- |----------------
```x```     |     An object coercable to a Spark DataFrame (typically, a `tbl_spark` ).
```response```     |     The name of the response vector (as a length-one character vector), or a formula, giving a symbolic description of the model to be fitted. When `response` is a formula, it is used in preference to other parameters to set the `response` , `features` , and `intercept`  parameters (if available). Currently, only simple linear combinations of existing parameters is supposed; e.g. `response ~ feature1 + feature2 + ...` . The intercept term can be omitted by using `- 1` in the model fit.
```features```     |     The name of features (terms) to use for the model fit.
```intercept```     |     Boolean; should the model be fit with an intercept term?
```family```     |     The family / link function to use; analogous to those normally passed in to calls to list() 's own [`glm`](glm.html) .
```weights.column```     |     The name of the column to use as weights for the model fit.
```iter.max```     |     The maximum number of iterations to use.
```ml.options```     |     Optional arguments, used to affect the model generated. See [`ml_options`](ml_options.html) for more details.
```...```     |     Optional arguments. The `data` argument can be used to specify the data to be used when `x` is a formula; this allows calls of the form `ml_linear_regression(y ~ x, data = tbl)` , and is especially useful in conjunction with [`do`](do.html) .

## Details


 In contrast to [`ml_linear_regression`](ml_linear_regression.html) and
 [`ml_logistic_regression`](ml_logistic_regression.html) , these routines do not allow you to
 tweak the loss function (e.g. for elastic net regression); however, the model
 fits returned by this routine are generally richer in regards to information
 provided for assessing the quality of fit.


## Seealso


 Other Spark ML routines: [`ml_als_factorization`](ml_als_factorization.html) ,
  [`ml_decision_tree`](ml_decision_tree.html) ,
  [`ml_gradient_boosted_trees`](ml_gradient_boosted_trees.html) ,
  [`ml_kmeans`](ml_kmeans.html) , [`ml_lda`](ml_lda.html) ,
  [`ml_linear_regression`](ml_linear_regression.html) ,
  [`ml_logistic_regression`](ml_logistic_regression.html) ,
  [`ml_multilayer_perceptron`](ml_multilayer_perceptron.html) ,
  [`ml_naive_bayes`](ml_naive_bayes.html) ,
  [`ml_one_vs_rest`](ml_one_vs_rest.html) , [`ml_pca`](ml_pca.html) ,
  [`ml_random_forest`](ml_random_forest.html) ,
  [`ml_survival_regression`](ml_survival_regression.html) 


