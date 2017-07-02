# `sdf_len`: Create DataFrame for Length

## Description


 Creates a DataFrame for the given length.


## Usage

```r
sdf_len(sc, length, repartition = NULL)
```


## Arguments

Argument      |Description
------------- |----------------
```sc```     |     The associated Spark connection.
```length```     |     The desired length of the sequence.
```repartition```     |     The number of partitions to use when distributing the data across the Spark cluster.

