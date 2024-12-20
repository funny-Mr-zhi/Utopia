
# 目录

* 概论
	* 导论（2）
	* 操作系统结构（38）
* 进程管理
	* 进程（72）
		* 进程概念
			* 需要支持多用户，多程序同时执行。
			* 包括执行的代码段和相关存储器状态
			* 进程状态：new, running, waiting, ready, terminated 
			* 进程控制块：PCB
			* 线程：拓展进程概念，每个进程可以同时执行多个线程，PCB也被拓展到每个线程。
		* 进程调度
			* 调度队列：包括就绪队列和设备队列
			* 调度程序：按照一定方式从队列中选择合适进程。
			* 上下文切换：包括状态保存和恢复，主要存取PCB中的数据。
		* 进程运行
			* 进程可以并发执行，需要动态的创建和删除
			* 进程创建: 进程树--根据进程和父子关系构建；进程标识符--pid
			* 进程终止：调用eixt（），释放资源。通常由父进程控制。
		* 进程间通信
			* IPC，独立于进程的存储，两种基本模型：共享内存和消息传递
			* 共享内存：引入生产者-消费者概念，可对应于服务器-客户机概念。引入缓冲区以保证消费者和生产者可以并发执行。存在同步问题
			* 消息传递：由操作系统系统的另一种消息传递机制，至少需要send和receive。分为直接和间接两种。
			* 实现S/R原语有不同的方案，分为阻塞和非阻塞（同步/异步）。同样缓冲队列也有不同的设计方式，分为零容量，有限容量和无限容量。
		* 举例
		* 服务器/客户机通信
			* 客户机除了上述两种通信方式外，还有三种通信方式：套接字，远程程序调用（RPC）和管道。
			* 每对进程分配一对套接字，通常分为服务端和客户端，服务端监听请求，客户端发送请求。一个套接字包含IP和端口号。
			* RPC，类似两种进程间通信，不过是在不同的操作系统之间，基于消息传递机制的。可以用来实现分布式文件系统。一个进程调用远端应用的过程时使用。
			* 管道允许两个进程间进行通信，分为普通管道（单向，父子关系）和命名管道（UNIX--半双工，父子关系非必须，由OS创建，通信进程应位于同一台机器上，若跨平台应使用套接字）。
		* 小结：进程的**组织执行关系、从属构建关系、跨进程，平台通信关系**。
			* 进程及进程状态-->用PCB表示
			* PCB组成进程调度队列和IO队列，调度在队列上展开。（**执行关系**）
			* 进程间的从属关系通过父子关系构建。
			* 进程必须可以协作，提供进程间的消息传递机制。
			* 服务器-客户机的进程之间也应该能够通信，通过套接字，RPC和管道实现。
	* 多线程编程（112）
		* 概述
			* 线程是CPU使用的基本单元，包括线程ID、程序计数器，寄存器核堆。与统一进程其它线程共享代码段，数据段核其它操作系统资源。
			* 需要执行多任务时，创建线程比创建进程节省资源。
			* 优势：响应性、资源共享、经济、可伸缩性。
	* 进程调度（138）
		* 基本概念
			* CPU调度时多道程序操作系统的基础。操作系统实际调度的时内核级线程而非进程。
			* 多道程序的目标是：允许某个进程运行以最大化CPU利用率。
			* CPU空闲时，OS从就绪队列中选择一个进程来执行，队列内记录通常为进程控制块（PCB）
			* 分为抢占式和非抢占式
			* 调度程序是一个模块，用来将CPU控制交给短期调度程序选择进程，功能包括：切换上下文、切换到用户模式、跳到用户的合适位置，以便重新启动程序。
	* 同步（175）
		* 背景
			* 写作进程能相互影响，为了确保共享数据的一致性（完整性），引入临界区问题。
			* 本章主要讲写作进程如何进程同步和进程协调。
		* 临界区问题
			* 临界区指代码段中位于进入区和退出区之间的代码，进程在执行该区时可能修改公共变量，更新一个表，写一个文件等。
			* 临界区解决三个要求：互斥、进步、有限等待。抢占式方法更受欢迎。
		* Peterson解决方案
		* 硬件同步
		* 互斥锁
		* 信号量
		* 经典同步问题
		* 管程
		* 同步例子
		* 替代方法
		* 小结
	* 死锁（212）
* 内存管理
	* 内存管理策略（234）
	* 虚拟内存管理（264）
* 存储管理
	* 文件系统（310）
	* 文件系统的实现（337）
	* 大容量存储结构（367）
	* I/O系统（390）
* 保护与安全
	* 系统保护（416）
	* 系统安全（436）
* 案例研究
	* Linux, Windows7, 有影响的操作系统（474）

>论说性书，类似百科全书类。