# PL/SQL Conditional and Iterative Statements

Start the server to see the output:

```mysql
set serveroutput on;
```

```mysql
DECLARE

a integer:=10;
b integer:=18;

BEGIN

dbms_output.put_line(a);
dbms_output.put_line(b);

END;
/
```

```text
SQL> DECLARE
  2  a integer:=10;
  3  b integer:=18;
  4  BEGIN
  5
  6  dbms_output.put_line(a);
  7  dbms_output.put_line(b);
  8
  9  END;
 10  /
10
18

PL/SQL procedure successfully completed.
```

## Text Execution

```mysql
DECLARE
text_data VARCHAR(200):='Hello, My name is Debasish Ray. Nice to meet you , all.';

BEGIN

dbms_output.put_line(text_data);

END;
/

```

```text
SQL> DECLARE
  2  text_data VARCHAR(200):='Hello, My name is Debasish Ray. Nice to meet you , all.';
  3
  4  BEGIN
  5
  6  dbms_output.put_line(text_data);
  7
  8  END;
  9  /
Hello, My name is Debasish Ray. Nice to meet you , all.

PL/SQL procedure successfully completed.
```

## Constant Execution

use constant before declaration.

```mysql
DECLARE

PI constant NUMBER:=3.14;
G constant NUMBER:=9.8;

BEGIN

dbms_output.put_line('Pie value: '||PI);
dbms_output.put_line('Acceleration constant: '||G);

END;
/
```

```text
SQL> DECLARE
  2
  3  PI constant NUMBER:=3.14;
  4  G constant NUMBER:=9.8;
  5
  6  BEGIN
  7
  8  dbms_output.put_line('Pie value: '||PI);
  9  dbms_output.put_line('Acceleration constant: '||G);
 10
 11  END;
 12  /
Pie value: 3.14
Acceleration constant: 9.8

PL/SQL procedure successfully completed.
```

## Arithmetic Calculation

```mysql
DECLARE

length INTEGER:=125;
breadth INTEGER:=100;
area INTEGER;

BEGIN

area:=leNgth*breadth;
dbms_output.put_line('The area is: '||area);

END;
/
```

```text
SQL> DECLARE
  2
  3  length INTEGER:=125;
  4  breadth INTEGER:=100;
  5  area INTEGER;
  6
  7  BEGIN
  8
  9  area:=length*breadth;
 10  dbms_output.put_line('The area is: '||area);
 11
 12  END;
 13  /
The area is: 12500

PL/SQL procedure successfully completed.
```

## IF/ELSE statement execution

**Note: always end if/else statement using ENFIF; at last before END**

```mysql
DECLARE
a INTEGER:=10;
b INTEGER:=20;

BEGIN

IF (a>b) THEN
dbms_output.put_line('a is greater than b');
ELSE
dbms_output.put_line('b is greater than a');

END IF;

END;
/

```

```text
SQL> DECLARE
  2  a INTEGER:=10;
  3  b INTEGER:=20;
  4
  5  BEGIN
  6
  7  IF (a>b) THEN
  8  dbms_output.put_line('a is greater than b');
  9  ELSE
 10  dbms_output.put_line('b is greater than a');
 11
 12  END IF;
 13
 14  END;
 15  /
b is greater than a

PL/SQL procedure successfully completed.
```

## CASE Statement

```mysql
DECLARE

grade CHAR(1):='A';

BEGIN

CASE grade
    WHEN 'A' THEN dbms_output.put_line('Excellent');
    WHEN 'B' THEN dbms_output.put_line('Good');
    WHEN 'C' THEN dbms_output.put_line('Bad');
END CASE;

END;
/
```

```text
SQL> DECLARE
  2
  3  grade CHAR(1):='A';
  4
  5  BEGIN
  6
  7  CASE grade
  8      WHEN 'A' THEN dbms_output.put_line('Excellent');
  9      WHEN 'B' THEN dbms_output.put_line('Good');
 10      WHEN 'C' THEN dbms_output.put_line('Bad');
 11  END CASE;
 12
 13  END;
 14  /
Excellent

PL/SQL procedure successfully completed.
```

## LOOP statement

```mysql
DECLARE

num INTEGER:=10;

BEGIN

LOOP
EXIT WHEN num>20;

dbms_output.put_line(num);
num:=num+1;

END LOOP;
END;
/
```

```text
10
11
12
13
14
15
16
17
18
19
20

PL/SQL procedure successfully completed.
```

## WHILE statement

```mysql
DECLARE
num INTEGER:=10;

BEGIN

WHILE num<=20 LOOP
dbms_output.put_line(num);

num:=num+1;

END LOOP;
END;
/
```

```text
SQL> DECLARE
  2  num INTEGER:=10;
  3
  4  BEGIN
  5
  6  WHILE num<=20 LOOP
  7  dbms_output.put_line(num);
  8
  9  num:=num+1;
 10
 11  END LOOP;
 12  END;
 13  /
10
11
12
13
14
15
16
17
18
19
20

```
