# `top_n`: Select top (or bottom) n rows (by value)

## Description


 This is a convenient wrapper that uses [filter()] and
 [min_rank()] to select the top or bottom entries in each group,
 ordered by `wt`.


## Usage

```r
top_n(x, n, wt)
```


## Arguments

Argument      |Description
------------- |----------------
```x```     |     a [tbl()] to filter
```n```     |     number of rows to return. If `x` is grouped, this is the number of rows per group. Will include more than `n` rows if there are ties.  If `n` is positive, selects the top `n` rows. If negative, selects the bottom `n` rows.
```wt```     |     (Optional). The variable to use for ordering. If not specified, defaults to the last variable in the tbl.  This argument is automatically [quoted][rlang::quo] and later [evaluated][rlang::eval_tidy] in the context of the data frame. It supports [unquoting][rlang::quasiquotation]. See `vignette("programming")` for an introduction to these concepts.

