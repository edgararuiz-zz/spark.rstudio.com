# `ml_lda`: Spark ML -- Latent Dirichlet Allocation

## Description


 Fit a Latent Dirichlet Allocation (LDA) model to a Spark DataFrame.


## Usage

```r
ml_lda(x, features = tbl_vars(x), k = length(features), alpha = (50/k) +
  1, beta = 0.1 + 1, ml.options = ml_options(), ...)
```


## Arguments

Argument      |Description
------------- |----------------
```x```     |     An object coercable to a Spark DataFrame (typically, a `tbl_spark` ).
```features```     |     The name of features (terms) to use for the model fit.
```k```     |     The number of topics to estimate.
```alpha```     |     Concentration parameter for the prior placed on documents' distributions over topics. This is a singleton which is replicated to a vector of length `k` in fitting (as currently EM optimizer only supports symmetric distributions, so all values in the vector should be the same). For Expectation-Maximization optimizer values should be > 1.0. By default `alpha = (50 / k) + 1` , where `50/k` is common in LDA libraries and +1 follows from Asuncion et al. (2009), who recommend a +1 adjustment for EM.
```beta```     |     Concentration parameter for the prior placed on topics' distributions over terms. For Expectation-Maximization optimizer value should be > 1.0 and by default `beta = 0.1 + 1` , where 0.1 gives a small amount of smoothing and +1 follows Asuncion et al. (2009), who recommend a +1 adjustment for EM.
```ml.options```     |     Optional arguments, used to affect the model generated. See [`ml_options`](ml_options.html) for more details.
```...```     |     Optional arguments. The `data` argument can be used to specify the data to be used when `x` is a formula; this allows calls of the form `ml_linear_regression(y ~ x, data = tbl)` , and is especially useful in conjunction with [`do`](do.html) .

## Seealso


 Other Spark ML routines: [`ml_als_factorization`](ml_als_factorization.html) ,
  [`ml_decision_tree`](ml_decision_tree.html) ,
  [`ml_generalized_linear_regression`](ml_generalized_linear_regression.html) ,
  [`ml_gradient_boosted_trees`](ml_gradient_boosted_trees.html) ,
  [`ml_kmeans`](ml_kmeans.html) ,
  [`ml_linear_regression`](ml_linear_regression.html) ,
  [`ml_logistic_regression`](ml_logistic_regression.html) ,
  [`ml_multilayer_perceptron`](ml_multilayer_perceptron.html) ,
  [`ml_naive_bayes`](ml_naive_bayes.html) ,
  [`ml_one_vs_rest`](ml_one_vs_rest.html) , [`ml_pca`](ml_pca.html) ,
  [`ml_random_forest`](ml_random_forest.html) ,
  [`ml_survival_regression`](ml_survival_regression.html) 


## Note


 The topics' distributions over terms are called "beta" in the original LDA paper by Blei et al., but are called "phi" in many later papers such as Asuncion et al., 2009.
 
 For terminology used in LDA model see [Spark LDA documentation](https://spark.apache.org/docs/latest/api/scala/index.html#org.apache.spark.ml.clustering.LDA) .


## References


 Original LDA paper (journal version): Blei, Ng, and Jordan. "Latent Dirichlet Allocation." JMLR, 2003.
 
 Asuncion et al. (2009)


## Examples

```r 
 list("\n", "library(janeaustenr)\n", "library(sparklyr)\n", "library(dplyr)\n", "\n", "sc <- spark_connect(master = \"local\")\n", "\n", "austen_books <- austen_books()\n", "books_tbl <- sdf_copy_to(sc, austen_books, overwrite = TRUE)\n", "first_tbl <- books_tbl %>% filter(nchar(text) > 0) %>% head(100)\n", "\n", "first_tbl %>%\n", "  ft_tokenizer(\"text\", \"tokens\") %>%\n", "  ft_count_vectorizer(\"tokens\", \"features\") %>%\n", "  ml_lda(\"features\", k = 4)\n") 
 ``` 

