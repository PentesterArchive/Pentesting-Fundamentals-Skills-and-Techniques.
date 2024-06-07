# SQL Query
In this section, we will learn how to control the results output of any SELECT query.
##Sorting Results
We are going to use the next database:<br />
<img src="https://github.com/alejandro-pentest/Hacking-Web/assets/161533623/fa658029-64df-44b1-bdcc-c3dfc7ed828e" width="350">



### ORDER BY
We can sort the results of any query using ORDER BY and specifying the column to sort by:
```sql
SELECT * FROM logins ORDER BY password;
```

<img src="https://github.com/alejandro-pentest/Hacking-Web/assets/161533623/7dbaabbb-60c3-465e-a88e-9968693c7111" width="350">


By default, the sort is done in ascending order, but we can also sort the results by `ASC` or `DESC`:
```sql
SELECT * FROM logins ORDER BY password DESC;
```
<img src="https://github.com/alejandro-pentest/Hacking-Web/assets/161533623/4a9ee588-09f2-4d14-a0c8-bf67e688a5a6" width="350">


It is also possible to sort by multiple columns, to have a secondary sort for duplicate values in one column:
```sql
SELECT * FROM logins ORDER BY password DESC, id ASC;
```
<img src="https://github.com/alejandro-pentest/Hacking-Web/assets/161533623/390c51aa-2ea7-4755-95c7-473a584e0197" width="400">

### LIMIT results
In case our query returns a large number of records, *we can LIMIT the results to what we want only*, using `LIMIT` and the number of records we want:
```sql
SELECT * FROM logins LIMIT 2;
```
<img src="https://github.com/alejandro-pentest/Hacking-Web/assets/161533623/8ba43c62-498d-4f12-9743-0f92c66cd813" width="400">

### WHERE Clause
To **filter or search for specific data**, we can use conditions with the SELECT statement using the **WHERE clause**, to fine-tune the results:
```sql
SELECT * FROM table_name WHERE <condition>;
```

```sql
SELECT * FROM logins WHERE id > 1;
```



<img src="https://github.com/alejandro-pentest/Hacking-Web/assets/161533623/fd0f0c19-0f48-48cf-a996-e1bd377bdf26" width="400">



```sql
SELECT * FROM logins WHERE username = "eddie";
```
> String and date data types should be surrounded by single quote (') or double quotes ("), while numbers can be used directly.



<img src="https://github.com/alejandro-pentest/Hacking-Web/assets/161533623/fc0145a9-ed78-4486-9d9a-c76415ea7c17" width="450">







### LIKE Clause
Another useful SQL clause is **LIKE**, enabling *selecting records by matching a certain pattern*. The query below retrieves all records with usernames starting with admin:
```sql
SELECT * FROM logins WHERE username LIKE 'admin%';
```
<img src="https://github.com/alejandro-pentest/Hacking-Web/assets/161533623/f4a40a30-85cd-400f-bca5-e01c5455a915" width="450"><br />
<img src="https://github.com/alejandro-pentest/Hacking-Web/assets/161533623/dcb2992e-63bf-4a46-9867-38a1e60cd5d3" width="550">


- The **%** symbol acts as a wildcard and *matches all characters after admin*. It is used to match zero or more characters. 
- The **_** symbol *is used to match exactly one character*.
```sql
mysql> SELECT * FROM logins WHERE username like '___';
```
<img src="https://github.com/alejandro-pentest/Hacking-Web/assets/161533623/26f3d747-ec24-49d9-84b7-34e96c34bf9a" width="450">





