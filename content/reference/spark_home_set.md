# `spark_home_set`: Set the SPARK_HOME environment variable

## Description


 Set the `SPARK_HOME` environment variable. This slightly speeds up some
 operations, including the connection time.


## Usage

```r
spark_home_set(path = NULL, verbose = getOption("sparklyr.verbose",
  is.null(path)))
```


## Arguments

Argument      |Description
------------- |----------------
```path```     |     A string containing the path to the installation location of Spark. If `NULL` , the path to the most latest Spark/Hadoop versions is used.
```verbose```     |     Logical. Should the function explain what is it doing?

## Value


 The function is mostly invoked for the side-effect of setting the
 `SPARK_HOME` environment variable. It also returns `TRUE` if the
 environment was successfully set, and `FALSE` otherwise.


## Examples

```r 
 list("\n", "# Not run due to side-effects\n", "spark_home_set()\n") 
 ``` 

