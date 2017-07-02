# `ft_quantile_discretizer`: Feature Transformation -- QuantileDiscretizer

## Description


 Takes a column with continuous features and outputs a column with binned
 categorical features. The bin ranges are chosen by taking a sample of the
 data and dividing it into roughly equal parts. The lower and upper bin bounds
 will be -Infinity and +Infinity, covering all real values. This attempts to
 find numBuckets partitions based on a sample of the given input data, but it
 may find fewer depending on the data sample values.


## Usage

```r
ft_quantile_discretizer(x, input.col = NULL, output.col = NULL,
  n.buckets = 5L, ...)
```


## Arguments

Argument      |Description
------------- |----------------
```x```     |     An object (usually a `spark_tbl` ) coercable to a Spark DataFrame.
```input.col```     |     The name of the input column(s).
```output.col```     |     The name of the output column.
```n.buckets```     |     The number of buckets to use.
```...```     |     Optional arguments; currently unused.

## Details


 Note that the result may be different every time you run it, since the sample
 strategy behind it is non-deterministic.


## Seealso


 See [http://spark.apache.org/docs/latest/ml-features.html](http://spark.apache.org/docs/latest/ml-features.html) for
 more information on the set of transformations available for DataFrame
 columns in Spark.
 
 Other feature transformation routines: [`ft_binarizer`](ft_binarizer.html) ,
  [`ft_bucketizer`](ft_bucketizer.html) ,
  [`ft_count_vectorizer`](ft_count_vectorizer.html) ,
  [`ft_discrete_cosine_transform`](ft_discrete_cosine_transform.html) ,
  [`ft_elementwise_product`](ft_elementwise_product.html) ,
  [`ft_index_to_string`](ft_index_to_string.html) ,
  [`ft_one_hot_encoder`](ft_one_hot_encoder.html) ,
  [`ft_regex_tokenizer`](ft_regex_tokenizer.html) ,
  [`ft_sql_transformer`](ft_sql_transformer.html) ,
  [`ft_string_indexer`](ft_string_indexer.html) ,
  [`ft_tokenizer`](ft_tokenizer.html) ,
  [`ft_vector_assembler`](ft_vector_assembler.html) ,
  [`sdf_mutate`](sdf_mutate.html) 


