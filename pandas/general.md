# General

## Functions

- `pd.set_option()`

```py
import pandas as pd
reviews = pd.read_csv("./review.csv", index_col=0)
pd.set_option('display.max_rows', 5)
```

Here, we set the max showed row number to 5.
