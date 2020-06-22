新建一个名叫student_examination_sys的数据库：

1. 新建一个名为student的表：
```
CREATE TABLE student(
  id VARCHAR2(10) NOT NULL,
  name VARCHAR2(40) NOT NULL,
  age NUMBER NOT NULL,
  sex VARCHAR2(20) NOT NULL,
  PRIMARY KEY(id)
);
```
插入数据：
```
INSERT INTO student(
  id,name,age,sex)
  values
  ('001','zhangsan',18,'male');
```
```
INSERT INTO student(
  id,name,age,sex)
  values
  ('002','lisi',20,'female');
```
![1](https://github.com/liuaaahui/sqlTest2/blob/master/screenshot/1.png)

2. 新建一个名为subject的表：
```
CREATE SEQUENCE subject_id 
INCREMENT BY 1 
START WITH 1000 
NOMAXVALUE
NOCYCLE 
NOCACHE;
```
```
CREATE TABLE subject(
  id NUMBER NOT NULL,
  subject VARCHAR2(20) NOT NULL,
  teacher VARCHAR2(30) NOT NULL,
  description VARCHAR2(255) NOT NULL,
  PRIMARY KEY(id)
);
```
插入数据：
```
INSERT INTO subject(
  id,subject,teacher,description)
  values
  (subject_id.NEXTVAL,'Chinese','Mr. Wang','the exam is easy');
```
```
INSERT INTO subject(
  id,subject,teacher,description)
  values
  (subject_id.NEXTVAL,'math','Miss Liu','the exam is difficult');
```
![2](https://github.com/liuaaahui/sqlTest2/blob/master/screenshot/2.png)

3. 新建一个名为score的表：
```
CREATE SEQUENCE score_id 
INCREMENT BY 1
START WITH 1
NOMAXVALUE 
NOCYCLE 
NOCACHE;
```
```
CREATE TABLE score(
  id NUMBER NOT NULL,
  student_id VARCHAR2(10) NOT NULL,
  subject_id NUMBER NOT NULL,
  score FLOAT NOT NULL,
  PRIMARY KEY(id)
)SEGMENT CREATION IMMEDIATE;
```
插入数据：
```
INSERT INTO score(
  id,student_id,subject_id,score)
  values
  (score_id.NEXTVAL,'001',1001,80);
```
```
INSERT INTO score(
  id,student_id,subject_id,score)
  values
  (score_id.NEXTVAL,'002',1002,60);
```
```
INSERT INTO score(
  id,student_id,subject_id,score)
  values
  (score_id.NEXTVAL,'001',1001,70);
```
```
INSERT INTO score(
  id,student_id,subject_id,score)
  values
  (score_id.NEXTVAL,'002',1002,60.5);
```
![3](https://github.com/liuaaahui/sqlTest2/blob/master/screenshot/3.png)
