# `ml_saveload`: Save / Load a Spark ML Model Fit

## Description


 Save / load a `ml_model` fit.


## Usage

```r
ml_load(sc, file, meta = ml_load_meta(file))
ml_save(model, file, meta = ml_save_meta(model, file))
```


## Arguments

Argument      |Description
------------- |----------------
```sc```     |     A `spark_connection` .
```file```     |     The path where the Spark model should be serialized / deserialized.
```meta```     |     The path where the list() metadata should be serialized / deserialized. Currently, this must be a local filesystem path. Alternatively, this can be an list() function that saves / loads the metadata object.
```model```     |     A `ml_model` fit.

## Details


 These functions are currently experimental and not yet ready for production
 use. Unfortunately, the training summary information for regression fits
 (linear, logistic, generalized) are currently not serialized as part of the
 model fit, and so model fits recovered through `ml_load` will not work
 with e.g. `fitted` , `residuals` , and so on. Such fits should still
 be suitable for generating predictions with new data, however.


