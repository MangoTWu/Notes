# table标签

- 整个表格以 `<table>` 标签开始、 `</table>` 标签结束

- `<tbody>...</tbody>、<thead>、<tfooter>` 这些表格结构包含的内容不必等待表格加载完成后再显示，可以一块一块地显示
- `<tr>...</tr>` 表格的行
-  `<td>...</td>` 表格的单元格，一行中包含几个 `<td>...</td>` ，说明就有几列
- `<th>...</th>` 表格头部的单元格，**表格表头**
- `<caption>标题文本</caption>`
- `<table summary="表格简介文本">` 表格摘要，不显示



# a标签，加入链接

`<a  href="目标网址"  title="鼠标滑过显示的文本">链接显示的文本</a>` 

**在新建浏览器窗口中打开链接，添加**`target="_blank"`

`<a href="目标网址" target="_blank">click here!</a>`



# 插入图片

`<img src="图片地址" alt="下载失败时的替换文本" title = "提示文本">`



# 表单标签

`<form   method="传送方式"   action="服务器文件">`

**所有表单控件（文本框、文本域、按钮、单选框、复选框等）都必须放在 `<form></form>` 标签之间（否则用户输入的信息可提交不到服务器上哦！）**

```html
<form    method="post"   action="save.php">
        <label for="username">用户名:</label>
        <input type="text" name="username" />
        <label for="pass">密码:</label>
        <input type="password" name="pass" />
</form>
```



### 文本输入框、密码输入框

```html
<form>
   <input type="text/password" name="名称" value="文本" />
</form>
```

- **type**：当`type="text"`时，输入框为**文本输入框**

   当`type="password"`时,输入框为**密码输入框**

- **name**：为文本框命名，以备后台程序ASP 、PHP使用
- **value**：为文本输入框设置默认值



### 文本域，支持多行文本输入

```html
<textarea rows="行数" cols="列数">文本</textarea>
```



### 使用单选框、复选框，让用户选择

```html
<input type="radio/checkbox" value="值" name="名称" checked="checked"/>
```

- **type**： 当 `type="radio"`时，控件为**单选框**

  当 `type="checkbox"`时，控件为**复选框**

- **value**：提交数据到服务器的值（后台程序使用）

- **name**：为控件命名，以备后台程序使用

- **checked**：当设置 `checked="checked"` 时，该选项被默认选中

**同一组的单选按钮，name 取值一定要一致，这样同一组的单选按钮才可以起到单选的作用**



### 下拉列表框

```html
<form action="save.php" method="post" >
    <label>爱好:</label>
    <select>
      <option value="看书">看书</option>
      <option value="旅游">旅游</option>
      <option value="运动">运动</option>
      <option value="购物">购物</option>
    </select>
</form>
```

- **value**：向服务器提交的值
- **selected**：设置`selected="selected"`属性，则该选项就被默认选中

**使用下拉列表框进行多选**

在 `<select>` 标签中设置 `multiple="multiple"`  属性，就可以实现多选功能



### 使用提交按钮，提交数据

```html
<input type="submit" value="提交">
```

- **type**：只有当type值设置为submit时，按钮才有提交作用
- **value**：按钮上显示的文字



### 使用重置按钮，重置表单信息

当用户需要重置表单信息到初始时的状态时，比如用户输入“用户名”后，发现书写有误，可以使用`重置按钮`使输入框恢复到初始状态。只需要把type设置为"reset"就可以

```html
<input type="reset" value="重置">
```



### form表单中的label标签

label标签不会向用户呈现任何特殊效果，它的作用是为鼠标用户改进了可用性。如果你在 label 标签内点击文本，就会触发此控件。就是说，当用户单击选中该label标签时，浏览器就会自动将焦点转到和标签相关的表单控件上（就自动选中和该label标签相关连的表单控件上）

```html
<label for="控件id名称">显示内容</label>
```

**标签的 for 属性中的值应当与相关控件的 id 属性值一定要相同**

