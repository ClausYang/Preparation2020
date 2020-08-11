# Chapter 7 确保Web安全的HTTPS

- HTTP的缺点

  - 通信使用明文未加密
  - 不验证对方身份
  - 无法证明报文的完整性

- HTTPS=HTTP+加密+认证+完整性保护

  - HTTPS（HTTP Secure）：添加了加密及认证机制的HTTP
  - 并非新的通信协议，只是HTTP通信接口部分用SSL（Secure Socket Layer）和TLS（Transport Layer Security）协议代替，即**身披SSl外壳的HTTP**
  - 加密技术
    - 共享密钥加密：双方使用对称密钥，加密的同时也要发送密钥
    - 公开密钥加密：双方使用非对称密钥，只传送公开密钥，解密时根据公开密钥和自己的私密密钥来进行解密
  - HTTPS采用混合加密方式
  - 公开密钥的安全性保证：使用数字证书认证机构的公开密钥证书

- HTTPS通信步骤

  - SSL协商阶段1-4（SSL第一次握手）
  - 确认密钥阶段5-9
  - HTTP传送阶段10-11

  1. 客户端发送Client Hello报文开始SSL通信，报文中包含SSL相关信息
  2. 服务器以Server Hello进行应答，应答报文中包含SSL相关信息
  3. 服务器发送Certificate报文，包含公钥证书
  4. 服务器发送Server Hello Done报文
  5. 客户端用Client Key Exchange报文回应，其中包含Pre-master secret随机密码串，已经由公开密钥加密
  6. 客户端发送Change Cipher Spec报文，提示服务器接下来通信使用Pre-master secret密钥加密
  7. 客户端发送Finished报文，以服务端是否可以正确解密此次报文为握手成功与否的标准
  8. 服务器发送Change Cipher Spec报文
  9. 服务器发送Finished报文
  10. SSL通信建立完毕，客户端发送HTTP请求
  11. 服务端返回HTTP请求
  12. 客户端断开连接，发送close_notify报文

- HTTPS使用缺点

  - 加密通信会消耗更多的CPU和内存资源，仅在需要加密的时候才会选择使用
  - 节约购买证书的开销

