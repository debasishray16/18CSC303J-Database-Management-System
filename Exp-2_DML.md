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

**For entering data dynamically**

```mysql
SQL> /
```

```text
Enter value for id: 2
Enter value for name: Parthajeet Sharma
Enter value for phone: 9809762353
Enter value for section: A1
old   1: INSERT INTO Student VALUES (&ID,'&NAME',&PHONE,'&SECTION')
new   1: INSERT INTO Student VALUES (2,'Parthajeet Sharma',9809762353,'A1')

1 row created.
```

```mysql
SQL> /
```

```text
Enter value for id: 3
Enter value for name: Jeet Kumar Nath
Enter value for phone: 9087654321
Enter value for section: B1
old   1: INSERT INTO Student VALUES (&ID,'&NAME',&PHONE,'&SECTION')
new   1: INSERT INTO Student VALUES (3,'Jeet Kumar Nath',9087654321,'B1')

1 row created.
```

```mysql
SQL> /
```

```text
Enter value for id: 4
Enter value for name: Utkarsh Raj
Enter value for phone: 3545674634
Enter value for section: C1
old   1: INSERT INTO Student VALUES (&ID,'&NAME',&PHONE,'&SECTION')
new   1: INSERT INTO Student VALUES (4,'Utkarsh Raj',3545674634,'C1')

1 row created.
```

```mysql
SQL> /
```

```text
SQL> /
Enter value for id: 5
Enter value for name: Vansh Saxena
Enter value for phone: 8339234322
Enter value for section: j1
old   1: INSERT INTO Student VALUES (&ID,'&NAME',&PHONE,'&SECTION')
new   1: INSERT INTO Student VALUES (5,'Vansh Saxena',8339234322,'J1')

1 row created.
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

        ID NAME                      PHONE SEC
---------- -------------------- ---------- --
         1 Debasish Ray         8700560943 G1
         2 Parthajeet Sharma    9809762353 A1
         3 Jeet Kumar Nath      9087654321 B1
         4 Utkarsh Raj          3545674634 C1
         5 Vansh Saxena         8339234322 J1
```

## Foreign Key

Main Table:

```sql

CREATE TABLE Student_details (Student_ID NUMBER(10) NOT NULL PRIMARY KEY,Email VARCHAR2(23) NOT NULL,Password VARCHAR2(10) NOT NULL, Name VARCHAR2(20) NOT NULL,DOB DATE,Sex VARCHAR2(2) NOT NULL,Address VARCHAR2(20) NOT NULL,Phone NUMBER(10) NOT NULL,Date_of_join VARCHAR2(20) NOT NULL);

```

Another table:

```sql
CREATE TABLE Classroom_Student (Student_ID NUMBER(10) NOT NULL,Classroom_ID NUMBER(10) NOT NULL);
```

To create a foreign key from table: Classroom_Student to main table Student_details, we add:

```sql
ALTER TABLE Classroom_Student ADD CONSTRAINT fk_key1 FOREIGN KEY (Student_ID) REFERENCES Student_details(Student_I
D);
```

**Note: This foreign key is created only one time for one connection . The foreign key is always declared in the derived table , not in main table.**

Another Example:

```text

There is a table Teacher which have attributes and some attributes can be derived from another table(Classroom).

So, we need to declare Foreign key in another table. Not in main table.
```

Main Table(Teacher):

```sql
CREATE TABLE Teacher (Teacher_ID NUMBER(10) PRIMARY KEY NOT NULL,Email VARCHAR(20) NOT NULL, Password VARCHAR2(20) NOT NULL, Name VARCHAR(20) NOT NULL,DOB DATE,Sex VARCHAR2(2) NOT NULL,Address VARCHAR2(20) NOT NULL,Phone NUMBER(10) NOT NULL, Date_of_join VARCHAR2(20) NOT NULL);
```

Another Table(Classroom):

```sql
CREATE TABLE Classroom (Classroom_ID NUMBER(10) NOT NULL PRIMARY KEY, Section VARCHAR2(10) NOT NULL, Grade NUMBER(2) NOT NULL,Teacher_ID NUMBER(10) NOT NULL);
```


So, to declare a Foreign Key in Table(Classroom):

```sql
ALTER TABLE Classroom ADD CONSTRAINT fk_key2 FOREIGN KEY (Teacher_ID) REFERENCES Teacher(Teacher_ID);
```