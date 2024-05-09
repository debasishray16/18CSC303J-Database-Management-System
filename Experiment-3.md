# DCL (Data Control Language)

DCL commands are those commands that controls the process of transaction within the database and maintains integrity and security.

```sql
CREATE TABLE class(id NUMBER(10) NOT NULL,name VARCHAR2(10));
```

The output is:

```text
SQL> CREATE TABLE class(id NUMBER(10) NOT NULL,name VARCHAR2(10));

Table created.
```

```sql
INSERT INTO class VALUES (5,'Rahul');
SAVEPOINT A;
```

```sql
INSERT INTO class VALUES (6,'Data');
INSERT INTO class VALUES (7,'Hridesh');
SAVEPOINT B;
```

```sql
INSERT INTO class VALUES (8,'Hridesha');
INSERT INTO class VALUES (9,'ridesha');
INSERT INTO class VALUES (10,'ridesh');
SAVEPOINT C;
```

```sql
Select * from class;
```

The output is:

```text
SQL> Select * from class;

        ID NAME
---------- ----------
         5 Rahul
         6 Data
         7 Hridesh
         8 Hridesha
         9 ridesha
        10 ridesh
```

Then, if we rollback without committing , then, most of the data gets deleted.

```sql
rollback to b;
```

The output is:

```text
SQL> Select * from class;

        ID NAME
---------- ----------
         5 Rahul
         6 Data
         7 Hridesh
```

```sql
rollback to a;
```

```text
SQL> Select * from class;

        ID NAME
---------- ----------
         5 Rahul
```
