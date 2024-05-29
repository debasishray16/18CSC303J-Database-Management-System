# PL/SQL Exception Handling

Exception handling are used to handle exceptions where they are executed according to errors encountered.

## System-Defined Exception

System-Defined Exception are those exceptions where the exceptions are pre-defined by oracle database.

```text
no_data_found
too_many_rows
others
```

```sql
DECLARE
tmp VARCHAR2(10);

BEGIN

SELECT name INTO tmp FROM Employee;

EXCEPTION
WHEN too_many_rows THEN
dbms_output.put_line('too many rows present');
WHEN others THEN 
dbms_output.put_line('no data');

END;
/
```

```text
SQL> DECLARE
  2  tmp VARCHAR2(10);
  3
  4  BEGIN
  5
  6  SELECT name INTO tmp FROM Employee;
  7
  8  EXCEPTION
  9  WHEN too_many_rows THEN
 10  dbms_output.put_line('too many rows present');
 11  WHEN others THEN
 12  dbms_output.put_line('no data');
 13
 14  END;
 15  /
too many rows present

PL/SQL procedure successfully completed.
```

**Note: A temporary variable is created in this.**

To print no such employee present.

```sql
DECLARE


e_id Employee.id%type:=10;
e_name Employee.name%type;

BEGIN

SELECT id,name into e_id,e_name FROM Employee where id=e_id;
dbms_output.put_line('Name: '||e_name);
dbms_output.put_line('ID: '||e_id);

EXCEPTION
WHEN no_data_found THEN dbms_output.put_line('No such customer');
WHEN others THEN dbms_output.put_line('Error');

END;
/
```

```text
SQL> DECLARE
  2
  3
  4  e_id Employee.id%type:=10;
  5  e_name Employee.name%type;
  6
  7  BEGIN
  8
  9  SELECT id,name into e_id,e_name FROM Employee where id=e_id;
 10  dbms_output.put_line('Name: '||e_name);
 11  dbms_output.put_line('ID: '||e_id);
 12
 13  EXCEPTION
 14  WHEN no_data_found THEN dbms_output.put_line('No such customer');
 15  WHEN others THEN dbms_output.put_line('Error');
 16
 17  END;
 18  /
No such customer

PL/SQL procedure successfully completed.
```

## User-Defined Exception

User-Defined Exception are those exceptions which are created by user and are used to throw errors and values.

```sql
DECLARE
RAISE
HANDLE
```

The general syntax is:

```sql
DECLARE
temp VARCHAR2(10);
exp EXCEPTION;

BEGIN

SELECT .....
IF temp IS NULL
THEN

RAISE exp;

EXCEPTION
WHEN exp THEN dbms_output.put_line('Error');
END;
```

```sql
DECLARE
e_id Employee.id%type:=&id;

e_name Employee.name%type;
e_age Employee.age%type;

ex_invalid_id EXCEPTION;

BEGIN

if e_id<0 THEN
RAISE ex_invalid_id;
ELSE
SELECT name,age INTO e_name,e_age FROM Employee WHERE id=e_id;

dbms_output.put_line('Name: '||e_name);
dbms_output.put_line('Age: '||e_age);

END IF;

EXCEPTION
WHEN ex_invalid_id THEN dbms_output.put_line('Id should be greater than zero');
WHEN no_data_found THEN dbms_output.put_line('No such customer present');
WHEN others THEN dbms_output.put_line('Error');

END;
/
```

```text
SQL> DECLARE
  2  e_id Employee.id%type:=&id;
  3
  4  e_name Employee.name%type;
  5  e_age Employee.age%type;
  6
  7  ex_invalid_id EXCEPTION;
  8
  9  BEGIN
 10
 11  if e_id<0 THEN
 12  RAISE ex_invalid_id;
 13  ELSE
 14  SELECT name,age INTO e_name,e_age FROM Employee WHERE id=e_id;
 15
 16  dbms_output.put_line('Name: '||e_name);
 17  dbms_output.put_line('Age: '||e_age);
 18
 19  END IF;
 20
 21  EXCEPTION
 22  WHEN ex_invalid_id THEN dbms_output.put_line('Id should be greater than zero');
 23  WHEN no_data_found THEN dbms_output.put_line('No such customer present');
 24  WHEN others THEN dbms_output.put_line('Error');
 25
 26  END;
 27  /
Enter value for id: 3
old   2: e_id Employee.id%type:=&id;
new   2: e_id Employee.id%type:=3;
No such customer present

PL/SQL procedure successfully completed.
```
