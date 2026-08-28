# Analyzing Data

## `DataFrame`

### Column Methods

`DataFrame[column_name]` = `df.col`

- `df.col.describe()`

Returns a high-level summary of the attributes of the given column. (Statistical values)

- `df.col.mean()`

Returns mean value.

- `df.col.median()`

Returns median value.

- `df.col.unique()`

Returns unique values.

- `df.col.value_counts()`

Returns unique values with a list of their occurrence.

- `df.col.map(func)`

Returns a `Series` whose values changed according to the given function.
Does not change original `DataFrame`.

For example:

```py
review_points_mean = reviews.points.mean()
reviews.points.map(lambda p: p - review_points_mean)
```

Here, we changed points column values (p) with p - mean.

- `df.col.apply(func)`

Acts similar to `.map()`

For example:

```py
df["age"].apply(lambda x: x + 1) #
df["name"].apply(lambda x: len(x)) # finds length of strings
df["age_next_year"] = df["age"].apply(lambda x: x + 1) # creates new column
df["result"] = df["score"].apply(
    lambda x: "Pass" if x >= 80 else "Fail"
)
```

- `df.apply(func, axis)`

Pandas moves as column by column. It first applies to the function first column, then second ...
`axis=0` or `axis="rows"` -> columns
`axis=1` or `axis="columns"` -> rows

axis -> think like a direction

If no axis is given, by default it applies to all columns.
If axis is row, it applies to all rows.

For example:

```py
df["total"] = df.apply(
    lambda row: row["age"] + row["score"],
    axis=1
)
```

## `Series`

- `df.apply(func)`

Returns new series whose elements are applied by given function.

## Builtin Mapping

For example:

```py
review_points_mean = reviews.points.mean()
reviews.points - review_points_mean
```

```py
reviews.country + " - " + reviews.region_1
```
