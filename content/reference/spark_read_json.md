# `spark_read_json`: Read a JSON file into a Spark DataFrame

## Description


 Read a table serialized in the c("[JavaScript\n](http://www.json.org/)", "[Object Notation](http://www.json.org/)") format into a Spark DataFrame.


## Usage

```r
spark_read_json(sc, name, path, options = list(), repartition = 0,
  memory = TRUE, overwrite = TRUE)
```


## Arguments

Argument      |Description
------------- |----------------
```sc```     |     A `spark_connection` .
```name```     |     The name to assign to the newly generated table.
```path```     |     The path to the file. Needs to be accessible from the cluster. Supports the "hdfs://" , "s3n://" and "file://" protocols.
```options```     |     A list of strings with additional options.
```repartition```     |     The number of partitions used to distribute the generated table. Use 0 (the default) to avoid partitioning.
```memory```     |     Boolean; should the data be loaded eagerly into memory? (That is, should the table be cached?)
```overwrite```     |     Boolean; overwrite the table with the given name if it already exists?

## Details


 You can read data from HDFS ( `hdfs://` ), S3 ( `s3n://` ), as well as
 the local file system ( `file://` ).
 
 If you are reading from a secure S3 bucket be sure that the `AWS_ACCESS_KEY_ID` and
  `AWS_SECRET_ACCESS_KEY` environment variables are both defined.


## Seealso


 Other Spark serialization routines: [`spark_load_table`](spark_load_table.html) ,
  [`spark_read_csv`](spark_read_csv.html) ,
  [`spark_read_jdbc`](spark_read_jdbc.html) ,
  [`spark_read_parquet`](spark_read_parquet.html) ,
  [`spark_read_source`](spark_read_source.html) ,
  [`spark_read_table`](spark_read_table.html) ,
  [`spark_save_table`](spark_save_table.html) ,
  [`spark_write_csv`](spark_write_csv.html) ,
  [`spark_write_json`](spark_write_json.html) ,
  [`spark_write_parquet`](spark_write_parquet.html) ,
  [`spark_write_table`](spark_write_table.html) 


