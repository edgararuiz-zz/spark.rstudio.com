# `sdf_register`: Register a Spark DataFrame

## Description


 Registers a Spark DataFrame (giving it a table name for the
 Spark SQL context), and returns a `tbl_spark` .


## Usage

```r
sdf_register(x, name = NULL)
```


## Arguments

Argument      |Description
------------- |----------------
```x```     |     A Spark DataFrame.
```name```     |     A name to assign this table.

## Seealso


 Other Spark data frames: [`sdf_copy_to`](sdf_copy_to.html) ,
  [`sdf_partition`](sdf_partition.html) , [`sdf_predict`](sdf_predict.html) ,
  [`sdf_sample`](sdf_sample.html) , [`sdf_sort`](sdf_sort.html) 


