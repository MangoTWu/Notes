# 继承

有些可以继承，比如

```css
p{color:red;}
```

```html
<p>三年级时，我还是一个<span>胆小如鼠</span>的小女孩。</p>
```

`p`标签的红色会继承到`span`中

有些不可以继承，比如

```css
p{border:1px solid red;}
```

```html
<p>三年级时，我还是一个<span>胆小如鼠</span>的小女孩。</p>
```

这一段仅仅给`p`标签设置了边框，没有继承到`span`





# 特殊性

标签的权值为1，类选择符的权值为10，ID选择符的权值最高为100

```css
p{color:red;} /*权值为1*/
p span{color:green;} /*权值为1+1=2*/
.warning{color:white;} /*权值为10*/
p span.warning{color:purple;} /*权值为1+1+10=12*/
#footer .note p{color:yellow;} /*权值为100+10+1=111*/
```

还有一个权值比较特殊--继承也有权值但很低，有的文献提出它只有0.1，所以可以理解为继承的权值最低





# 层叠

当有相同权重的样式存在时，会根据这些css样式的前后顺序来决定，处于最后面的css样式会被应用

```css
p{color:red;}
p{color:green;
```

```html
<p class="first">三年级时，我还是一个<span>胆小如鼠</span>的小女孩。</p>
```

后面的样式会覆盖前面的样式，最后 p 中的文本会设置为green

css样式优先级（在嵌入式样式表之前引入外部样式表的情况下）：

内联样式表（标签内部）> 嵌入样式表（当前文件中）> 外部样式表（外部文件中）





# 重要性

为某些样式设置最高权值

```css
p{color:red!important;}
```

`!important`要写在`;`前面



# 