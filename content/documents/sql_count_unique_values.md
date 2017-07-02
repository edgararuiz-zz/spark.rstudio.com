Spark SQL: Count Unique Values
================

This article shows how you might use the `dplyr` interface to Spark SQL to compute the number of times a particular value shows up in a DataFrame column.

First, we read our data into Spark.

``` r
library(sparklyr)
library(dplyr)
library(ggplot2)

data(diamonds, package = "ggplot2")

sc <- spark_connect(master = "local", version = "1.6.1")
diamonds_tbl <- copy_to(sc, diamonds, "diamonds", overwrite = TRUE)
```

Now that we have `diamonds_tbl` available, we can use the `dplyr` interface to compute the number of times each entry in the `cut` column occurs.

``` r
diamonds_tbl %>%
  group_by(cut) %>%
  summarize(total = n())
```

    ## Source:   query [?? x 2]
    ## Database: spark connection master=local app=sparklyr local=TRUE
    ## 
    ##         cut total
    ##       <chr> <dbl>
    ## 1     Ideal 21551
    ## 2      Fair  1610
    ## 3 Very Good 12082
    ## 4      Good  4906
    ## 5   Premium 13791
