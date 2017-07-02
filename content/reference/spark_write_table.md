# `spark_write_table`: Writes a Spark DataFrame into a Spark table

## Description


 Writes a Spark DataFrame into a Spark table.


## Usage

```r
spark_write_table(x, name, mode = NULL, options = list(),
  partition_by = NULL, ...)
```


## Arguments

Argument      |Description
------------- |----------------
```x```     |     A Spark DataFrame or dplyr operation
```name```     |     The name to assign to the newly generated table.
```mode```     |     Specifies the behavior when data or table already exists.
```options```     |     A list of strings with additional options.
```partition_by```     |     Partitions the output by the given columns on the file system.
```...```     |     Optional arguments; currently unused.

## Seealso


 Other Spark serialization routines: [`spark_load_table`](spark_load_table.html) ,
  [`spark_read_csv`](spark_read_csv.html) ,
  [`spark_read_jdbc`](spark_read_jdbc.html) ,
  [`spark_read_json`](spark_read_json.html) ,
  [`spark_read_parquet`](spark_read_parquet.html) ,
  [`spark_read_source`](spark_read_source.html) ,
  [`spark_read_table`](spark_read_table.html) ,
  [`spark_save_table`](spark_save_table.html) ,
  [`spark_write_csv`](spark_write_csv.html) ,
  [`spark_write_json`](spark_write_json.html) ,
  [`spark_write_parquet`](spark_write_parquet.html) 


