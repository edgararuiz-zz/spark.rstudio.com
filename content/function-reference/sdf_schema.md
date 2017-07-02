# `sdf_schema`: Read the Schema of a Spark DataFrame

## Description


 Read the schema of a Spark DataFrame.


## Usage

```r
sdf_schema(x)
```


## Arguments

Argument      |Description
------------- |----------------
```x```     |     An object coercable to a Spark DataFrame (typically, a `tbl_spark` ).

## Details


 The `type` column returned gives the string representation of the
 underlying Spark  type for that column; for example, a vector of numeric
 values would be returned with the type `"DoubleType"` . Please see the
 [Spark Scala API Documentation](http://spark.apache.org/docs/latest/api/scala/index.html#org.apache.spark.sql.types.package) 
 for information on what types are available and exposed by Spark.


## Value


 An list()  `list` , with each `list` element describing the
  `name` and `type` of a column.


