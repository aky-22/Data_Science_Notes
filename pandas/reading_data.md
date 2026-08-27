# Reading Data

## What is CSV?

CSV: Comma-Separated Values

For example:

```
Product A,Product B,Product C,
30,21,9,
35,34,1,
41,11,11
```

## Functions

- `pd.read_csv(path)`

Returns a `DataFrame` object

**Notes**:

1. `pd.read_csv()` does not automatically identifies index values.
   However, you can specify the column number which one you want it to be index column.
   For example:

```py
reviews = pd.read_csv("./reviews.csv", index_col=0)
```

## DataFrame

### Methods

- `DataFrame.head()`

Returns first 5 rows

- `DataFrame.to_csv(file_name)`

Save the `DataFrame` to the file.

### Properties

- `DataFrame.shape`

Returns size of the table
