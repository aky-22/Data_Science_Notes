
```sql
... JOIN ...
ON ... ... ...
``` 
- Bir tabloyu diğer tablonun sonuna `ON` parametresine göre ekliyor kısaca.
- Küme işlemlerine benzer.

# `INNER JOIN ...`

Kısaca kümelerdeki kesişim $A \cap B$ gibi. `ON` üzerine verdiğimiz koşula göre eşleşme yapıyor. Eşleşenleri sadece gösteriyor. Mesela
```sql
SELECT *
FROM employees
INNER JOIN buildings
ON building_name = building;
```
Burada önce `employees` tablosunu alıyor. Sonra `building_name` ile `building` sutün değerleri aynı olanları buluyor ve sadece bunları listeliyor.

# `LEFT JOIN ...`

Kısaca kümelerdeki $A - B$ işlemi gibi. Mesela
```sql
SELECT *
FROM employees
LEFT JOIN buildings
ON building_name = building;
```
Önce `employees` tablosunu alıyor. Buradaki sutünlar korunacak ne olursa olsun. Sonra `ON` üzerine verdiğimiz koşulları sağlayan sutünları `buildings` ten bulup sona ekleyecek. Burada bazı satırlar `NULL` kalabilir normal.

Bunlara ek olarak `RIGHT JOIN`, `FULL JOIN` mevcut.