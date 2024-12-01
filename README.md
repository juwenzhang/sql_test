### Python TCP 详解

> * 界面
>   * 界面就是实现的是我们的用来实现用户实现操作实现的可视化的界面
> * 协议
>   * 协议：就是我们的预先实现定义好的规范，就是我们实现彼此之间遵守的具备一定约束性的一套标准
>   * 网络协议：预定义好的用于网络通信的一套规范，这个协议的实现是在我们的设备之间共同遵守
>   * 为什么会出现这种协议呐？？主要还是为了我们后续的便于理解，所以说我们的网络之间实现的交流，也是需要这种规范的
>     * 来实现我们的不同的设备之间可以实现以相同的一种规范来进行交流
>     * 只要是涉及到我们的通信的设备，这些都是需要实现遵循协议来实现通讯的
>   * `TCP（Transimission Control Protocol）` 传输控制协议具有三次握手，**实现了可靠，稳定的特性，但是性能低**
>   * `UDP（User Datagram Protocol）` 用户数据包协议没有三次握手，**不稳定不可靠，性能高**（视频通话）
> * 代码

![](./images/img_01.png)

![](./images/img_02.png)

* ACK 就是应答的意思Acknowleage
* TCP 的连接是全双工模式，所以说就要求我们的实现基本的两边的同意才可以执行某种行为
  * 所以说我们的 TCP 的连接层实现断开都是需要 4 次的挥手才可以实现

> 实现我们的自动化的测试的时候，我们的实现的就是对应用层实现测试的处理



> * 实现模拟我们的客户端发送请求服务器的过程含有
>   * 建立连接 `connect`
>   * 接收/发送数据 `/recvsend`
>   * 关闭连接 `close`
> * 一个中文汉字是占用的是 三个字节
>   * 为什么是三个字节呐？？？
>   * 这个是因为我们的一个字节代表的是八位
>   * 这个时候我们的三个字节可以实现表示的范围就是 2^32 的范围的语言文字
>   * 所以说就是使用的是三个字节了
> * 启动一个 TCP 服务器分为四步
>   * 实现绑定一个 IP 地址和端口号 `bind`
>   * 等待客户端的连接 `accept` 实现返回的是我们的 **conn** 连接对象和 **addr** 连接的地址
>   * 接收/发送数据 `recv/send`
>   * 关闭连接 `close`



### Python threading 线程的使用

> [threading 进程和线程 CSDN 博客详解](https://blog.csdn.net/weixin_41662255/article/details/144112049)
>
> 首先使用的方法是: 开辟我们的 python 的运行的线程
>
> `threading.Thread(target=target_func, args=(,)).start()`
>
> 同时我们还可以为我们的线程进行添加 `join 阻塞` 来守护我们的子线程，这个时候，我们的主线程就需要等待我们的子线程运行
>
> 完后才运行主线程中的代码，运行完后直接程序结束