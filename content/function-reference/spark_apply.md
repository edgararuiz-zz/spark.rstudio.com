# `spark_apply`: Apply a Function in Spark

## Description


 Applies a function to a Spark object (typically, a Spark DataFrame).


## Usage

```r
spark_apply(x, f, names = colnames(x), memory = TRUE, ...)
```


## Arguments

Argument      |Description
------------- |----------------
```x```     |     An object (usually a `spark_tbl` ) coercable to a Spark DataFrame.
```f```     |     A function that transforms a data frame partition into a data frame.
```names```     |     The column names for the transformed object, defaults to the names from the original object.
```memory```     |     Boolean; should the table be cached into memory?
```...```     |     Optional arguments; currently unused.

