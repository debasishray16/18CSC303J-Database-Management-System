# Views

Taking table :

```sql
CREATE TABLE student1(id NUMBER(10),name VARCHAR2(10) NOT NULL,department VARCHAR2(10), mark1 NUMBER(10), mark2 NUMBER(10),mark3 NUMBER(10));

INSERT INTO Student1 VALUES (&id,'&name','&department',&mark1,&mark2,&mark3);

```

To create a view with single table:

```sql
create view Viewer AS SELECT student1.name,student1.mark2 from Student1;

Select * from Viewer;
```

To create a view with multiple table:

```sql
create view Viewer1 AS SELECT Student1.name,Student1.mark2,Details.name,Details.Description from Student1 FROM Student1,Details;

Select * from Viewer1;

```

