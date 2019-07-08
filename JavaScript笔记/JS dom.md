# <font size=6px>js的bom对象</font>

<font size= 3px>

## dom: document object model: 文档对象模型

### 文档: 
    超文本文档(超文本标记文档) html/xml

### 对象:
    提供了属性和方法

### 模型:
    使用属性和方法操作超文本标记型文档

#### 可以使用js里面的dom里面提供的对象，使用这些对象的属性和方法，对标记型文档进行操作

- 需要把html里面的标签、属性、文本内容都封装成对象

DOM模型有三种:

    DOM level 1: 将html文档封装成对象
    DOM level 2: 在level 1的基础上添加新的功能,例如: 对于事件和css样式的支持。
    DOM level 3：支持xml1.0的一些新特性。

#### DHTML： 是很多技术的简称
- HTML：封装数据
- css：使用属性和属性值设置样式
- dom：操作html文档（标记型文档）
- JavaScript： 专门指的是js的语法语句（ECMAScript）

### document对象

#### - 表示整个文档

#### 常用方法
- write()方法：
    (1)向页面输出变量(值)
    (2)向页面输入html代码
    ```js
    var str = "abc";
    document.write(str);
    document.write("<hr/>");
    ```
- getElementById();
    通过id得到元素(标签)