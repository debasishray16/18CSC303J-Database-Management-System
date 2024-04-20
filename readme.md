# Experiment 1

## DDL Commands
1. Create command creates a table in database.

```mysql
CREATE TABLE student (id NUMBER(10) NOT NULL PRIMARY KEY, name VARCHAR(10) NOT NULL,phone NUMBER(10) NOT NULL, section VARCHAR2(2) NOT NULL);
```

2. Adding the column
```mysql
ALTER TABLE student ADD address VARCHAR2(20) NOT NULL;
```

3. Modify the column
```mysql
SQL> ALTER TABLE student MODIFY address VARCHAR2(10) NULL;
```

4. Deleting the column
```mysql
ALTER TABLE student DROP COLUMN address ;
```

```text
 Name                                      Null?    Type
 ----------------------------------------- -------- ----------------------------
 ID                                        NOT NULL NUMBER(10)
 NAME                                      NOT NULL VARCHAR2(10)
 PHONE                                     NOT NULL NUMBER(10)
 SECTION                                   NOT NULL VARCHAR2(2)
```


## TRUNCATE VS DROP TABLE

1. Truncate table deletes rows from table but does not remove table from database.
```mysql
TRUNCATE TABLE student;
```

```text
SQL> select * from student;
no rows selected
```
2. Drop table deletes the whole table from the database.
```mysql
```

```mysql
DROP TABLE student;
```

```text
SQL> select * from student;
select * from student
              *
ERROR at line 1:
ORA-00942: table or view does not exist
```
