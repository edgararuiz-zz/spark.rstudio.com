# `sdf_partition`: Partition a Spark Dataframe

## Description


 Partition a Spark DataFrame into multiple groups. This routine is useful
 for splitting a DataFrame into, for example, training and test datasets.


## Usage

```r
sdf_partition(x, ..., weights = NULL, seed = sample(.Machine$integer.max,
  1))
```


## Arguments

Argument      |Description
------------- |----------------
```x```     |     An object coercable to a Spark DataFrame.
```...```     |     Named parameters, mapping table names to weights. The weights will be normalized such that they sum to 1.
```weights```     |     An alternate mechanism for supplying weights -- when specified, this takes precedence over the `...` arguments.
```seed```     |     Random seed to use for randomly partitioning the dataset. Set this if you want your partitioning to be reproducible on repeated runs.

## Details


 The sampling weights define the probability that a particular observation
 will be assigned to a particular partition, not the resulting size of the
 partition. This implies that partitioning a DataFrame with, for example,
 
 `sdf_partition(x, training = 0.5, test = 0.5)` 
 
 is not guaranteed to produce `training` and `test` partitions
 of equal size.


## Value


 An list()  `list` of `tbl_spark` s.


## Seealso


 Other Spark data frames: [`sdf_copy_to`](sdf_copy_to.html) ,
  [`sdf_predict`](sdf_predict.html) , [`sdf_register`](sdf_register.html) ,
  [`sdf_sample`](sdf_sample.html) , [`sdf_sort`](sdf_sort.html) 


## Examples

```r 
 list("\n", "# randomly partition data into a 'training' and 'test'\n", "# dataset, with 60% of the observations assigned to the\n", "# 'training' dataset, and 40% assigned to the 'test' dataset\n", "data(diamonds, package = \"ggplot2\")\n", "diamonds_tbl <- copy_to(sc, diamonds, \"diamonds\")\n", "partitions <- diamonds_tbl %>%\n", "  sdf_partition(training = 0.6, test = 0.4)\n", "print(partitions)\n", "\n", "# alternate way of specifying weights\n", "weights <- c(training = 0.6, test = 0.4)\n", 
    "diamonds_tbl %>% sdf_partition(weights = weights)\n") 
 ``` 

