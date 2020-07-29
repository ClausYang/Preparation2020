# Chapter 4 返回结果的HTTP状态码

- 状态码：客户端向服务端发送请求，描述返回的请求结果。

  - 状态码第一位制定响应类别，后两位无分类

  |      | 类别          | 原因短语                   |
  | ---- | ------------- | -------------------------- |
  | 1xx  | Informational | 接收的请求正在处理         |
  | 2xx  | Success       | 正常处理                   |
  | 3xx  | Redirection   | 需要进行附加操作已完成请求 |
  | 4xx  | Client Error  | 服务器无法处理请求         |
  | 5xx  | Server Error  | 服务器处理请求出错         |

  - 14个状态码
    - 2xx 成功
      - 200 OK：在服务器端正常处理
      - 204 Not Content：请求处理成功，返回值没有实体的主体部分，往往网页不会更新
      - 206 Partial Content：客户端进行范围请求，服务器成功执行
    - 3xx 重定向
      - 301 Moved Permanently：永久性重定向，表示资源已经被分配到新的URI，会更新书签
      - 302 Found：临时重定向，不会更新书签
      - 303 See Other：表示请求的资源存在另一个URI，应使用GET获取资源
      - 304 Not Modified：服务器允许访问资源但是没找到符合条件的
      - 307 Temporary Redirect：临时重定向，类似302，但是不会强行将POST改成GET
    - 4xx 客户端错误
      - 400 Bad Request：请求报文中存在语法错误
      - 401 Unauthorized：需要认证，第一次返回认证界面，第二次则返回认证失败
      - 403 Forbidden：请求资源被拒绝
      - 404 Not Found：无法找到资源
    - 5xx 服务器错误
      - 500 Internal Server Error：服务器端在执行请求时出错
      - 503 Service Unavailable：服务器超负载或在维护，现在无法处理请求