### Create Table Command

- create table `table-name`.

```sql
create table student(
roll_no number(5) primary key,
name varchar2(30) not null,
marks number(4) deafult 0,
result varchar2(8) check (result in ('Pass', 'Fail', 'Reappear', 'RA'))
);
```

---
### Show table

- desc `table-name`.

```sql
desc student
```
==This Command will Show your table==

---
### Insert data into table

```sql
insert into student
values(&roll_no, &name, &marks, &result)
Enter value of roll_no: 101
Enter value of name: 'Rakesh Kumar'
Enter value of marks: 400
Enter value of result: 'Pass'
```

---
### Show data in table

- See all Entry of Data. `*`  means all.

```sql
select * from student
```

- See any particular row. like roll no, marks

```sql
select roll_no, marks from student
```

---
