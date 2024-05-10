# Entity Relationship Model

Entity Relationship Model gives a way of identifying the whole structure of the database directly with the involvement of attributes and relationships.

```sql
CREATE TABLE Marks (Mark_ID NUMBER(10) PRIMARY KEY NOT NULL ,Student_ID NUMBER(10) NOT NULL,Subject_ID NUMBER(10) NOT NULL,Date_time VARCHAR2(10) NOT NULL,Mark NUMBER(10) NOT NULL);

CREATE TABLE Subjects (Subject_ID NUMBER(10) PRIMARY KEY NOT NULL,Title VARCHAR2(20) NOT NULL);

CREATE TABLE Students (Student_ID NUMBER(10) PRIMARY KEY NOT NULL, Firstname VARCHAR2(20) NOT NULL, Lastname VARCHAR2(20) NOT NULL,Group_ID NUMBER(20) NOT NULL);

CREATE TABLE Teachers (Teacher_ID NUMBER(10) PRIMARY KEY NOT NULL,Firstname VARCHAR2(20) NOT NULL,Lastname VARCHAR2(20) NOT NULL);

CREATE TABLE Subj_Teach(ST_id NUMBER(10) PRIMARY KEY NOT NULL,Subject_ID NUMBER(10) NOT NULL,Teacher_ID NUMBER(10) NOT NULL,Group_ID NUMBER(20) NOT NULL);

CREATE TABLE Groups (Group_id NUMBER(20) PRIMARY KEY NOT NULL,Name VARCHAR2(40) NOT NULL);
```

Defining foreign key in each table:

```sql
ALTER TABLE Marks ADD CONSTRAINT fk_6 FOREIGN KEY (Student_ID) REFERENCES Students(Student_ID);

ALTER TABLE Marks ADD CONSTRAINT fk_7 FOREIGN KEY (Subject_ID) REFERENCES Subjects(Subject_ID);



ALTER TABLE Subj_Teach ADD CONSTRAINT fk_8 FOREIGN KEY (Subject_ID) REFERENCES Subjects(Subject_ID);

ALTER TABLE Subj_Teach ADD CONSTRAINT fk_9 FOREIGN KEY (Teacher_ID) REFERENCES Teachers(Teacher_ID);

ALTER TABLE Subj_Teach ADD CONSTRAINT fk_10 FOREIGN KEY (Group_ID) REFERENCES Groups(Group_ID);

```
