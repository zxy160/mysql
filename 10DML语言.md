# DML语言
>数据操作语言：  
>插入：insert  
>修改：update  
>删除：delete  

## 一，插入语句
>语法：  
>方式1：  
>insert into 表名（列名，。。。） values(值1，。。。);  
>方式2：  
>insert into  表名  
>set 列名=值，列名=值，。。

#### 1.插入的值的类型要与列的类型一致或兼容  
insert into beauty(id,name,sex，phone)  
values(13,'唐艺昕','女'，NULL)  
#### 2.不可以为null的列必须插入值，也可以这一列不写
insert into beauty(id,name,sex)  
values(13,'唐艺昕','女')  
#### 3.列的顺序可以调换 
insert into beauty(name,id,sex)  
values('唐艺昕',13,'女')  
####  4.列数和值的个数必须一致
####  5.可以省略列名，默认所有列，而且列的顺序和表中列的顺序一致

### 两种方式大PK
1.方式1支持插入多行，方式二不支持  
2.方式1支持子查询，方式2不支持  
INSERT INTO girl(name,phone)  
SELECT 'zqw','1234';  
## 二，修改语句
>1.修改单表的记录  
>语法：  
>update 表名  
>set 列=新值，列=新值。。。。  
>where 筛选条件；
>
>2.修改多表的记录【补充】  
>语法：  
>sql92语法
>update 表1 别名，表2 别名  
>set 列=值，，，，  
>where 连接条件    
>and 筛选条件；  
>
>sql99语法  
>update 表1 别名，表2 别名  
>inner|left|right join 表2 别名  
>on 连接条件  
>set 列=值，，，  
>where 筛选条件  

## 三，删除语句
>方式一：delete  
>语法：  
>1，单表的删除
>delete from 表名 where 筛选条件  
>2，多表的删除【补充】  
>方式二：truncate   
>语法：truncate table 表名  

案例：将魅力值>100的男神信息删除  
truncate table boys;  
**不能加where，一删就全删**

### delete pk truncate
1.delete可以加where，truncate不能加   
2.truncate删除，效率高一点
3.假如要删除的表中有自增长列    
如果用delete删除后，再插入数据，自增长列的值从断点开始，    
而truncate删除后，再插入数据，自增长列的值从1开始  
4.truncate删除没有返回值，delete删除有返回值   
5.truncate删除不能回滚，delete删除能回滚