# CSS布局模型

CSS包含3种基本的布局模型

- 流动模型（Flow）
- 浮动模型（Float）

- 层模型（Layer）

# 流动模型

流动（Flow）是默认的网页布局模式，有2个典型的特征

- 块状元素都会在所处的包含元素内自上而下按顺序垂直延伸分布，因为默认情况下块状元素的宽度为100%。
- 内联元素都会在所处的包含元素内从左到右水平分布显示

# 浮动模型

任何元素在默认情况下不能浮动，但可以用CSS定义为浮动，实现并排显示

下面实现了左浮动并排显示

```css
div{
    float: left;
}
```

```html
<div id="div1"></div>
<div id="div2"></div>
```

也可以实现右浮动并排显示

```css
div{
    float: right;
}
```

```html
<div id="div1"></div>
<div id="div2"></div>
```

也可以设置两个元素一左一右浮动来实现一行显示

```css
#div1{float: left;}
#div2{float: right;}
```

```html
<div id="div1"></div>
<div id="div2"></div>
```

# 层模型

CSS定义了一组定位属性（positioning）来支持层布局模型，层模型有三种形式

- 绝对定位`position: absolute`
- 相对定位`position: relative`
- 固定定位`position: fixed`

## 层模型--绝对定位

为元素设置层模型中的绝对定位，先设置`position: absolute`，这条语句的作用将元素从文档流中拖出来，然后使用`left、right、top、bottom`属性相对于其最接近的一个具有定位属性的父包含块进行绝对定位。如果不存在这样的包含块，则相对于`body`元素，即相对于浏览器窗口

下面代码可实现元素相对于浏览器窗口向右移动100px，向下移动50px

```css

```

## 层模型--相对定位

设置`position: relative`实现相对定位。相对定位完成的过程是首先按static`float`方式生成一个元素（并且元素像层一样浮动了起来），然后相对于以前的位置移动，移动的方向和幅度由`left、right、top、bottom`属性确定。偏移前的原位置保持不动，即不会被其他内容直接覆盖掉

## 层模型--固定定位

设置`position: fixed`实现固定定位。固定定位与绝对定位类似，但它的相对移动的坐标是视图（屏幕内的网页窗口）本身。由于视图本身是固定的，它不会随浏览器窗口的滚动条滚动而变化，因此固定定位的元素会始终位于浏览器窗口内视图的某个位置，不会受文档流动影响，这与`background-attachment: fixed`属性功能相同

## Relative和Absolute组合使用

相对与其它元素来进行定位，使用`position: relative`实现，需要遵守下面这些规范

- 参照定位的元素必须是相对定位元素的前辈元素
- 参照定位的元素必须加入`position: relative`
- 定位元素加入`position: absolute`，便可以使用`top、bottom、left、right`来进行偏移定位

比如

```css
#box1{position: relative;}
#box2{
    position: absolute;
    top: 20px;
    right: 10px;
}
```

```html
<div id="box1"><!--参照定位的元素-->
	<div id="box2"><!--相对定位元素--></div>
</div>
```





























