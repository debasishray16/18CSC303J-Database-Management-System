# PL/SQL Triggers

It is a procedure that starts automatically if specified changes access to the DBMS.

Taking Example, we wanted to display the changes made before and after using some DML commands. So we use Triggers.

```sql
CREATE OR REPLACE TRIGGER display_salary_changes
BEFORE DELETE OR INSERT OR UPDATE ON Employee

FOR EACH ROW
WHEN (NEW.id>0)

DECLARE

sal_diff NUMBER;

BEGIN

sal_diff:=:NEW.salary-:OLD.salary;
dbms_output.put_line('Old Salary: '||:OLD.salary);
dbms_output.put_line('New Salary: '||:NEW.salary);
dbms_output.put_line('Salary Difference: '||sal_diff);

END;
/
```

```sql
DECLARE
total_rows NUMBER(2);

BEGIN
    UPDATE Employee
    SET Salary=Salary+10000;
    IF SQL%notfound THEN
    dbms_output.put_line('No such Employee');
    
    ELSIF SQL%found THEN
    total_rows:=sql%rowcount;

    dbms_output.put_line(total_rows||' Customer Updated');
    END IF;
END;
/

```

```text
SQL> DECLARE
  2  total_rows NUMBER(2);
  3
  4  BEGIN
  5      UPDATE Employee
  6      SET Salary=Salary+10000;
  7      IF SQL%notfound THEN
  8      dbms_output.put_line('No such Employee');
  9
 10      ELSIF SQL%found THEN
 11      total_rows:=sql%rowcount;
 12
 13      dbms_output.put_line(total_rows||' Customer Updated');
 14      END IF;
 15  END;
 16  /
Old Salary: 21000
New Salary: 31000
Salary Difference:
10000
Old Salary: 91000
New Salary: 101000
Salary Difference:
10000
2 Customer Updated

PL/SQL procedure successfully completed.
```
