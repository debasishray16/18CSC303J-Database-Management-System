# PL/SQL Functions

PL/SQL functions can be created in sql for using function features and prevents repetitive actions and statements.

```sql
CREATE OR REPLACE FUNCTION <function_name> (<variable_name> IN <datatype>,...)
RETURN <same_datatype>

IS

<variable_declaration>

BEGIN

<functions to be performed>

END;
/
```

1. For creating functions that performs addition operations.

```sql
CREATE OR REPLACE FUNCTION Addition(n1 IN NUMBER,n2 IN NUMBER)
RETURN NUMBER

IS

n3 NUMBER;

BEGIN

n3:=n1+n2;
return n3;

END;
/
```

Output:

```text
SQL> CREATE OR REPLACE FUNCTION Addition(n1 IN NUMBER,n2 IN NUMBER)
  2  RETURN NUMBER
  3
  4  IS
  5
  6  n3 NUMBER;
  7
  8  BEGIN
  9
 10  n3:=n1+n2;
 11  return n3;
 12
 13  END;
 14  /

Function created.
```

**For using the function we use:**

```sql
DECLARE
n3 NUMBER;

BEGIN

n3:=Addition(12,24);
dbms_output.put_line('Addition Function created');
dbms_output.put_line('Value: '|| n3);

END;
/
```

Output:

```text
SQL> DECLARE
  2  n3 NUMBER;
  3
  4  BEGIN
  5
  6  n3:=Addition(12,24);
  7  dbms_output.put_line('Addition Function created');
  8  dbms_output.put_line('Value: '|| n3);
  9
 10  END;
 11  /
Addition Function created
Value: 36

PL/SQL procedure successfully completed.
```

2. For creating the function that performs subtration operations

```sql
CREATE OR REPLACE FUNCTION Subtraction(n1 IN NUMBER, n2 IN NUMBER)
RETURN NUMBER

IS

n3 NUMBER;

BEGIN

n3:=n1-n2;
return n3;

END;
/
```

Output:

```text
SQL> CREATE OR REPLACE FUNCTION Subtraction(n1 IN NUMBER, n2 IN NUMBER)
  2  RETURN NUMBER
  3
  4  IS
  5
  6  n3 NUMBER;
  7
  8  BEGIN
  9
 10  n3:=n1-n2;
 11  return n3;
 12
 13  END;
 14  /

Function created.
```

**For using the function we use:**

```sql
DECLARE

n3 NUMBER;

BEGIN

n3:=Subtraction(23,10);
dbms_output.put_line('Subtraction fucntion created');
dbms_output.put_line('Value: '||n3);

END;
/
```

Output:

```text
SQL> DECLARE
  2
  3  n3 NUMBER;
  4
  5  BEGIN
  6
  7  n3:=Subtraction(23,10);
  8  dbms_output.put_line('Subtraction fucntion created');
  9  dbms_output.put_line('Value: '||n3);
 10
 11  END;
 12  /
Subtraction fucntion created
Value: 13

PL/SQL procedure successfully completed.
```

3. For creating the function that performs multiplication operations

```sql
CREATE OR REPLACE FUNCTION Multiplication(n1 IN NUMBER, n2 IN NUMBER)
RETURN NUMBER

IS

n3 NUMBER;

BEGIN

n3:=n1*n2;
return n3;

END;
/
```

Output:

```text
SQL> CREATE OR REPLACE FUNCTION Multiplication(n1 IN NUMBER, n2 IN NUMBER)
  2  RETURN NUMBER
  3
  4  IS
  5
  6  n3 NUMBER;
  7
  8  BEGIN
  9
 10  n3:=n1*n2;
 11  return n3;
 12
 13  END;
 14  /

Function created.
```

**For using the function we use:**

```sql
DECLARE
n3 NUMBER;

BEGIN

n3:=Multiplication(23,23);
dbms_output.put_line('Multiplication function created');
dbms_output.put_line('Value :'||n3);

END;
/
```

Output:

```text
SQL> DECLARE
  2  n3 NUMBER;
  3
  4  BEGIN
  5
  6  n3:=Multiplication(23,23);
  7  dbms_output.put_line('Multiplication function created');
  8  dbms_output.put_line('Value :'||n3);
  9
 10  END;
 11  /
Multiplication function created
Value :529

PL/SQL procedure successfully completed.
```

4. For creating the function that performs division.

```sql
CREATE OR REPLACE FUNCTION Division(n1 IN NUMBER, n2 IN NUMBER)
RETURN NUMBER

IS

n3 NUMBER;

BEGIN

n3:=n1/n2;
return n3;

END;
/
```

Output:

```text
SQL> CREATE OR REPLACE FUNCTION Division(n1 IN INTEGER, n2 IN INTEGER)
  2  RETURN NUMBER
  3
  4  IS
  5
  6  n3 NUMBER;
  7
  8  BEGIN
  9
 10  n3:=n1/n2;
 11  return n3;
 12
 13  END;
 14  /

Function created.
```

**For using the function we use:**

```sql
DECLARE

n3 NUMBER;

BEGIN

n3:=Division(23,12);
dbms_output.put_line('Division function created');
dbms_output.put_line('Value: '||n3);

END;
/
```

Output:

```text
SQL> DECLARE
  2
  3  n3 NUMBER;
  4
  5  BEGIN
  6
  7  n3:=Division(23,12);
  8  dbms_output.put_line('Division function created');
  9  dbms_output.put_line('Value: '||n3);
 10
 11  END;
 12  /
Division function created
Value: 1.91666666666666666666666666666666666667

PL/SQL procedure successfully completed.
```
