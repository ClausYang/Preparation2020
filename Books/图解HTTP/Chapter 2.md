# Chapter 2 简单的HTTP协议

- 请求报文和响应报文

  - 请求报文

    ```
    POST /form/entry HTTP/1.1
    
    HOST: hackr.jp
    Connection: keep-alive
    Content-Type: 
    Content-Length:
    
    name=ueco&age=37
    ```

    - 方法：POST/GET
    - 请求URI：`/form/entry`
    - 协议版本：HTTP/1.1
    - 请求首部字段：```HOST: hackr.jp
      Connection: keep-alive
      Content-Type: 
      Content-Length:```
    - 内容实体：`name=ueco&age=37`

  - 响应报文

    ```
    HTTP/1.1 200 OK
    Date: 
    Content-Type: 
    Content-Length:
    
    <html>
    ......
    ```

    - 协议版本：HTTP/1.1
    - 状态码：200
    - 状态码原因短语：OK
    - 响应首部字段：`Date: 
      Content-Type: 
      Content-Length:`
    - 主体：`<html>
      ......`

- HTTP是无状态协议：不保存之前的内容，引入cookie机制进行状态保存
- 请求URI：用来定位互联网上的资源，使用*来对服务器本身发起请求
- HTTP方法
  - GET：获取资源
  - POST：传输实体主体
  - PUT：传输文件，因为不带验证故较少使用
  - HEAD：获取报文首部，用于确认资源有效性和更新时间日期等
  - DELETE：删除文件，类似PUT，不带验证
  - OPTIONS：询问支持的方法
  - TRACE：追踪路径，很不常用
  - CONNECT：使用隧道协议连接代理
- HTTP持久连接（HTTP keep-alive）：任意一端没有明确提出断开连接，则保持TCP连接状态
  - 优点：减少额外开销，提高响应速度
  - 管线化：不用等待响应直接发送下一个请求
- Cookie状态管理：通过在请求和响应报文中写入Cookie信息来控制客户端状态
  
  - Cookie根据服务端发送的响应报文内的Set-Cookie的首部字段信息，客户端保存Cookie，下一次发送报文辉在里面加入Cookie信息，服务端进行比对得到之前的状态信息
  
  