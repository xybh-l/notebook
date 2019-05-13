# SQL语句

### 1.什么是SQL
+ SQL是`Structured Query Language(结构化查询语言)`的缩写。
+ SQL是专为数据库而建立的操作命令集,　是一种功能齐全的数据库语言。
+ 在使用它时，只需要发出“做什么”的命令，“怎么做”是不用使用者考虑的。
  
### 2.SQL功能分类

| 语言  |   语言类型   |                功能                 |
| :---: | :----------: | :---------------------------------: |
|  DDL  | 数据定义语言 | 用来定义数据库对象:创建库,表,列等。 |
|  DML  | 数据操作语言 |      用来操作数据库表中的记录       |
|  DQL  | 数据查询语言 |            用来查询数据             |
|  DCL  | 数据控制语言 |     用来定义访问权限和安全级别      |

### 3.SQL数据类型

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

### DDL

- 创建数据库
  - <font size = 2>CREATE DATABASE 数据库名 CHARACTER SET utf8;</font>
- 修改数据库
  - <font size = 2>ALTER DATABASE 数据库名 CHARACTER SET gbk;</font>
- 创建学生表
  <img src='https://github.com/a1353433900/notebook/blob/master/image/%E5%88%9B%E5%BB%BA%E8%A1%A8.png?raw=true' width = 300px height = 300px>
  <img src='https://github.com/a1353433900/notebook/blob/master/image/%E5%AE%9A%E4%B9%89%E8%A1%A8.png?raw=true ' width = 300px height = 300px>
- 添加一列
  - <font size = 2>ALTER TABLE 表名 DROP 字段名;</font>
- 查看表的字段信息
  - <font size = 2>DESC 表名;</font>
- 修改一个表的字段类型
  - <font size = 2>ALTER TABLE 表名 MODIFY 字段名 数据类型; </font>  
- 删除一列
  - <font size = 2>ALTER TABLE 表名 DROP 字段名;</font>
- 修改表名
  - <font size = 2>RENAME TABLE 原始表名 TO 要修改的表名;</font>
- 查看表的创建细节
  - <font size = 2>SHOW CREATE TABLE 表名;</font>
- 修改表的字符集为gbk
  - <font size = 2>ALTER TABLE 表名 CHARACTER SET 字符集名称;</font>
- 修改表的列名
  - <font size = 2>ALTER TABLE 表名 CHANGE 原始列名 新列名 数据类型;</font>
- 删除表
  - <font size = 2>DROP TABLE 表名;  </font>

### DML
- 查询表中的所有数据 
  - <font size = 2>SELECT * FORM 表名;</font>
- DML是对表中的数据进行增删改查的操作
- 插入操作
> - <font size=2 color=blue>INSERT INTO 表名(列名1, 列名2...) VALUES (列值1, 列值2);</font>
> - <font size=3 color=red>注意事项</font>
<font size=2 color=blue> 
>   - 列名与列值的类型,个数,顺序要一一对应。
>   - 值不要超出列定义的长度。
>   - 插入的日期好字符一样，都使用引号括起来。
> - 批量插入 INSERT INTO 表名(列名1, 列名2...) VALUES(列值1, 列值2...),(列值1, 列值2);
</font>
- 更新操作
  - UPDATE 表名 SET 列名1=列值1, 列名2=列值2。。。 WHERE 列名=值
  - 把所有学生的分数改为90
  > UPDATE students SET score=90;
  - 把姓名为zs的学生分数改为60
  > UPDATE students SET score=60 WHERE NAME='zs'; 
  - 把姓名为李四的年龄改为20和分数改为70
  > UPDATE students SET age=20,score=70 WHERE name='ls';
  - 把wc的年龄在原来基础上加1岁
  > UPDATE students SET age=age+1 WHERE name='wc;