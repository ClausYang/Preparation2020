# Chapter 1

### 1. 课程概要

- 操作系统结构

- 中断及系统调用
  - **中断**是OS与**硬件**打交道的接口
  - **系统调用**是OS对上层应用提供的服务接口

- 内存管理

- 进程及线程
  - OS对状态的维护

- 处理机调度

- 同步互斥
  - 进程间通讯的处理

- 文件系统

- I/O子系统

### 2. 什么是操作系统

- 系统软件
  - 错误处理
  - 协助用户
- 资源管理器
  - 应用程序和硬件的中间层
  - 资源管理

### 3. 操作系统软件的组成

- Shell--命令行

- GUI--图形化界面

- Kernel--操作系统内部

### 4. 操作系统的特征

- 并发
  - 管理和调度正在运行的多个程序
- 共享
  - 宏观：同时访问
  - 微观：互斥共享，需要做很好的隔离
- 虚拟
  - 利用多道程序设计技术，让用户觉得只有一台计算机为其服务
- 异步
  - 程序并不是一直执行，行为不可预测
  - 运行环境相同需要保证结果一致