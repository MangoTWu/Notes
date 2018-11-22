# 颜色值

设置颜色的方法有很多种

- 英文命令颜色

  ```css
  p{color: red;}
  ```

- RGB颜色

  RGB每一项的值可以是0-255之间的整数，也可以是0%-100%的百分数

  ```css
  p{color: rgb(133,45,222);}
  ```

  ```css
  p{color: rgb(20%,33%,46%);}
  ```

- 十六进制颜色

  原理也是RGB，只是每一项的值变成了十六进制数

  ```css
  p{color: #00ffff;}
  ```

# 长度值

- 像素`px`

  像素指的是显示器上的小点。实际情况是浏览器会使用显示器的实际像素值

- `em`

  就是本元素给定字体的`font-size`值，如果元素的`font-size`为`14px`，那么`1em`=`14px`

  ```css
  p{
      font-size: 12px;
      text-indent: 2em;
  }
  ```

  当给`font-size`设置单位为`em`时，此时计算的标准以父元素的`font-size`为基础，如

  ```css
  p{font-size: 14px;}
  span{font-size: 0.8em;}
  ```

  ```html
  <p>以这个<span>例子</span>为例</p>
  ```

  结果`span`标签中的字体为`11.2px`（14 * 0.8）

- 百分比

  ```css
  p{
      font-size: 12px;
      line-height: 130%;
  }
  ```

  设置行高（行间距）为字体的130%，即`15.6px`（12 * 130%）











