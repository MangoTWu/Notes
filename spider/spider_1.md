# 1. requests 库

## 1.1 get 请求

### 1.1.1 基本方法

首先安装 requests 库到虚拟环境中

```
pipenv install requests
```

新建 .py 脚本文件，输入以下代码后运行：

```python
import requests
url = "https://www.baidu.com"
r = requests.get(url)
if r.status_code == 200:
    print("请求成功！")
    print(r.text)
```

控制台输出“请求成功”以及网页HTML代码，表示成功发起 get 请求并得到响应



### 1.1.2 在请求中添加查询参数

直接发起带有查询参数的 get 请求的 url 如下：

```python
r = requests.get("http://example.com/get?name=shieh&age=20")
```

除了直接添加到 url 的方式，还可以使用 params 参数：

```python
data = {
	'name': 'shieh',
	'age': '22'
}

r = requests.get("http://example.com/get", params=data)
```



### 1.1.3 将 JSON 格式的转化为字典

对于返回是 str 类型的 JSON 格式的响应，使用 json() 方法转化为字典：

```python
r = requests.get(url)
r.json()
```



### 1.1.4 抓取二进制文件

对于用二进制码来存储的图片、音频、视频等文件，直接输出会显示错误，我们用二进制存储到文件的方法来查看：

```python
r = requests.get(url_of_picture)
with open('filename.img', 'wb') as f:
	f.write(r.content)
```

在这里，`r.content` 和 `r.text` 的输出内容实质是一样的，其区别在于：

- r.text 返回的是 Unicode 型的数据，用来获取文本
- r.content 返回的是 bytes 型也就是二进制的数据，用来获取图片等文件

`'wb'` 的作用是以二进制的形式将数据写入到文件



### 1.1.5 添加 headers 

需要添加 headers 的请求，用 headers 参数：

```python
headers = {
	'User-Agent': 'Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 	  (KHTML, like Gecko) Chrome/69.0.3497.100 Safari/537.36'
}
r = requests.get(url, headers = headers)
```

先将需要添加的 headers 内容以键值对形式写入字典，然后添加到参数 headers 



## 1.2 post 请求

使用 requests 库发起 post 请求的方法：

```python
data = {'name': 'shieh', 'age': '22'}
r = requests.post(url, data=data)
```

data 存放了需要提交的数据

## 1.3 获取响应信息的方法

以下代码可以对响应对象获取相关信息：

```python
r = requests.post(url)
print(r.status_code) #状态码
print(r.headers) #响应头
print(r.cookies) #Cookies
print(r.url) #URL
print(r.history) #请求历史
```

## 1.4 状态码查询

requests 库内置了状态码查询对象 requests.codes，如：

```python
requests.codes.ok #200
requests.codes.not_found #404
requests.codes.found #302
requests.codes.server_error #500
requests.codes.bad_gateway #502
```

​	