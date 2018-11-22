# 元素分类

html中的标签元素大体被分为三种不同的类型

- 常见的块状元素

`<div>、<p>、<h1>...<h6>、<ol>、<ul>、<li>、<dl>、<table>、<address>、<blockquote>、<form>`

- 常见的内联元素

`<a>、<span>、<br>、<i>、<em>、<strong>、<label>、<q>、<var>、<cite>、<code>`

- 常见的内联块状元素

`<img>、<input>`

# 块级元素

块级元素特点

- 每个块级元素都从新的一行开始，并且其后的元素也另起一行
- 元素的高度、宽度、行高以及顶和底边距都可设置
- 元素宽度在不设置的情况下，是它本身父容器的100%（和父元素的宽度一致），除非设定一个宽度

将内联元素转换为块状元素

```css
a{display:block;}
```

# 内联元素

内联元素特点

- 和其他元素都在一行上
- 元素的高度、宽度及顶部和底部边距不可设置
- 元素的宽度就是它包含的文字或图片的宽度，不可改变

将块状元素转换为内联元素

```css
div{display:inline;}
```

# 内联块状元素

内联块状元素特点

- 和其他元素都在一行上
- 元素的高度、宽度、行高以及顶和底边距都可设置

# 盒模型--边框

盒模型的边框就是围绕着内容和补白的线，可以设置它的粗细、样式和颜色

```css
div{border: 2px solid red;}
```

上面是`border`代码的缩写形式，可以分开写

```css
div{
    border-width: 2px;
    border-style: solid;
    border-color: red;
}
```

只为一个方向设置边框

```css
div{
    border-bottom: 1px solid red; /*下边框*/
    border-top: 1px solid red; /*上边框*/
    border-right: 1px solid red; /*右边框*/
    border-left: 1px solid red; /*左边框*/
 }
```

# 盒模型--宽度和高度

css内定义的宽`width`和高`height`指的是填充`padding`以里的内容的大小

元素实际宽度（盒子宽度）=左边界`margin-left`+左边框`border-left`+左填充`padding-left`+内容宽度`width`+右填充`padding-right`+右边框`border-right`+右边界`margin-right`

元素的高度同理

# 盒模型--填充

元素的内容与边框之间的距离称为填充

```css
div{padding: 20px 10px 15px 30px;}
```

顺序是上、右、下、左（顺时针）

也可以分开写

```css
div{
    padding-top: 20px;
    padding-right: 10px;
    padding-bottom: 15px;
    padding-left: 30px
}
```

如果上、右、下、左都一样，可以这么写

```css
div{padding: 10px;}
```

如果上下填充都为10px，左右填充都为20px，可以这么写

```css
div{padding: 10px 20px;}
```

# 盒模型--边界

不同元素之间的距离使用边界`margin`来设置

```css
div{margin: 20px 10px 15px 30px;}
```

顺序是上、右、下、左（顺时针）

分开写

```css
div{
    margin-top: 20px;
    margin-right: 10px;
    margin-bottom: 15px;
    margin-left: 30px;
}
```

如果上下左右边界都一样，可以这么写

```css
div{margin: 10px;}
```

如果上下都为20px，左右都为10px，可以这么写

```css
div{margin: 20px 10px;}
```













