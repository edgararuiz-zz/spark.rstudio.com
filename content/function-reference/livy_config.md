# `livy_config`: Create a Spark Configuration for Livy

## Description


 Create a Spark Configuration for Livy


## Usage

```r
livy_config(config = spark_config(), username = NULL, password = NULL)
```


## Arguments

Argument      |Description
------------- |----------------
```config```     |     Optional base configuration
```username```     |     The username to use in the Authorization header
```password```     |     The password to use in the Authorization header

## Details


 Extends a Spark `"spark_config"` configuration with settings
 for Livy. For instance, `"username"` and `"password"` 
 define the basic authentication settings for a Livy session.


## Value


 Named list with configuration data


