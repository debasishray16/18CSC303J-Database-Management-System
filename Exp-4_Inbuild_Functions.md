# SQL Inbuild Functions

```sql
CREATE TABLE student1(id NUMBER(10),name VARCHAR2(10) NOT NULL,department VARCHAR2(10), mark1 NUMBER(10), mark2 NUMBER(10),mark3 NUMBER(10));
```

```text
SQL> select * from student1;

        ID NAME       DEPARTMENT      MARK1      MARK2      MARK3
---------- ---------- ---------- ---------- ---------- ----------
       100 aaa        cse                90         89         95
       101 bbb        cse                88         89         90
       102 ccc        cse                90         88         87
       103 ddd        cse                75         80         85

```

```sql
select count(*) from student1;
select count(department) as 'No_of_Dept' from student1;
select count(department) from student1 where department='ece';
```

```sql
select min(mark1+mark2) from student1;
select max(mark1+mark2) from student1;
select avg(mark1) from student1;

```

```sql
select sum(mark1) from student1;
select sum(mark2) from student1;
select sum(mark3) from student1;
select sum(mark1+mark2) from student1;
select sum(mark2+mark3) from student1;
select sum(mark3+mark1) from student1;
```
