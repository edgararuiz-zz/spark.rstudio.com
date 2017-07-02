# `ml_classification_eval`: Spark ML - Classification Evaluator

## Description


 See the Spark ML Documentation [MulticlassClassificationEvaluator](https://spark.apache.org/docs/1.6.1/api/scala/index.html#org.apache.spark.ml.evaluation.MulticlassClassificationEvaluator) 


## Usage

```r
ml_classification_eval(predicted_tbl_spark, label, predicted_lbl,
  metric = "f1")
```


## Arguments

Argument      |Description
------------- |----------------
```predicted_tbl_spark```     |     A tbl_spark object that contains a columns with predicted labels
```label```     |     Name of the column that contains the true, indexed label. Support for binary and multi-class labels, column should be of double type (use as.double)
```predicted_lbl```     |     Name of the column that contains the predicted label NOT the scored probability. Support for binary and multi-class labels, column should be of double type (use as.double)
```metric```     |     A classification metric, one of: f1 (default), precision, recall, weightedPrecision, weightedRecall, accuracy

## Value


 see `metric` 


