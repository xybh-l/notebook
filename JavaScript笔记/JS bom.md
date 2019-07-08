# <font size=6px>js的bom对象<font>

<font size=5px>

- bom: browser object model：浏览器对象模型
- 有哪些对象？
  - navigator:获取客户机的信息(浏览器的信息)
    - navigator.appName
    - document.write(navigator.appName) 
  - screen: 获取屏幕的信息
    - screen.width 浏览器宽度
    - screen.height 浏览器高度
  - location: 请求url地址
    - href属性 
      - 获取到请求的url地址
        - location.href 当前浏览网址
      - 设置url地址
        - 页面上安置一个按钮, 按钮绑定一个事件, 当我点击这个按钮, 页面可以跳转到另外一个页面   
        <input type="button" value="tiaozhaun" onclick="href1()"> 
  - history:请求的url的历史记录
    - 创建三个页面
      - 1、创建第一个页面a.html 写一个超链接到b.html
      - 2、创建b.html超链接到c.html
      - 3、创建c.html
    - history.go()
    - history.back()
  -  <font color=red>window</font>
        - 窗口对象
        - 顶层对象(所用的bom对象都是在window里面操作的)
        - 方法
          - window.alert(): 页面弹出一个框,显示内容
          - window.confirm(message): 弹出一个确定或取消的页面框    
          - window.prompt(text, default): 弹出一个提示框提示用户输入 
          - window.open(url," ",窗口特征)
            - 创建一个按钮,点击这个按钮,打开一个新的窗口
            - window.open("hello.html","","width=200,height=100");
          - window.close():关闭窗口(兼容性较差)
          - 做定时器
            - setInterval(code, interval); 模拟循环执行指定代码  
            - setTimeout("js代码",毫秒数)
              - 表示在毫秒数之后执行,但是只会执行一次
            - clearInterval():清除setInterval设置的定时器
            - clearTimeout():清除setTimeout设置的定时器
