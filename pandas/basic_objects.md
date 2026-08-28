# Basic Objects

```py
import pandas as pd
```

There are 2 core objects: `DataFrame` and `Series`

## DataFrame

Simply, it is a table.

`pd.DataFrame(dict)`

_dict_ is a special dictionary object which is every key's value is a list.
Every key is a column name, and value of the key is corresponding row values.

Example:

```py
pd.DataFrame({'Yes': [50, 21], 'No': [131, 2]})
```

_row labels_ -> 0, 1, 2, ... if not specified.
These _row labels_ are also known as **index**

Example:

```py
pd.DataFrame({'Bob': ['I liked it.', 'It was awful.'],
              'Sue': ['Pretty good.', 'Bland.']},
             index=['Product A', 'Product B'])
```

**Note**: Make sure the table size is consistent.
For example if there are 3 rows in the table however there are only 2 index, then it will throw an error.

## Series

Simply, it is a list.

`pd.Series(list)`

Example:

```py
pd.Series([1, 2, 3, 4, 5])
```

_row labels_ -> you can change same way with `DataFrame`
_name_ -> You can change the name of series

Example:

```py
pd.Series([30, 35, 40], index=['2015 Sales', '2016 Sales', '2017 Sales'], name='Product A')
```

**Note**: A Series is, in essence, a single column of a DataFrame.

**Note**: The Series and the DataFrame are intimately related. It's helpful to think of a DataFrame as actually being just a bunch of Series "glued together".

## Assigning Data

For example:

```py
reviews['critic'] = 'everyone'
```

Assigns constant value to every cell of the column.

Or you can assign iterable values like:

```py
reviews['index_backwards'] = range(len(reviews), 0, -1)
```
