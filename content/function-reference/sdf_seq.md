# `sdf_seq`: Create DataFrame for Range

## Description


 Creates a DataFrame for the given range


## Usage

```r
sdf_seq(sc, from = 1L, to = 1L, by = 1L, repartition = NULL)
```


## Arguments

Argument      |Description
------------- |----------------
```sc```     |     The associated Spark connection.
```from, to```     |     The start and end to use as a range
```by```     |     The increment of the sequence.
```repartition```     |     The number of partitions to use when distributing the data across the Spark cluster.

