# `spark_read_csv`: Read a CSV file into a Spark DataFrame

## Description


 Read a tabular data file into a Spark DataFrame.


## Usage

```r
spark_read_csv(sc, name, path, header = TRUE, columns = NULL,
  infer_schema = TRUE, delimiter = ",", quote = "\"", escape = "\\",
  charset = "UTF-8", null_value = NULL, options = list(),
  repartition = 0, memory = TRUE, overwrite = TRUE)
```


## Arguments

Argument      |Description
------------- |----------------
```sc```     |     A `spark_connection` .
```name```     |     The name to assign to the newly generated table.
```path```     |     The path to the file. Needs to be accessible from the cluster. Supports the "hdfs://" , "s3n://" and "file://" protocols.
```header```     |     Boolean; should the first row of data be used as a header? Defaults to `TRUE` .
```columns```     |     A vector of column names or a named vector of column types.
```infer_schema```     |     Boolean; should column types be automatically inferred? Requires one extra pass over the data. Defaults to `TRUE` .
```delimiter```     |     The character used to delimit each column. Defaults to ',' .
```quote```     |     The character used as a quote. Defaults to '"' .
```escape```     |     The character used to escape other characters. Defaults to '\' .
```charset```     |     The character set. Defaults to "UTF-8" .
```null_value```     |     The character to use for null, or missing, values. Defaults to `NULL` .
```options```     |     A list of strings with additional options.
```repartition```     |     The number of partitions used to distribute the generated table. Use 0 (the default) to avoid partitioning.
```memory```     |     Boolean; should the data be loaded eagerly into memory? (That is, should the table be cached?)
```overwrite```     |     Boolean; overwrite the table with the given name if it already exists?

## Details


 You can read data from HDFS ( `hdfs://` ), S3 ( `s3n://` ),
 as well as the local file system ( `file://` ).
 
 If you are reading from a secure S3 bucket be sure that the
 `AWS_ACCESS_KEY_ID` and `AWS_SECRET_ACCESS_KEY` environment
 variables are both defined.
 
 When `header` is `FALSE` , the column names are generated with a
 `V` prefix; e.g. `V1, V2, ...` .


## Seealso


 Other Spark serialization routines: [`spark_load_table`](spark_load_table.html) ,
  [`spark_read_jdbc`](spark_read_jdbc.html) ,
  [`spark_read_json`](spark_read_json.html) ,
  [`spark_read_parquet`](spark_read_parquet.html) ,
  [`spark_read_source`](spark_read_source.html) ,
  [`spark_read_table`](spark_read_table.html) ,
  [`spark_save_table`](spark_save_table.html) ,
  [`spark_write_csv`](spark_write_csv.html) ,
  [`spark_write_json`](spark_write_json.html) ,
  [`spark_write_parquet`](spark_write_parquet.html) ,
  [`spark_write_table`](spark_write_table.html) 


