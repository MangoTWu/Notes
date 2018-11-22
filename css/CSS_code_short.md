# 盒模型代码简写

盒模型中的外边距`margin`、内边距`padding`、边框`border`设置上下左右四个方向的大小是按照顺时针方向的，即上、右、下、左

```css
div{
    margin: 10px 15px 12px 14px; /*上外边距10px，右外边距15px，下外边距12px，左外边距14px*/
}
```

通常有三种缩写方法

- 如果四个方向都相同，可缩写为

  ```css
  div{margin: 10px;}
  ```

- 如果`top`和`bottom`相同，`left`和`right`相同，可缩写为

  ```css
  div{margin: 10px 20px} /*上下为10px，左右为20px*/
  ```

- 如果`left`和`right`相同，可缩写为

  ```css
  div{margin: 10px 20px 30px;} /*上为10px，左右为20px，下为30px*/
  ```

# 颜色值缩写

当设置的颜色是十六进制的色彩值时，如果每两位的值相同，可以缩写一半

如将下面代码

```css
p{color: #335566;}
```

缩写为

```css
p{color: #356;}
```

# 字体缩写

字体样式的CSS样式代码也可以进行缩写，比如将下面代码

```css
body{
    font-style: italic;
    font-variant: small-caps;
    font-weight: bold;
    font-size: 12px;
    line-weight: 1.5em;
    font-family: "Microsoft Yahei", sans-serif;
}
```

可以缩写为

```css
body{
    font: italic small-caps bold 12px/1.5em "Microsoft Yahei", sans-serif;
}
```

注意

- 使用这一简写形式至少需要指定`font-size`和`font-family`属性
- 在缩写`font-size`和line-weight时两者中间要加入`/`斜杠















































