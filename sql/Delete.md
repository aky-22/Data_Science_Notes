When you need to delete data from a table in the database, you can use a `DELETE` statement, which describes the table to act on, and the rows of the table to delete through the `WHERE` clause.

```sql
DELETE FROM mytable
WHERE condition;
```

**Note:** If you decide to leave out the `WHERE` constraint, then _all_ rows are removed, which is a quick and easy way to clear out a table completely (if intentional).

Check before executing with `SELECT`.


# Delete Completely

Like the `CREATE TABLE` statement, the database may throw an error if the specified table does not exist, and to suppress that error, you can use the `IF EXISTS` clause.

```sql
DROP TABLE IF EXISTS mytable;
```


In addition, if you have another table that is dependent on columns in table you are removing (for example, with a `FOREIGN KEY` dependency) then you will have to either update all dependent tables first to remove the dependent rows or to remove those tables entirely.