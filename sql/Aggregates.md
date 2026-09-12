```sql
SELECT AGG_FUNC(_column_or_expression_) AS aggregate_description, … 
FROM mytable
WHERE _constraint_expression_;
```


| Function                                | Description                                                                                                                                                                                     |
| --------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **COUNT(*****)**, **COUNT(**column**)** | A common function used to counts the number of rows in the group if no column name is specified. Otherwise, count the number of rows in the group with non-NULL values in the specified column. |
| **MIN(**column**)**                     | Finds the smallest numerical value in the specified column for all rows in the group.                                                                                                           |
| **MAX(**column**)**                     | Finds the largest numerical value in the specified column for all rows in the group.                                                                                                            |
| **AVG(**column)                         | Finds the average numerical value in the specified column for all rows in the group.                                                                                                            |
| **SUM(**column**)**                     | Finds the sum of all numerical values in the specified column for the rows in the group.                                                                                                        |

# `GROUP BY ...`

```sql
SELECT AGG_FUNC(_column_or_expression_) AS aggregate_description, …
FROM mytable
WHERE _constraint_expression_
GROUP BY column;
```
column'a göre önce gruplara ayırıyor gibi düşünebilirsin ve sonra seçim yapıyor. Ancak normalde okunuşa göre galiba sırayla her şey.

# `HAVING conditions`

Bu aslında biraz gereksiz gibi şuanlık. Gruplara ayırdıktan sonra belli koşula göre tekrar filtrelemek için kullanılır.