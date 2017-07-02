# `spark_write_csv`: Write a Spark DataFrame to a CSV

## Description


 Write a Spark DataFrame to a tabular (typically, comma-separated) file.


## Usage

```r
spark_write_csv(x, path, header = TRUE, delimiter = ",", quote = "\"",
  escape = "\\", charset = "UTF-8", null_value = NULL,
  options = list(), mode = NULL, partition_by = NULL, ...)
```


## Arguments

Argument      |Description
------------- |----------------
```x```     |     A Spark DataFrame or dplyr operation
```path```     |     The path to the file. Needs to be accessible from the cluster. Supports the "hdfs://" , "s3n://" and "file://" protocols.
```header```     |     Should the first row of data be used as a header? Defaults to `TRUE` .
```delimiter```     |     The character used to delimit each column, defaults to `,` .
```quote```     |     The character used as a quote, defaults to `"hdfs://"` .
```escape```     |     The chatacter used to escape other characters, defaults to `\` .
```charset```     |     The character set, defaults to `"UTF-8"` .
```null_value```     |     The character to use for default values, defaults to `NULL` .
```options```     |     A list of strings with additional options.
```mode```     |     Specifies the behavior when data or table already exists.
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
  [`spark_write_json`](spark_write_json.html) ,
  [`spark_write_parquet`](spark_write_parquet.html) ,
  [`spark_write_table`](spark_write_table.html) 


