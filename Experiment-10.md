# PL/SQL Procedures

Taking a sample SQL table

```sql
CREATE TABLE Student_data(id INTEGER(4) PRIMARY KEY NOT NULL, name VARCHAR2(10) NOT NULL, age INTEGER(2) NOT NULL,address VARCHAR2(10) NOT NULL);
```

Start the server for observing the output.

- The procedure created is "Data" where it contains attributes for inserting data into the table.

```sql
CREATE OR REPLACE PROCEDURE "Data"

(id IN INTEGER,
name IN VARCHAR2,
age IN INTEGER,
address IN VARCHAR2)

IS 

BEGIN

INSERT INTO Student_data VALUES (id,name,age,address);

END;
/
```

Output:

```text
CREATE OR REPLACE PROCEDURE "Data"
  2  (id IN INTEGER,
  3  name IN VARCHAR2,
  4  age IN INTEGER,
  5  address IN VARCHAR2)
  6
  7  IS
  8
  9  BEGIN
 10
 11
 12  INSERT INTO Student_data VALUES (id,name,age,address);
 13
 14  END;
 15  /

Procedure created.
```

To enter the data using PROCEDURE.

```sql
BEGIN

Data(1,'Debasish',21,'Delhi');
Data(2,'Vineet',19,'Delhi');
dbms_output.put_line('Record Added Successfully.');

END;
/
```

```text
SQL> BEGIN
  2  data(1,'Debasish',23,'Delhi');
  3  dbms_output.put_line('Record Added Successfully');
  4  END;
  5  /

  Record added successfully.
```

**Note: This will print the result when the data is added to table.**

