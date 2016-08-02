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
## 第七解内容
	条件查询
```sh
select * from ac where c1!=2;
select * from ac where c1=2;
select * from ac where c1>1;
select * from ac where c1!=2 or c1=1;

select * from ac where c1!=2 and idd!=123;
select * from ac where (c1!=2 and idd!=123) or c1=5;
```
## 第八节内容
		null判断 is/is not
```sh
select * from ac where gender is null;
select * from ac where idd is not null;
```
## 第九节内容
	select distinct去掉重复查找
```sh
select distinct idd from ac;
```
## 第十节内容
	select 用order by 排序
```sh
select * from ac [where 字句]order by [column_name][asc/desc];
select * from ac where c1!=0 order by idd asc, c1 desc ;
```
## 第十一节内容
	使用linit截取查询结果
```sh
select * from ac [where 字句][order by字句] limit [offset,]rowCount;
select * from ac limit 0,4;
```
## 第十二节内容
	insert into 与 select组合使用
```sh
一般用法
insert into [表名] values(值1,值2,...)
insert into [表名](列1,列2,...) values(值1,值2,...)
insert into 与select的组合用法
insert into [表名1] select 列1,列2 from [表名2]
insert into [表名1] (列1,列2) select 列3,列4 from [表2]
```
## 第十三节内容
	更新表数据
```sh
update ac set c1=1 where c1=5;
```
## 第十四节内容
	where语句中in操作符
```sh
select * from 表名 where 列名 in(valu1,value2,...)
select * from 表名 where 列名 in(select 列名 from 表名...)
select * from ac where c1 in(2);
```
## 第十五节内容
	where语句中between操作符
```sh
select * from 表名 where 列名 between 值1 and 值2
select * from 表名 where 列名 not between 值1 and 值2
```
## 第十六节内容
	where语句中like操作符
```sh
select * from 表名 where 列名 [not] like pattern
partten:匹配模式，比如'abc','%abc','%abc%'，'%'通配符可以替代任意字符串
```
