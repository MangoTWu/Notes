# 2. 模拟登录 hub 系统查询成绩

##### 首先找到向哪一个 url 发起了登录请求。

在 chrome 的开发者工具里打开 network 监听所有请求，点击登录后直接查找请求方法（Method）为 post，状态码（Status）为302的请求，找到一个 name 为 hublogin.action 的请求，点击查看：

![1541840009313](/home/wuxie/.config/Typora/typora-user-images/1541840009313.png)

![1541840060348](/home/wuxie/.config/Typora/typora-user-images/1541840060348.png)

在响应头（Response Headers）里发现两个 Set-Cookie ，其设置了包含登录状态的 cookie。

表单数据（Form Data）包含了 post 请求提交的数据，但我们发现 **密码（password）是被加密后再传输的，所以要想直接使用密码来发起请求行不通，必须知道密码加密的方式，目前还未找到解决方法。** 

上面的请求确认了我们的登录状态，并设置了 Cookie，之后客户端携带该 Cookie 再次向网站发起请求进入教学信息服务平台的页面，在开发者工具里找到该请求：

![1541840741020](/home/wuxie/.config/Typora/typora-user-images/1541840741020.png)

这次请求返回的响应就是带有登录状态的响应了，成功获取了登录后的页面。

**目前模拟登录的方法是直接携带该 Cookie 向服务平台发起 get 请求**：

```python
import requests

login_url = 'http://hubs.hust.edu.cn/hub.jsp
login_headers = {
    'Cookie': 'username=U201613630; JSESSIONID=0000rtBqcPqLXXAQeEORJJOpcbB:166nac9ai',
    'User-Agent': 'Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/69.0.3497.100 Safari/537.36'
}
```

**hub 系统的登录请求，有时候是 hub.jsp，hublogin.action；有时候没有这两个，而是 hustpass.action**

**突然想起，监听到的请求应该是按照请求的顺序来排序的，所以 Set-Cookie 和 请求头里携带 Cookie 的顺序也就明了了。**