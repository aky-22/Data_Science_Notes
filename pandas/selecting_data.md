# Selecting Data

```py
import pandas as pd
reviews = pd.read_csv("./reviews.csv", index_col=0)
```

## Basic Selection (Column Selection)

Also select a `Series` from `DataFrame`

For example:

```py
reviews.country
reviews['country']
```

Selects column.

**Note**: Watch out to column labels such as "country names", "state names", ...
If there is a space in a column label, you should use [] syntax when selecting it.
Also you can use variables inside of [].

```py
reviews.country[0]
reviews["country"][0]
```

Selects first cell.

## Advanced Selection

### Index-based Selection (`iloc`)

The letter i stands for index, so remember from it.
Because it is index based, it chooses 1:10 -> 1, 2, ..., 9

**Note**: We treat the `DataFrame` as a matrix.

For example:

```py
reviews.iloc[0]
```

Selects first row.

`DataFrame.iloc` is used to select either rows, or columns or both.

For example:

```py
reviews.iloc[:, 0]
```

Selects first column

Another example:

```py
reviews.iloc[:3, 0]
```

Select first 3 rows of the first column.

It is also possible to pass a list.
For example:

```py
reviews.iloc[[0, 5, 9]]
```

Negative numbers can be used to select starting from the end
For example:

```py
reviews.iloc[-5:]
```

Selects the last 5 rows.

### Label-based Selection (`loc`)

For example:

```py
reviews.loc[0, 'country']
```

Selects first entry of the column "country"

**Note**: Since our datasets are generally have meaningful column labels,
it is easier to use `loc`

For example:

```py
reviews.loc[:, ['taster_name', 'taster_twitter_handle', 'points']]
```

Seems really intuitive

**Note**: Label-based selection derives its power from the labels in the index.
For example:

```py
reviews.set_index("title")
```

Sets the "title" column asa index column, and we can choose meaningful rows.,

**Important Note**: `loc` looks like using a matrix notation. And as far as I learned it is better to use `loc` if you do not have a specific reason to use `iloc`.

### Differences

**Note**: `iloc` uses the Python stdlib indexing scheme, where the first element of the range is included and the last one excluded. So "0:10" will select entries 0,...,9. `loc`, meanwhile, indexes inclusively. So "0:10" will select entries 0,...,10.

## Conditional Selection

For example:

```py
reviews.country == 'Italy'
```

Returns a `Series` which has elements of boolean values.
Then this result can be used inside of `loc` to select reviews from the country Italy.

```py
reviews.loc[reviews.country == 'Italy']
```

We can even mix the conditions

```py
reviews.loc[(reviews.country == 'Italy') & (reviews.points >= 90)]
reviews.loc[(reviews.country == 'Italy') | (reviews.points >= 90)]
```

There are some builtin conditional selectors.

For example:

```py
reviews.loc[reviews.country.isin(['Italy', 'France'])]
```

Lets you select data whose value "is in" a list of values

`isnull` and `notnull` lets you select null related values
For example:

```py
reviews.loc[reviews.price.notnull()]
```

Selects the reviews which do have a price.

**Note**: Do not forget to use `loc`
