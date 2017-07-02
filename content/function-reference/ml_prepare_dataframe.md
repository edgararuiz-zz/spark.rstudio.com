# `ml_prepare_dataframe`: Prepare a Spark DataFrame for Spark ML Routines

## Description


 This routine prepares a Spark DataFrame for use by Spark ML routines.


## Usage

```r
ml_prepare_dataframe(x, features, response = NULL, ...,
  ml.options = ml_options(), envir = new.env(parent = emptyenv()))
```


## Arguments

Argument      |Description
------------- |----------------
```x```     |     An object coercable to a Spark DataFrame (typically, a `tbl_spark` ).
```features```     |     The name of features (terms) to use for the model fit.
```response```     |     The name of the response vector (as a length-one character vector), or a formula, giving a symbolic description of the model to be fitted. When `response` is a formula, it is used in preference to other parameters to set the `response` , `features` , and `intercept`  parameters (if available). Currently, only simple linear combinations of existing parameters is supposed; e.g. `response ~ feature1 + feature2 + ...` . The intercept term can be omitted by using `- 1` in the model fit.
```...```     |     Optional arguments. The `data` argument can be used to specify the data to be used when `x` is a formula; this allows calls of the form `ml_linear_regression(y ~ x, data = tbl)` , and is especially useful in conjunction with [`do`](do.html) .
```ml.options```     |     Optional arguments, used to affect the model generated. See [`ml_options`](ml_options.html) for more details.
```envir```     |     An list() environment -- when supplied, it will be filled with metadata describing the transformations that have taken place.

## Details


 Spark DataFrames are prepared through the following transformations:
 
   

*  All specified columns are transformed into a numeric data type (using a simple cast for integer / logical columns, and  [`ft_string_indexer`](ft_string_indexer.html) for strings),  

*  The [`ft_vector_assembler`](ft_vector_assembler.html) is used to combine the specified features into a single 'feature' vector, suitable for use with Spark ML routines. 
 
 After calling this function, the `envir` environment (when supplied)
 will be populated with a set of variables:
 
 list(list("ll"), list("\n", list("features"), ":", list(), " The name of the generated ", list("features"), " vector.", list(), "\n", list("response"), ":", list(), " The name of the generated ", list("response"), " vector.", list(), "\n", list("labels"), ":  ", list(), " When the ", list("response"), " column is a string vector,\n", "                     the ", list(list("ft_string_indexer")), " is used to transform\n", "                     the vector into a [0:n) numeric vector. The ordered\n", 
    "                     labels are injected here to allow for easier mapping\n", "                     from the [0:n) values back to the original label.\n")) 


## Examples

```r 
 list("\n", "# example of how 'ml_prepare_dataframe' might be used to invoke\n", "# Spark's LinearRegression routine from the 'ml' package\n", "envir <- new.env(parent = emptyenv())\n", "tdf <- ml_prepare_dataframe(df, features, response, envir = envir)\n", "\n", "lr <- invoke_new(\n", "  sc,\n", "  \"org.apache.spark.ml.regression.LinearRegression\"\n", ")\n", "\n", "# use generated 'features', 'response' vector names in model fit\n", "model <- lr %>%\n", "  invoke(\"setFeaturesCol\", envir$features) %>%\n", 
    "  invoke(\"setLabelCol\", envir$response)\n") 
 ``` 

