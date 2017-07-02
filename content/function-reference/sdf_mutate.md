# `sdf_mutate`: Mutate a Spark DataFrame

## Description


 Use Spark's [feature transformers](http://spark.apache.org/docs/latest/ml-features.html) 
 to mutate a Spark DataFrame.


## Usage

```r
sdf_mutate(.data, ...)
sdf_mutate_(.data, ..., .dots)
```


## Arguments

Argument      |Description
------------- |----------------
```.data```     |     A `spark_tbl` .
```...```     |     Named arguments, mapping new column names to the transformation to be applied.
```.dots```     |     A named list, mapping output names to transformations.

## Seealso


 Other feature transformation routines: [`ft_binarizer`](ft_binarizer.html) ,
  [`ft_bucketizer`](ft_bucketizer.html) ,
  [`ft_count_vectorizer`](ft_count_vectorizer.html) ,
  [`ft_discrete_cosine_transform`](ft_discrete_cosine_transform.html) ,
  [`ft_elementwise_product`](ft_elementwise_product.html) ,
  [`ft_index_to_string`](ft_index_to_string.html) ,
  [`ft_one_hot_encoder`](ft_one_hot_encoder.html) ,
  [`ft_quantile_discretizer`](ft_quantile_discretizer.html) ,
  [`ft_regex_tokenizer`](ft_regex_tokenizer.html) ,
  [`ft_sql_transformer`](ft_sql_transformer.html) ,
  [`ft_string_indexer`](ft_string_indexer.html) ,
  [`ft_tokenizer`](ft_tokenizer.html) ,
  [`ft_vector_assembler`](ft_vector_assembler.html) 


## Examples

```r 
 list("\n", "# using the 'beaver1' dataset, binarize the 'temp' column\n", "data(beavers, package = \"datasets\")\n", "beaver_tbl <- copy_to(sc, beaver1, \"beaver\")\n", "beaver_tbl %>%\n", "  mutate(squared = temp ^ 2) %>%\n", "  sdf_mutate(warm = ft_binarizer(squared, 1000)) %>%\n", "  sdf_register(\"mutated\")\n", "\n", "# view our newly constructed tbl\n", "head(beaver_tbl)\n", "\n", "# note that we have two separate tbls registered\n", "dplyr::src_tbls(sc)\n") 
 ``` 

