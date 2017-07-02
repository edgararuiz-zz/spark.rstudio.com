# `spark_read_source`: Read from a generic source into a Spark DataFrame.

## Description


 Read from a generic source into a Spark DataFrame.


## Usage

```r
spark_read_source(sc, name, source, options = list(), repartition = 0,
  memory = TRUE, overwrite = TRUE)
```


## Arguments

Argument      |Description
------------- |----------------
```sc```     |     A `spark_connection` .
```name```     |     The name to assign to the newly generated table.
```source```     |     A data source capable of reading data.
```options```     |     A list of strings with additional options. See [http://spark.apache.org/docs/latest/sql-programming-guide.html#configuration](http://spark.apache.org/docs/latest/sql-programming-guide.html#configuration) .
```repartition```     |     The number of partitions used to distribute the generated table. Use 0 (the default) to avoid partitioning.
```memory```     |     Boolean; should the data be loaded eagerly into memory? (That is, should the table be cached?)
```overwrite```     |     Boolean; overwrite the table with the given name if it already exists?

## Seealso


 Other Spark serialization routines: [`spark_load_table`](spark_load_table.html) ,
  [`spark_read_csv`](spark_read_csv.html) ,
  [`spark_read_jdbc`](spark_read_jdbc.html) ,
  [`spark_read_json`](spark_read_json.html) ,
  [`spark_read_parquet`](spark_read_parquet.html) ,
  [`spark_read_table`](spark_read_table.html) ,
  [`spark_save_table`](spark_save_table.html) ,
  [`spark_write_csv`](spark_write_csv.html) ,
  [`spark_write_json`](spark_write_json.html) ,
  [`spark_write_parquet`](spark_write_parquet.html) ,
  [`spark_write_table`](spark_write_table.html) 


