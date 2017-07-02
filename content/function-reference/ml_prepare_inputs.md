# `ml_prepare_response_features_intercept`: Pre-process the Inputs to a Spark ML Routine

## Description


 Pre-process / normalize the inputs typically passed to a
 Spark ML routine.


## Usage

```r
ml_prepare_response_features_intercept(x = NULL, response, features,
  intercept, envir = parent.frame(),
  categorical.transformations = new.env(parent = emptyenv()),
  ml.options = ml_options())
ml_prepare_features(x, features, envir = parent.frame(),
  ml.options = ml_options())
```


## Arguments

Argument      |Description
------------- |----------------
```x```     |     An object coercable to a Spark DataFrame (typically, a `tbl_spark` ).
```response```     |     The name of the response vector (as a length-one character vector), or a formula, giving a symbolic description of the model to be fitted. When `response` is a formula, it is used in preference to other parameters to set the `response` , `features` , and `intercept`  parameters (if available). Currently, only simple linear combinations of existing parameters is supposed; e.g. `response ~ feature1 + feature2 + ...` . The intercept term can be omitted by using `- 1` in the model fit.
```features```     |     The name of features (terms) to use for the model fit.
```intercept```     |     Boolean; should the model be fit with an intercept term?
```envir```     |     The list() environment in which the `response` , `features`  and `intercept` bindings should be mutated. (Typically, the parent frame).
```categorical.transformations```     |     An list() environment used to record what categorical variables were binarized in this procedure. Categorical variables that included in the model formula will be transformed into binary variables, and the generated mappings will be stored in this environment.
```ml.options```     |     Optional arguments, used to affect the model generated. See [`ml_options`](ml_options.html) for more details.

## Details


 Pre-processing of these inputs typically involves:
 
  

*  Handling the case where `response` is itself a formula describing the model to be fit, thereby extracting the names of the `response` and `features` to be used, 

*  Splitting categorical features into dummy variables (so they can easily be accommodated + specified in the underlying Spark ML model fit), 

*  Mutating the associated variables in the specified environment . 
 
 Please take heed of the last point, as while this is useful in practice,
 the behavior will be very surprising if you are not expecting it.


## Examples

```r 
 list("\n", "# note that ml_prepare_features, by default, mutates the 'features'\n", "# binding in the same environment in which the function was called\n", "local({\n", "   ml_prepare_features(features = ~ x1 + x2 + x3)\n", "   print(features) # c(\"x1\", \"x2\", \"x3\")\n", "})\n") 
 ``` 

