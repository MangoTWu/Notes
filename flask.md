# Jinja2

## 删去空行

[用以下代码可以将模板标签后第一个空行自动删去以及将模板标签前的制表符或者空格自动删去]()

```python
# 删去Jinja2语句后第一个空行
app.jinja_env.trim_blocks = True
# 删去Jinja2语句所在行之前的制表符和空格
app.jinja_env.lstrip_blocks = True 
```

## 过滤器

在书83页



# Bootstrap

书208页

render_form()渲染表单时，加入参数button_map

```html
<div class="hello-form">
    {{ render_form(form, action=request.full_path, button_map={'submit': 'primary'}) }}
</div>
```

一些bootstrap的主题资源：

[Bootswatch](https://bootswatch.com/)

[StartBootstrap](https://startbootstrap.com/)



# Faker

实例化Faker类时，传入参数可改变语言

```python
from faker import Faker
fake = Faker('zh_CN')
```

