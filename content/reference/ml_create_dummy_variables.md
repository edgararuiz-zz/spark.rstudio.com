# `ml_create_dummy_variables`: Create Dummy Variables

## Description


 Given a column in a Spark DataFrame, generate a new Spark DataFrame
 containing dummy variable columns.


## Usage

```r
ml_create_dummy_variables(x, input, reference = NULL, levels = NULL,
  labels = NULL, envir = new.env(parent = emptyenv()))
```


## Arguments

Argument      |Description
------------- |----------------
```x```     |     An object coercable to a Spark DataFrame (typically, a `tbl_spark` ).
```input```     |     The name of the input column.
```reference```     |     The reference label. This variable is omitted when generating dummy variables (to avoid perfect multi-collinearity if all dummy variables were to be used in the model fit); to generate dummy variables for all columns this can be explicitly set as `NULL` .
```levels```     |     The set of levels for which dummy variables should be generated. By default, constructs one variable for each unique value occurring in the column specified by `input` .
```labels```     |     An optional list() list, mapping values in the `input`  column to column names to be assigned to the associated dummy variable.
```envir```     |     An optional list() environment; when provided, it will be filled with useful auxiliary information. See list("Auxiliary Information") for more information.

## Details


 The dummy variables are generated in a similar mechanism to
 [`model.matrix`](model.matrix.html) , where categorical variables are expanded into a
 set of binary (dummy) variables. These dummy variables can be used for
 regression of categorical variables within the various regression routines
 provided by `sparklyr` .


