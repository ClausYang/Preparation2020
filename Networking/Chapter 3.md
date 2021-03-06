# Chapter 3 数据链路层

- 数据链路层使用的信道
  - 点对点信道：一对一
  - 广播信道：一对多
- 链路：一条点到点的物理线路段
- 数据链路：实现相应协议的硬件和软件加到链路上
  - 例：网卡+物理链路=数据链路
- 帧：数据链路层传送的
- 数字链路层类似数字管道，其中传输的就是帧

## 2.三个基本问题

- 封装成帧：定义开始和结束的标记
  - 在一段数据的前后分别添加**首部和尾部**，构成一个帧
  - 首部和尾部用于确认帧的边界
  - 只有收到完整的帧才会保留
- 透明传输
  - 头和尾尽量使用不可打印的字符，防止在数据部分出现结束字符，导致提前结束传输
  - 字节填充法：在出现控制字符“SOH”或“EOT”时在其前面添加一个转义字符“ESC”，告诉计算机这里出现的不是控制字符
  - 若“ESC”作为数据内容，前面再加一个“ESC”
- 差错控制
  - 比特差错：传输过程中比特发生错误
  - 误码率：一段时间内传输错误的比特站传输总比特的比例
  - CRC：循环冗余检验方法，在数据后面增加相应位数，进行二进制除法，得到结果FCS，与数据进行拼接，然后接收端接收数据帧后进行二进制除法，看结果是否为0，表示传输无误
  - FCS：冗余码，通过CRC算出
  - CRC只能做到“无差错接受”，没有确认和重传机制

## 3.PPP协议*

- 三个部分：
  - 数据链路层协议
  - LCP（链路控制协议）建立并维护链路连接
  - NCP（网络控制协议）允许点到点连接上使用多种网络层协议
- PPP协议帧格式
  - 标志字段F：字节1:7E表示开始
  - 地址字段A：字节1:FF表示目标地址，在点对点中可不写
  - 控制字段C：字节1:03
  - 字节2:协议，标识信息部分是什么信息
  - 不超过1500字节：信息部分
  - 字节2:FCS
  - 字节1:7E表示结束
- 零比特填充法：在5个1之后插入一个0，可以防止出现标志字段F的7E在数据中出现

## 4.局域网

- 局域网：一个单位拥有的网络，地理范围和站点数目有限
  - 具有广播功能
  - 便于系统扩展
  - 提高系统可靠性

## 5.CSMA/CD协议

- 载波监听多点接入/碰撞检测
  - 多点接入：计算机以多点接入的方式连接在一根总线上
  - 载波监听：发送数据前检测总线上是否有其他计算机在发送数据，如果有则暂时先不发送数据
- 特点：
  - 半双工：双方都可以发送，但不能同时发送
- 争用期：往返时延；先发送512bit，即64字节，若没有出现冲突，则后续可以继续发数据包
- 基本退避时间：取争用期时间

## 6.以太网

- 局域网的数据链路层拆分成两个子层
  - 逻辑链路控制LLC
  - 媒体介入控制MAC（现在只有这一个）
- 以太网提供**不可靠的交付**
- 集线器：星型拓扑
  - 工作在物理层
- MAC层：硬件地址/物理地址
- 本站的帧
  - 单播帧：一对一
  - 广播帧：一对全体
  - 多播帧：一对多
- MAC帧地址
  - 目的地址：6字节
  - 源地址：6字节
  - 类型：2字节
  - 数据：46-1500字节
  - FCS：4字节
  - 前面插入一个8字节的头
- 无效的MAC帧：直接丢弃
  - 帧的长度不是整数字节
  - 帧检验序列FCS有差错
  - 数据字段长度不在46-1500之间
  - 有效的MAC帧在64-1518字节

- 网桥
  - 可以隔绝冲突，有存储转发的功能
  - 效率降低

## 7.虚拟局域网

- 局域网
- 虚拟局域网：一个广播域/网段