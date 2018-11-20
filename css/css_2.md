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