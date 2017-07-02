# `ml_model`: Create an ML Model Object

## Description


 Create an ML model object, wrapping the result of a Spark ML routine call.
 The generated object will be an list() list with S3 classes
 `c("ml_model_<class>", "ml_model")` .


## Usage

```r
ml_model(class, model, ..., .call = sys.call(sys.parent()))
```


## Arguments

Argument      |Description
------------- |----------------
```class```     |     The name of the machine learning routine used in the encompassing model. Note that the model name generated will be generated as `ml_model_<class>` ; that is, `ml_model`  will be prefixed.
```model```     |     The underlying Spark model object.
```...```     |     Additional model information; typically supplied as named values.
```.call```     |     The list() call used in generating this model object (ie, the top-level list() routine that wraps over the associated Spark ML routine). Typically used for print output in e.g. `print`  and `summary` methods.

