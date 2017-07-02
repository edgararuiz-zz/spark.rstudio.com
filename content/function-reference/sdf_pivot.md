# `sdf_pivot`: Pivot a Spark DataFrame

## Description


 Construct a pivot table over a Spark Dataframe, using a syntax similar to
 that from `reshape2::dcast` .


## Usage

```r
sdf_pivot(x, formula, fun.aggregate = "count")
```


## Arguments

Argument      |Description
------------- |----------------
```x```     |     An object coercable to a Spark DataFrame (typically, a `tbl_spark` ).
```formula```     |     A two-sided list() formula of the form `x_1 + x_2 + ... ~ y_1` . The left-hand side of the formula indicates which variables are used for grouping, and the right-hand side indicates which variable is used for pivoting. Currently, only a single pivot column is supported.
```fun.aggregate```     |     How should the grouped dataset be aggregated? Can be a length-one character vector, giving the name of a Spark aggregation function to be called; a named list() list mapping column names to an aggregation method, or an list() function that is invoked on the grouped dataset.

