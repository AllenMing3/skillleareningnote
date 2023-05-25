### HTTP
#### 常见字段
- HOST：服务器的域名
- content- length：本次回应的数据长度
- connection：客户端要求服务器使用【http 长连接】机制；connection：keep-alive
- content-type：本次数据是什么格式
- contend-encoding：数据的压缩方式。

#### 状态码： 
- 200 OK：一切正常
- 204 No Content: 成功状态码，响应头没有body数据
##### 3xx
3xx表示客户端请求的资源发生了变动，许哟啊客户端用新的URL重新发送请求获取资源，即**重定向**
- 301 Moved Permanently：永久重定向，资源已经不存在了，需改用新的 URL 来访问
- 302 Found：临时重定向，请求的资源还在，暂时需要用另一个 URL 访问
- 304 Not Modified：不具有跳转含义，表示资源未修改，重定向一存在的缓存文件。可以继续使用缓存资源
##### 4xx
4xx表示客户端发送的**报文有误**，服务器无法处理
- 400 Bad Request：客户端请求的报文有错误
- 403 Forbidden：服务器禁止访问资源
- 404 Not Found：请求的资源在服务器上不存在或未找到
##### 5xx
5xx 客户端请求的报文正确，但**服务器处理时内部发生了错误**
- 500 Internal Server Error：服务器发生了错误
- 501 Not Implemented：可客户端请求的功能还不支持
- 502 Bad Gateway：服务器作为网关或代理时返回的错误码，后端服务器发生了错误
- 503 Service Unavailable：服务器当前很忙，无法响应客户端

### TCP 和 UDP 的区别
1. 连接
- TCP 是面向连接的传输层协议，传输数据前要先建立链接; 
- UDP 是不需要连接的，即刻传输数据
2. 服务对象
- TCP 是一对一的两点服务
- UDP 支持一对一，一对多， 多对多的交互通信
3. 可靠性
- TCP 是可靠交付数据的，数据可以无差错，不丢失，不重复，按顺序到达
- UDP 是尽最大努力交付，不保证可靠交付数据。
4. 首部开销
 - TCP 20 字节
 - UDP 8 字节
5. 应用场景
- TCP：FTP 文件传输， HTTP / HTTPS
- UDP: DNS， SNMP，视频音频，广播通信
