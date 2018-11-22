# 水平居中设置

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
















