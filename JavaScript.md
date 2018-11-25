# 1. 基本使用

## 1.1 插入JS代码

- 直接加入在html中

  在`<script>`标签中写入JavaScript代码

  ```html
  <script type="text/javascript"></script>
  ```

- 外部引用

  在HTML中添加如下代码引用外部JS文件

  ```html
  <script src="path/script.js"></script>
  ```

一般将JS代码放在HTML的`head`部分，进行页面显示初始化的JS就必须放在`head`中；放在`body`部分，JS代码在网页读取到该语句的时候就会执行

## 1.2 语句和符号

JS的一条语句以分号`;`结尾

## 1.3 注释方法

单行注释使用`//`，多行注释使用`/*多行注释内容*/`

## 1.4 变量

定义变量使用关键字`var`，如

```javascript
var 变量名
```

注意事项

- 变量先声明后赋值，保证规范，可以在声明时就赋值
- 变量名区分大小写，必须以字母、下划线或者美元符`$`开始，之后可使用这三种字符加上数字的任意组合
- 不能使用JS关键词与保留字

## 1.5 判断语句

使用`if...else`语句来执行特定条件下的语句，语法如下

```js
if(condition)
{ run the code while condition is true }
else
{ run the code while condition is not true}
```

## 1.6 函数

定义一个函数的语法

```javascript
function 函数名()
{
    函数语句;
}
```

函数定义后，在需要使用到的地方写`函数名()`调用即可

# 2. 常用方法

## 2.1 输出内容

`document.write()`可直接向HTML输出内容，语法如下

- 直接输出双引号`""`包含的内容

  ```javascript
  document.write("I love JS!");
  ```

- 使用变量输出内容

  ```javascript
  var str="Hello World!";
  document.write(str);
  ```

- 输出多项内容的组合，使用加号`+`连接

  ```javascript
  var str="mango";
  document.write("My name is " + str);
  ```

- 输出HTML标签，用双引号`""`包围

  ```javascript
  document.write("<br>");
  ```

## 2.2 弹出消息框

- 使用`alert`实现弹出小窗口（包含一个`确定`按钮）消息

  ```javascript
  alert(字符串或变量);
  ```

  在弹出对话框后，要点击`确定`才能进行其它操作

- 使用`confirm`弹出对话框（包含一个`确定`和一个`取消`按钮）

  ```javascript
  confirm(str);
  ```

  根据用户点击，会返回布尔值`true`或`false`

  同样，需要点击按钮后才能进行其它操作

- 使用`prompt`弹出对话框（包含`确定`、`取消`按钮和文本输入框）

  ```javascript
  prompt(str1, str2);
  ```

  `str1`是显示在消息框中的内容，不可修改；`str2`是文本框中的内容，可以修改

  点击`确定`按钮，文本框中的内容将作为函数返回值；点击`取消`按钮，将返回`null`

  没有点击按钮前不能进行其它操作

## 2.3 打开新窗口

`open`方法可以查找一个存在的或者新建浏览器窗口

```javascript
window.open(URL, 窗口名称, 参数字符串)
```

参数说明

- URL：可选参数，在窗口中要显示的网页的网址或者路径。如果为空或省略，那么窗口不显示任何内容
- 窗口名称：可选参数，被打开窗口的名称。若使用特殊名称`_top`，则在框架网页的上部窗口中显示目标网页；使用`_blank`，则在新窗口显示目标网页；使用`_self`，则在当前窗口显示目标网页
- 参数字符串：可选参数，设置窗口参数，各参数使用逗号隔开，[查看这些参数](http://img.mukewang.com/52e3677900013d6a05020261.jpg)

## 2.4 关闭窗口

`close()`方法用来关闭窗口

```javascript
window.close(); //关闭当前窗口
```

或者

```javascript
窗口对象.close(); //关闭指定窗口
```

如

```javascript
var new_window = window.open(url); //新的窗口对象
new_window.close();
```

# 3. DOM

## 3.1 认识DOM

文档对象模型DOM（Document Object Model）定义访问和处理HTML文档的标准方法，DOM 将HTML文档呈现为带有元素、属性和文本的树结构（节点树）

常见的三种DOM节点

- 元素节点
- 文本节点：向用户展示的内容
- 属性节点：元素属性

## 3.2 用ID获取元素

标签的属性值ID是唯一的，我们可以通过ID找到相应标签

```javascript
document.getElementById("id");
```

找到元素的话，返回`[object HTML标签名Element]`；否则返回`null`

## 3.2 改变HTML元素内容

`innerHTML`属性用于获取或替换HTML元素的内容

```javascript
Object.innerHTML
```

Object是某个元素对象

## 3.3 改变HTML样式

```javascript
Object.style.property = new_style;
```

比如改变id为pcon的元素的样式

```javascript
var ele = document.getElementById("pcon");
ele.style.color = "red";
ele.style.fontsize = "20";
```

## 3.4 显示和隐藏（display属性）

```javascript
Object.style.display = value
```

value取值（要加双引号`"..."`）：

- none：此元素不会被显示
- block：此元素显示为块级元素

## 3.5 控制类名（className属性）

className属性可以返回或设置元素的class属性值

```javascript
Object.className = classname
```

