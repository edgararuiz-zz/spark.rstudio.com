# `ml_tree_feature_importance`: Spark ML - Feature Importance for Tree Models

## Description


 Spark ML - Feature Importance for Tree Models


## Usage

```r
ml_tree_feature_importance(sc, model)
```


## Arguments

Argument      |Description
------------- |----------------
```sc```     |     A `spark_connection` .
```model```     |     An `ml_model` encapsulating the output from a decision tree.

## Value


 A sorted data frame with feature labels and their relative importance.


