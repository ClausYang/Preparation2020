# Chapter 2

## 1. 物理层基本概念

- 如何在连接各种计算机的传输媒体上**传输数据比特流**
- 确定与传输媒体的接口的一些特性
  - 机械特性：接口形状、大小、引脚数目
  - 电气特性：电压范围
  - 功能特性
  - 过程特性

## 2.数据通信的基础知识

- 数据（data）：用户消息的实体
- 信号（signal）：数据的电气和电磁的表现
  - 模拟信号：连续的消息参数
  - 数字信号：离散的消息参数
- 码元（code）：代表不同离散数值的**基本波形**

- 信道
  - 单向信道（单工信道）：只能有一个方向通信而没有反方向
  - 双向交替通信（半双工）：通信的双方都可以发送信息，但不能同时发送
  - 双向同时通信（全双工通信）：通信的双方可以同时发送和接收消息
- 基带信号：来自信源的信号
- 带通信号：把基带信号通过**载波调制**后，把信号频率范围搬移到较高的频段以便在信道中传输，**传播更远**
- 调幅：载波的**振幅**随基带数字信号而变化
- 调频：载波的**频率**随基带数字信号而变化
- 调相：载波的**初始相位**随基带数字信号而变化

- 常用编码：
  - 单极性不归零码：高电平->1，没电压->0
  - 双极性不归零码：正电平->1，负电平->-1
  - 双极性归零码：正负0三个电平，**出现变化即归零**
  - 曼彻斯特编码：取电压变化的位置，低到高->0，高到低->1
  - 差分曼彻斯特编码：看信号之间的跳变，信号间有变化->0，信号间无变化->1，**bit中间必然跳变**
- 奈氏准则：在任何信道中，码元传输的速率是有上限的，否则就会出现**码间串扰**的问题
  - 理想低通信道的最高码元传输速率是![](http://latex.codecogs.com/svg.latex?\\=2WBaud)
    - ![](http://latex.codecogs.com/svg.latex?\\W)：理想低通信道的带宽（HZ）
    - ![](http://latex.codecogs.com/svg.latex?\\Baud)：波特，码元传输速率的单位

- 香农公式
  - 信道的带宽或信道中的信噪比越大，则信道的极限传输速率就越高

## 3.物理层下面的传输媒体

- 光纤与多模光纤
- 集线器：起到**信号放大**和**重发**的作用，扩大网络传输范围，**不具备定向传送能力**
  - 集线器是一个大的冲突域

## 4.信道复用技术

- 使用复用技术：复用-分用
- 频分复用：用户分配到一定的频带后，在通信过程中自始自终都占用这个频带
  - 波形叠加
- 时分复用：按顺序来放数据，在帧中的位置不变
- 统计时分复用：加标记区分数据
- 码分复用

## 5.数字传输技术

## 6.宽带接入技术