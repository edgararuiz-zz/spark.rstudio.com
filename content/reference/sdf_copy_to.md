# `sdf_copy_to`: Copy an Object into Spark

## Description


 Copy an object into Spark, and return an list() object wrapping the
 copied object (typically, a Spark DataFrame).


## Usage

```r
sdf_copy_to(sc, x, name, memory, repartition, overwrite, ...)
sdf_import(x, sc, name, memory, repartition, overwrite, ...)
```


## Arguments

Argument      |Description
------------- |----------------
```sc```     |     The associated Spark connection.
```x```     |     An list() object from which a Spark DataFrame can be generated.
```name```     |     The name to assign to the copied table in Spark.
```memory```     |     Boolean; should the table be cached into memory?
```repartition```     |     The number of partitions to use when distributing the table across the Spark cluster. The default (0) can be used to avoid partitioning.
```overwrite```     |     Boolean; overwrite a pre-existing table with the name `name`  if one already exists?
```...```     |     Optional arguments, passed to implementing methods.

## Seealso


 Other Spark data frames: [`sdf_partition`](sdf_partition.html) ,
  [`sdf_predict`](sdf_predict.html) , [`sdf_register`](sdf_register.html) ,
  [`sdf_sample`](sdf_sample.html) , [`sdf_sort`](sdf_sort.html) 


## Examples

```r 
 
 sc <- spark_connect(master = "spark://HOST:PORT")
 sdf_copy_to(sc, iris)
 
 ``` 

