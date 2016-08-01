## 第一节内容
   几个操作
```sh
mysql -u [root] -p
show databases;
create database [DBname];
drop database [DBname];
有若干个数据库，每个数据库有若干个数据表，每个表有若干列，每个数据表有若干个数据
```
## 第二节内容
	数据结构、数据类型type
```sh
文本类：varchar、text、longtext等
数字类：tinyint、int、bigint、double等
日期类：data()、datatime()、time()等
```
## 第三节内容
	添加删除table
```sh
use [DBname]

create table account2(
id bigint(20),
createTime datetime,
ip varchar(255),
mobile varchar(255),
nickname varchar(255),
paswwd varchar(255),
username varchar(255)
);

show tables;
describe account2; 
drop table account2;
```
## 第四节内容
	给数据表增加删除数据
```sh
alter table [tablename] add [columnname] [datatype] [not null] [default];
alter table account add c1 int(11) not null defaule 1;
#给数据添加列c1 int类型，赋初值1;
alter table account drop [columnname];
```
## 第五节内容
	修改列信息和表名
```sh
列信息，改变名称数据类型
alter [table_name] change [old_column_name] [new_column_name] [data_type];
修改表名
alter table [table_name] rename [new_talbe_name];
```
## 第六节内容
	查看插入表数据
```sh
select * from [table_neme];
select [column_name1] from [table_neme];
select [column_name1],[column_name2],...from [table_neme];

insert into ac(id) values(123456789);
insert into [table_neme] values(值1,值2,...);
insert into [table_neme](列1,列2,...) values(值1,值2,...);
```
	
	
