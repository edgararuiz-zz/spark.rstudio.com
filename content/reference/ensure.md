# `ensure`: Enforce Specific Structure for R Objects

## Description


 These routines are useful when preparing to pass objects to
 a Spark routine, as it is often necessary to ensure certain
 parameters are scalar integers, or scalar doubles, and so on.


## Usage

```r
ensure_scalar_integer(object, allow.na = FALSE, allow.null = FALSE,
  default = NULL)
ensure_scalar_double(object, allow.na = FALSE, allow.null = FALSE,
  default = NULL)
ensure_scalar_boolean(object, allow.na = FALSE, allow.null = FALSE,
  default = NULL)
ensure_scalar_character(object, allow.na = FALSE, allow.null = FALSE,
  default = NULL)
```


## Arguments

Argument      |Description
------------- |----------------
```object```     |     An list() object.
```allow.na```     |     Are `NA` values permitted for this object?
```allow.null```     |     Are `NULL` values permitted for this object?
```default```     |     If `object` is `NULL` , what value should be used in its place? If `default` is specified, `allow.null`  is ignored (and assumed to be `TRUE` ).

