## WebSocket
WebSocket, 是一种网络传输协议，位于**OSI**模型的应用层，可用在单个TCP连接上进行全双工通信，更好的节省服务器资源和带宽并达到实时通信

> 客户端和服务器只需要完成一次握手，两者之间就可以创建持久性的连接，进行双向传输

> 在没有WebSocket之前，web使用的方式是 **轮询**，不停的向服务器发送HTTP请求，问有没有数据，有数据服务器就会响应报文回应。如果轮询频率高，效果就类似 **实时通信**


### 特点
- 全双工： 双向传递
- 二进制帧：和HTTP完全不兼容，和HTTP2相比，WebSocket更侧重**实时通信**
- 协议名：引入 **ws**和**wss**分别代表明文和密文的websocket协议，默认端口使用 80 或 443
- 握手：WebSocket也有一个握手过程，才正式传输数据

### 优点
1. 减少开销：数据包头部信息携带较少，不同HTTP每次请求都要携带完整的头部信息
2. 实时性：http请求需要等到客户端发起请求服务端才能响应，减少延迟性
3. 保持创连接状态：创建通信后，就可以省略状态信息，不同于HTTP每次请求都需要携带验证信息
4. 二进制支持：通过二进制帧，更好处理二进制内容
5. 支持扩展： 可以扩展websocket协议、实现部分自定义子协议
6. 提高压缩率：Websocket在适当的扩展支持下，提高压缩率


### 应用场景
- 弹幕
- 媒体聊天
- 协同编辑
- 定位应用
- 实况更新、实时更新