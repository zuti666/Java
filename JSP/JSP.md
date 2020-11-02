# JSP

------

[TOC]

------



# 1 B/S和C/S



# 2 Jsp组成

![](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201022094449.jpg)



![](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201022094323.png)

![](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201022095956.png)

# 3内置对象有哪些

![](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201022094539.jpg)



![](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201022094656.png)



![](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201022094734.png)

# 4转发与重定向的区别

![](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201022094828.png)

# 5request,session,pageContext,application作用范围

![](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201022095016.png)



![](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201022095023.png)

![](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201022095054.png)

![](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201022095158.png)

# 6生命周期 cookie application session

pageContext 只在当前页面

Request 一次请求

Session 会话

Application 一直有效

![](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201022095232.png)

![](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201022095318.png)

![](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201022095355.png)

# 7 Servlet 响应与请求

![](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201022095530.png)

![](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201022095603.png)

# 8  AJAx

<img src="https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201022095753.png" style="zoom:200%;" />



# 9 第三方库的使用 JSTL  EL

![](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201022095922.png)





![](https://zuti.oss-cn-qingdao.aliyuncs.com/img/20201022100014.png)

# post 和get 方法的区别

下面的表格比较了两种 HTTP 方法：GET 和 POST。

|                  | GET                                                          | POST                                                         |
| :--------------- | :----------------------------------------------------------- | :----------------------------------------------------------- |
| 后退按钮/刷新    | 无害                                                         | 数据会被重新提交（浏览器应该告知用户数据会被重新提交）。     |
| 书签             | 可收藏为书签                                                 | 不可收藏为书签                                               |
| 缓存             | 能被缓存                                                     | 不能缓存                                                     |
| 编码类型         | application/x-www-form-urlencoded                            | application/x-www-form-urlencoded 或 multipart/form-data。为二进制数据使用多重编码。 |
| 历史             | 参数保留在浏览器历史中。                                     | 参数不会保存在浏览器历史中。                                 |
| 对数据长度的限制 | 是的。当发送数据时，GET 方法向 URL 添加数据；URL 的长度是受限制的（URL 的最大长度是 2048 个字符）。 | 无限制。                                                     |
| 对数据类型的限制 | 只允许 ASCII 字符。                                          | 没有限制。也允许二进制数据。                                 |
| 安全性           | 与 POST 相比，GET 的安全性较差，因为所发送的数据是 URL 的一部分。在发送密码或其他敏感信息时绝不要使用 GET ！ | POST 比 GET 更安全，因为参数不会被保存在浏览器历史或 web 服务器日志中。 |
| 可见性           | 数据在 URL 中对所有人都是可见的。                            | 数据不会显示在 URL 中。                                      |





# 具体代码应用

## 1 登录界面


