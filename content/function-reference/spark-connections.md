# `spark-connections`: Manage Spark Connections

## Description


 These routines allow you to manage your connections to Spark.


## Usage

```r
spark_connect(master = "local", spark_home = Sys.getenv("SPARK_HOME"),
  method = c("shell", "livy", "databricks", "test"), app_name = "sparklyr",
  version = NULL, hadoop_version = NULL, config = spark_config(),
  extensions = sparklyr::registered_extensions(), ...)
spark_connection_is_open(sc)
spark_disconnect(sc, ...)
spark_disconnect_all()
```


## Arguments

Argument      |Description
------------- |----------------
```master```     |     Spark cluster url to connect to. Use `"local"` to connect to a local instance of Spark installed via [`spark_install`](spark_install.html) .
```spark_home```     |     The path to a Spark installation. Defaults to the path provided by the `SPARK_HOME` environment variable. If `SPARK_HOME` is defined, it will be always be used unless the `version` parameter is specified to force the use of a locally installed version.
```method```     |     The method used to connect to Spark. Currently, only `"shell"` is supported.
```app_name```     |     The application name to be used while running in the Spark cluster.
```version```     |     The version of Spark to use. Only applicable to `"local"` Spark connections.
```hadoop_version```     |     The version of Hadoop to use. Only applicable to `"local"` Spark connections.
```config```     |     Custom configuration for the generated Spark connection. See [`spark_config`](spark_config.html) for details.
```extensions```     |     Extension packages to enable for this connection. By default, all packages enabled through the use of [`sparklyr::register_extension`](sparklyr::register_extension.html) will be passed here.
```...```     |     Optional arguments; currently unused.
```sc```     |     A `spark_connection` .

## Examples

```r 
 
 sc <- spark_connect(master = "spark://HOST:PORT")
 connection_is_open(sc)
 
 spark_disconnect(sc)
 
 ``` 

