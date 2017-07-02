# `ft_count_vectorizer`: Feature Tranformation -- CountVectorizer

## Description


 Extracts a vocabulary from document collections.


## Usage

```r
ft_count_vectorizer(x, input.col = NULL, output.col = NULL, min.df = NULL,
  min.tf = NULL, vocab.size = NULL, ...)
```


## Arguments

Argument      |Description
------------- |----------------
```x```     |     An object (usually a `spark_tbl` ) coercable to a Spark DataFrame.
```input.col```     |     The name of the input column(s).
```output.col```     |     The name of the output column.
```min.df```     |     Specifies the minimum number of different documents a term must appear in to be included in the vocabulary. If this is an integer greater than or equal to 1, this specifies the number of documents the term must appear in; if this is a double in [0,1), then this specifies the fraction of documents
```min.tf```     |     Filter to ignore rare words in a document. For each document, terms with frequency/count less than the given threshold are ignored. If this is an integer greater than or equal to 1, then this specifies a count (of times the term must appear in the document); if this is a double in [0,1), then this specifies a fraction (out of the document's token count).
```vocab.size```     |     Build a vocabulary that only considers the top vocab.size terms ordered by term frequency across the corpus.
```...```     |     Optional arguments; currently unused.

## Seealso


 See [http://spark.apache.org/docs/latest/ml-features.html](http://spark.apache.org/docs/latest/ml-features.html) for
 more information on the set of transformations available for DataFrame
 columns in Spark.
 
 Other feature transformation routines: [`ft_binarizer`](ft_binarizer.html) ,
  [`ft_bucketizer`](ft_bucketizer.html) ,
  [`ft_discrete_cosine_transform`](ft_discrete_cosine_transform.html) ,
  [`ft_elementwise_product`](ft_elementwise_product.html) ,
  [`ft_index_to_string`](ft_index_to_string.html) ,
  [`ft_one_hot_encoder`](ft_one_hot_encoder.html) ,
  [`ft_quantile_discretizer`](ft_quantile_discretizer.html) ,
  [`ft_regex_tokenizer`](ft_regex_tokenizer.html) ,
  [`ft_sql_transformer`](ft_sql_transformer.html) ,
  [`ft_string_indexer`](ft_string_indexer.html) ,
  [`ft_tokenizer`](ft_tokenizer.html) ,
  [`ft_vector_assembler`](ft_vector_assembler.html) ,
  [`sdf_mutate`](sdf_mutate.html) 


