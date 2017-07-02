# `sdf_predict`: Model Predictions with Spark DataFrames

## Description


 Given a `ml_model` fit alongside a new data set, produce a new Spark
 DataFrame with predicted values encoded in the `"prediction"` column.


## Usage

```r
sdf_predict(object, newdata, ...)
```


## Arguments

Argument      |Description
------------- |----------------
```object, newdata```     |     An object coercable to a Spark DataFrame.
```...```     |     Optional arguments; currently unused.

## Seealso


 Other Spark data frames: [`sdf_copy_to`](sdf_copy_to.html) ,
  [`sdf_partition`](sdf_partition.html) , [`sdf_register`](sdf_register.html) ,
  [`sdf_sample`](sdf_sample.html) , [`sdf_sort`](sdf_sort.html) 


