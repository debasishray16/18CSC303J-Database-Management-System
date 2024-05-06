# PL/SQL Cursor

PL/SQL Cursor are those which are used to hold multiple rows returned by the SQL statement.

```sql
CREATE TABLE IF NOT EXISTS (id NUMBER PRIMARY KEY NOT NULL, name VARCHAR2(10) NOT NULL, age NUMBER);
```

There are two types of Cursors:

1. Implicit Cursors- Implicit Cursors are those which are already cretaed by Oracle.

2. Explicit Cursors- Explicit Cursors are those which are created by user.

## Implicit Cursors

Implicit cursors are used to know the status of last DML statement executed.

```text
%found - True when previous DML executed successfully.
%notfound - False when previous DML not executed successfully.
%rowcount - Number of rows returned.
```

Taking an example, where we wanted to delete a rwo based on id number.

```sql
DECLARE

e_id Employee.id%type;

BEGIN

e_id:=&id;
DELETE FROM Employee WHERE id=e_id;

IF SQL%found THEN
dbms_output.put_line('Record Deleted');
ELSE
dbms_output.put_line('No such customer');
END IF;

COMMIT;
END;
/
```

```text
SQL> DECLARE
  2
  3  e_id Employee.id%type;
  4
  5  BEGIN
  6
  7  e_id:=&id;
  8
  9  DELETE FROM Employee WHERE id=e_id;
 10
 11  IF SQL%found THEN
 12  dbms_output.put_line('Record Deleted');
 13  ELSE
 14  dbms_output.put_line('No such customer');
 15  END IF;
 16
 17  COMMIT;
 18  END;
 19  /
Enter value for id: 2
old   7: e_id:=&id;
new   7: e_id:=2;
Record Deleted

PL/SQL procedure successfully completed.
```

## Explicit Cursors

Explicit cursors are those cursors which are created by the user in SQL Server.

The basic structure of explicit cursor is:

```sql
CURSOR C1 IS
OPEN C1
FETCH C1 INTO 
CLOSE C1
```

So, taking example.

```sql
DECLARE

e_id Employee.id%type;
e_name Employee.name%type;

CURSOR C1 IS
Select id,name from Employee;

BEGIN

OPEN C1;

LOOP
FETCH C1 INTO e_id,e_name;
EXIT WHEN C1%notfound;
dbms_output.put_line(e_id||' '||e_name);
END LOOP;
CLOSE C1;

END;
/

```

Output:

```text
SQL> DECLARE
  2
  3  e_id Employee.id%type;
  4  e_name Employee.name%type;
  5
  6  CURSOR C1 IS
  7  Select id,name from Employee;
  8
  9  BEGIN
 10
 11  OPEN C1;
 12
 13  LOOP
 14  FETCH C1 INTO e_id,e_name;
 15  EXIT WHEN C1%notfound;
 16  dbms_output.put_line(e_id||' '||e_name);
 17  END LOOP;
 18  CLOSE C1;
 19
 20  END;
 21  /
1 Debasish
2 Vineet
4 Parthajeet

PL/SQL procedure successfully completed.
```

