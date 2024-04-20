# DML Statements

1. INSERT command
```mysql
 INSERT INTO Student VALUES (&ID,'&NAME',&PHONE,'&SECTION');
```

```text
Enter value for id: 1
Enter value for name: Debasish Ray
Enter value for phone: 8700560943
Enter value for section: G1
old   1: INSERT INTO Student VALUES (&ID,'&NAME',&PHONE,'&SECTION')
new   1: INSERT INTO Student VALUES (1,'Debasish Ray',8700560943,'G1')
```

2. UPDATE command
```mysql
UPDATE student SET section='J1" where ID=5;
```

```text
SQL> UPDATE student SET section='J1' where ID=5;

1 row updated.
```

3. Delete command
```mysql
DELETE FROM student where ID=1;
```

```text
SQL> DELETE FROM student where ID=1;

1 row deleted.
```


## Result

```text
SQL> select * from student;

        ID NAME                      PHONE SE
---------- -------------------- ---------- --
         1 Debasish Ray         8700560943 G1
         2 Parthajeet Sharma    9809762353 A1
         3 Jeet Kumar Nath      9087654321 B1
         4 Utkarsh Raj          3545674634 C1
         5 Vansh Saxena         8339234322 J1
```