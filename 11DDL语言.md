# DDl语言
>数据定义语言  
>库和表的管理  
>一，库的管理  
>二，表的管理
>
>创建，修改，删除  
>创建：create  
>修改：alter  
>删除：drop  

##  一，库的管理
### 1，库的创建  
>语法：   
>create database 【if not exists】库名；

### 2.库的修改
更改库的字符集  
alter database 库名 character set 字符集；
### 3.库的删除
drop database 库名；

## 二，表的管理
### 1.表的创建   
>create table 表名（  
>列名 列的类型【(长度)约束】，  
>列名 列的类型【(长度)约束】， 
>... 
>列名 列的类型【(长度)约束】  
>)  

### 2.表的修改
>1.修改列名  
>alter table 表名 change column 列名 新列名 【类型】；   
>2.修改列的类型或约束  
>alter table 表名  modify column 列名【类型】；   
>3.添加新列   
>alter table 表名 add column 列名；  
>4.删除列     
>alter table 表名 drop column  列名；  
>5.修改表名  
>alter table 表名 rename to 新表名；

## 三。表的删除
>drop table if  exists表名；

## 四，表的复制
>1.仅仅复制表的结构   
>create table 新表 like 旧表；
>
>2.复制表的结构+数据  
>create table 新表名  
>select *  from 旧表名；
>
>只复制部分结构  
CREATE TABLE 表名  
SELECT id  
FROM table_name;  
where 条件；
   
>仅仅复制某些字段 
CREATE TABLE 新表  
SELECT id  
FROM table_name;  
where 0；