# `ml_binary_classification_eval`: Spark ML - Binary Classification Evaluator

## Description


 See the Spark ML Documentation [BinaryClassificationEvaluator](https://spark.apache.org/docs/1.6.1/api/scala/index.html#org.apache.spark.ml.evaluation.BinaryClassificationEvaluator) 


## Usage

```r
ml_binary_classification_eval(predicted_tbl_spark, label, score,
  metric = "areaUnderROC")
```


## Arguments

Argument      |Description
------------- |----------------
```predicted_tbl_spark```     |     The result of running sdf_predict
```label```     |     Name of column string specifying which column contains the true, indexed labels (ie 0 / 1)
```score```     |     Name of column contains the scored probability of a success (ie 1)
```metric```     |     The classification metric -  one of: areaUnderRoc (default) or areaUnderPR

## Value


 area under the specified curve


