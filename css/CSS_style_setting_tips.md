# 水平居中

## 行内元素

如果被设置元素是文本、图片等行内元素时，水平居中是通过给父元素设置`text-align: center`来实现的

```css
.TextCenter{
    text-align: center;
}
```

```html
<body>
	<div class="TextCenter">在容器中居中显示</div>
</body>
```

上面的代码中，`div`标签就是文本的父元素，反之文本是`div`的子元素

## 定宽块状元素

定宽块状元素指的是块状元素的宽度`width`为固定值。对于这种元素，设置`margin`的左右值为`auto`来实现水平居中

```css
div{
    width: 200px;
    margin: 20px auto;
}
```

```html
<div>定宽块状元素水平居中</div>
```

## 不定宽块状元素

宽度`width`不固定的块状元素叫做不定宽块状元素，有三种方法居中

- 加入`table`标签

  因为`table`标签具有长度自适应性（即不定义其长度也不默认父元素`body`的长度，`table`长度根据其内文本长度决定）

  先为需要设置的居中的元素外面加入`table`标签（包括`<tbody>、<tr>、<td>`

  再为这个`table`设置`margin`左右居中

  ```css
  table{margin: 0 auto;}
  ```

  ```html
  <table>
      <tbody>
          <tr><td>
  		    <div>需要居中的不定宽块状元素</div>
  		</tr></td>
      </tbody>
  </table>
  ```

- 改变块级元素为行内元素

  ```css
  .container{
  	display: inline; /*改变为行内元素*/
      text-align: center; /*实现居中*/
  }
  ```

  ```html
  <div id="container">块状元素要居中，而不是文本内容</div>
  ```

  虽然比上一次方法有了不用增加无语义标签的优势，但将块状元素改为行内元素后，导致比如设置长度的一些功能不能再使用

- 设置浮动和相对定位实现

  通过给父元素设置`float`，然后给父元素设置`position: relative`和 `left: 50%`，子元素设置 `position: relative`和`left: -50%`来实现水平居中

  可以这样理解：假想`ul`层的父层（即下面例子中的`div`层）中间有条平分线将`ul`层的父层（`div`层）平均分为两份，`ul`层的CSS代码是将`ul`层的最左端与`ul`层的父层（`div`层）的平分线对齐；而`li`层的CSS代码则是将`li`层的平分线与`ul`层的最左端（也是`div`层的平分线）对齐，从而实现`li`层的居中

  ```css
  .container{
      float:left;
      position:relative;
      left:50%
  }
  
  .container ul{
      list-style:none;
      margin:0;
      padding:0;
      
      position:relative;
      left:-50%;
  }
  .container li{float:left;display:inline;margin-right:8px;}
  ```

  ```html
  <body>
  <div class="container">
      <ul>
          <li><a href="#">1</a></li>
          <li><a href="#">2</a></li>
          <li><a href="#">3</a></li>
      </ul>
  </div>
  </body>
  ```

# 垂直居中

## 父元素高度确定的单行文本

父元素高度确定的单行文本的竖直居中的方法是通过设置父元素的`height`和`line-height`高度一致来实现的。（`height`为该元素的高度，`line-height`行高（行间距），指在文本中，行与行之间的基线间的距离）

`line-height`与`font-size`的差值，在CSS中成为行间距。行间距分为两半，分别加到一个文本行内容的顶部和底部

```css
.container{
    height: 100px;
    line-height: 100px;
}
```

```html
<div class="container">垂直居中文本</div>
```

## 父元素高度确定的多行文本

父元素高度确定的多行文本、图片等的竖直居中的方法有两种

- 使用插入`table`（包括`tbody、tr、td`）标签，同时设置`vertical-align: middle`

  CSS中有一个用于竖直居中的属性`vertical-align`，在父元素设置此样式时，会对`inline-block`类型的子元素都有用

  ```css
  table td{
  	height: 500px;
  	background: #ccc
  	}
  ```

  ```html
  <body>
  	<table>
          <tbody>
              <tr><td class="wrap">
                  <div>
                      <p>看我是否可以居中。</p>
                  </div>
              </td></tr>
          </tbody>
      </table>
  </body>
  ```

  因为`td`标签默认情况下设置了`vertcal-align: middle`，所以不需要显式地设置

- 设置块级元素`display: table-cell`（设置为表格单元显示）

  适用于chrome、firefox及IE8以上浏览器，可激活`vertical-align`属性

  ```css
  .container{
      height: 300px;
      background: #ccc;
      display: table-cell;/*IE8以上及Chrome、Firefox*/
      vertical-align: middle;/*IE8以上及Chrome、Firefox*/
  }
  ```

  ```html
  <div class="container">
      <div>
          <p>看我是否可以居中。</p>
      </div>
  </div>
  ```

# 隐性改变`display`类型

当为元素（`display: none`除外）设置以下属性之一时

- `position: absolute`
- `float: left`或`float:right`

出现以上代码之一时，元素的`display`显示类型就会自动转变为`display: inline-block`（内联块状元素）的方式显示







