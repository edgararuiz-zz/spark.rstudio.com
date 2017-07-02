# `ml_options`: Options for Spark ML Routines

## Description


 Provide this object to the various Spark ML methods, to control certain
 facets of the model outputs produced.


## Usage

```r
ml_options(id.column = random_string("id"),
  response.column = random_string("response"),
  features.column = random_string("features"), model.transform = NULL,
  only.model = FALSE, na.action = getOption("na.action", "na.omit"), ...)
```


## Arguments

Argument      |Description
------------- |----------------
```id.column```     |     The name to assign to the generated id column.
```response.column```     |     The name to assign to the generated response column.
```features.column```     |     The name to assign to the generated features column.
```model.transform```     |     An optional list() function that accepts a Spark model and returns a Spark model. This can be used to supply optional Spark model fitting parameters not made available in the `sparklyr` APIs.
```only.model```     |     Boolean; should the Spark model object itself be returned without fitting the actual model? Useful for [`ml_one_vs_rest`](ml_one_vs_rest.html) .
```na.action```     |     An list() function, or the name of an list() function, indicating how missing values should be handled.
```...```     |     Optional arguments, reserved for future expansion.

