# SQL语句
[TOC]
## <font size= 5>1.什么是SQL </font>
+ SQL是`Structured Query Language(结构化查询语言)`的缩写。
+ SQL是专为数据库而建立的操作命令集,　是一种功能齐全的数据库语言。
+ 在使用它时，只需要发出“做什么”的命令，“怎么做”是不用使用者考虑的。
  
## <font size= 5>2.SQL功能分类</font>

| 语言  |   语言类型   |                功能                 |
| :---: | :----------: | :---------------------------------: |
|  DDL  | 数据定义语言 | 用来定义数据库对象:创建库,表,列等。 |
|  DML  | 数据操作语言 |      用来操作数据库表中的记录       |
|  DQL  | 数据查询语言 |            用来查询数据             |
|  DCL  | 数据控制语言 |     用来定义访问权限和安全级别      |

## <font size= 5>3.SQL数据类型</font>

+ MySQL中定义数据字段的类型对你数据库的优化是非常重要的。
+ MySQL支持所有标准SQL数据数据类型。
+ MySQL支持多种类型，大致可以分为三类
  - 数值类型
    <img src="https://github.com/a1353433900/notebook/blob/master/image/%E5%AD%97%E7%AC%A6%E4%B8%B2%E7%B1%BB%E5%9E%8B.png?raw=true" width = 600px height = 400px>
  - 字符串类型
    <img src="https://github.com/a1353433900/notebook/blob/master/image/%E6%95%B0%E5%80%BC%E7%B1%BB%E5%9E%8B.png?raw=true" width = 600px height = 400px>

  - 日期和时间类型
    <img src="https://github.com/a1353433900/notebook/blob/master/image/%E6%97%A5%E6%9C%9F%E5%92%8C%E6%97%B6%E9%97%B4%E7%B1%BB%E5%9E%8B.png?raw=true" width = 600px height = 400px>

+ 常用数据类型
  - double
    >例如double(5,2)表示最多5位，其中必须有2位小数，即最大值为999.99；
  - char
    >固定长度字符串类型； char(10)  'abc       '
  - varchar
    >可变长度字符串类型；varchar(10) 'abc'
  - text
    >字符串类型
  - blob
    >二进制类型
  - date
    >日期类型，格式为：yyyy-MM-dd
  - time
    >时间类型, 格式为: hh:mm:ss
  - datetime
    >日期时间类型 yyyy-MM-dd hh:mm:ss

+ <font size=4 color=red>在mysql中，字符串类型和日期类型都要用单引号括起来。'xybh' '2020-01-01'</font>

## <font size= 5>4.DDL</font>
### <font size= 4>创建数据库</font>
  - <font size = 2>CREATE DATABASE 数据库名 CHARACTER SET utf8;</font>
### <font size= 4>修改数据库</font>
  - <font size = 2>ALTER DATABASE 数据库名 CHARACTER SET gbk;</font>
### <font size= 4>创建学生表</font>
  <img src='https://github.com/a1353433900/notebook/blob/master/image/%E5%88%9B%E5%BB%BA%E8%A1%A8.png?raw=true' width = 300px height = 300px>
  <img src='https://github.com/a1353433900/notebook/blob/master/image/%E5%AE%9A%E4%B9%89%E8%A1%A8.png?raw=true ' width = 300px height = 300px>
### <font size= 4>添加一列</font>
  - <font size = 2>ALTER TABLE 表名 DROP 字段名;</font>
### <font size= 4>查看表的字段信息</font>
  - <font size = 2>DESC 表名;</font>
### <font size= 4>修改一个表的字段类型</font>
  - <font size = 2>ALTER TABLE 表名 MODIFY 字段名 数据类型; </font>  
### <font size= 4>删除一列</font>
  - <font size = 2>ALTER TABLE 表名 DROP 字段名;</font>
### <font size= 4>修改表名</font>
  - <font size = 2>RENAME TABLE 原始表名 TO 要修改的表名;</font>
### <font size= 4>查看表的创建细节</font>
  - <font size = 2>SHOW CREATE TABLE 表名;</font>
### <font size= 4>修改表的字符集为gbk</font>
  - <font size = 2>ALTER TABLE 表名 CHARACTER SET 字符集名称;</font>
### <font size= 4>修改表的列名</font>
  - <font size = 2>ALTER TABLE 表名 CHANGE 原始列名 新列名 数据类型;</font>
### <font size= 4>删除表</font>
  - <font size = 2>DROP TABLE 表名;  </font>

## <font size= 5>5.DML</font>
### <font size= 4>查询表中的所有数据 </font>
  - <font size = 2>SELECT * FORM 表名;</font>
- DML是对表中的数据进行增删改查的操作
### <font size= 4>插入操作</font>
> - <font size=2 color=blue>INSERT INTO 表名(列名1, 列名2...) VALUES (列值1, 列值2);</font>
> - <font size=3 color=red>注意事项:</font>
>>列名与列值的类型,个数,顺序要一一对应。<br/>
>值不要超出列定义的长度。<br/>
>插入的日期好字符一样，都使用引号括起来。<br/>
>批量插入 INSERT INTO 表名(列名1, 列名2...) VALUES(列值1, 列值2...),(列值1, 列值2);<br/>



### <font size= 4>更新操作</font>
  - UPDATE 表名 SET 列名1=列值1, 列名2=列值2。。。 WHERE 列名=值
  - 把所有学生的分数改为90
    > UPDATE students SET score=90;
  - 把姓名为zs的学生分数改为60
    > UPDATE students SET score=60 WHERE NAME='zs'; 
  - 把姓名为李四的年龄改为20和分数改为70
    > UPDATE students SET age=20,score=70 WHERE name='ls';
  - 把wc的年龄在原来基础上加1岁
    > UPDATE students SET age=age+1 WHERE name='wc;

### <font size= 4>删除操作</font>
  - DELETE FROM 表名 [WHERE 列名=值];
  - TRUNCATE TABLE 表名; 
  - DELETE与TRUNCATE的区别
    - <font size = 2>DELETE删除表中的数据, 表结构还在;删除后的数据可以找回
    - TRUNCATE删除是把表直接DROP掉, 然后再创建一个同样的新表。删除的数据不能找回。执行速度比DELETE快 </font>

## <font size= 5>6.DQL</font>

### <font size= 4>查询所有列</font>
- SELECT * FROM 表名;
### <font size= 4>结果集</font>
- 数据库执行DQL语句不会对数据进行改变, 而是让数据库发送结果集给客户端。
- 结果集
  - 通过查询语句查询出来的数据以表的形式展示我们称为这个表的虚拟结果集。存放在内存中。
  - 查询返回的结果集是一张虚拟表。
### <font size= 4>查询指定列的数据</font>
- SELECT 列名1， 列名2... FROM 表名;
### <font size= 4>条件查询</font>
- 条件查询就是在查询时给出WHERE子句, 在WHERE子句中可以使用一些运算符及关键字
- 条件查询运算符及关键字
    > =（等于）、!=（不等于）、<>（不等于）、<（小于）、<=（小于等于）、>（大于）、>=（大于等于）；

    > BETWEEN…AND；值在什么范围

    >IN(set)； 固定范围值

    >IS NULL；（为空） IS NOT NULL（不为空）   

    >AND:与 OR:或 NOT:非

- 使用
  - 查询性别为男，并且年龄为20的学生记录
 	> SELECT * FROM students WHERE gender='男' AND age=20;
  - 查询学号为1001 或者 名为zs的记录
	> SELECT * FROM students WHERE id ='1001' OR name='zs';
  - 查询学号为1001，1002，1003的记录
	> SELECT * FROM students WHERE id='1001' OR id='1002' OR 1001='1003';
	> SELECT * FROM students WHERE id  IN('1001','1002','1003');
	> SELECT * FROM students WHERE id NOT IN ('1001','1002','1003');
  - 查询年龄为null的记录
	> SELECT * FROM students WHERE age IS NULL;
  - 查询年龄在18到20之间的学生记录
	> SELECT * FROM students WHERE age>=18 AND age<=20;
	> SELECT * FROM students WHERE age BETWEEN 18 AND 20;
  - 查询性别非男的学生记录
	> SELECT * FROM students WHERE gender !='男';
  - 查询姓名不为null的学生记录
	> SELECT * FROM students WHERE  name IS NOT  NULL;