# Grouping Data

## Interesting Example

```py
reviews.groupby('points').points.count()
```

`groupby()` created a group of reviews which allotted the same point values to the given wines.
Then, for each of these groups, we grabbed the `points` column and counted how many times it appeared.
`value_counts()` is just a shortcut to this `groupby()` operation.

Todo

- `groupby()`
- `agg()`
- multiindex
- `sort_values(by="column_name", [ascending=False])`
  -> we can sort more than one column at a time like if 2 of the row's first value same check the other value

## `df.groupby(col)...`

Needs a calculation. For example:

```py
reviews.groupby("country").points.mean()
```

Groups the table according to country values, then calculates their means according to point values.

df.groupby("NEYE\*GÖRE*GRUPLAYACAĞIM")
.NEYİ*ÖLÇECEĞİM
.NASIL_ÖLÇECEĞİM

## `df.groupby(col)....agg()`

To use more than one calculation. For example:

```py
reviews.groupby("country").points.agg(["mean", "min", "max"])
```
