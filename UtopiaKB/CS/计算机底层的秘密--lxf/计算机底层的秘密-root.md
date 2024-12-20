
# 概括
>深入浅出，层层递进的讲解了计算机软硬件的底层原理，说明了一个程序运行起来到底发生了什么。
>
>重点概念有“虚拟”。套上一层抽象，假装它能发挥作用A，或就是构造B，但是实际是什么样的上层并不关心，只要功能上和上层认为的一致即可。计算机系统就是这样一层一层虚拟上去的。多进程、虚拟内存等有关效率、便捷的概念也建立在“虚拟”思想之上。

# 目录/框架

* 从编程语言到可执行程序，这是怎么一回事
	* 假如你来发明编程语言
		* 创世纪：CPU是个聪明的笨蛋
		* 汇编语言出现了
		* 底层的细节VS高层的抽象
		* 套路满满：高级编程语言的雏形
		* 《盗梦空间》与递归：代码的本质
		* 让计算机理解递归
		* 优秀的翻译官：编译器
		* 解释型语言的诞生
	* 编译器是怎样工作的
		* 编译器就是一个普通程序
		* 提取出每一个符号
		* token想要表达什么含义
		* 语法树是不是合理的
		* 根据语法树生成中间代码
		* 代码生成
	* 链接器不能说的秘密
		* 连接器是如何工作的
		* 符号决议：供给与需求
		* 静态库、动态库与可执行文件
		* 动态库有哪些优势及劣势
		* 重定位：确定符号运行时地址
		* 虚拟内存与程序内存布局
	* 为什么抽象在计算机科学中如此重要
		* 编程与抽象
		* 系统设计与抽象
	* 总结
* 程序运行起来了，可我对其一无所知
	* 从根源上理解操作系统、进程与线程
		* 一切要从CPU说起
		* 从CPU到操作系统
		* 进程很好，但还不够方便
		* 从进程演变到线程
		* 多线程与内存布局
		* 线程的使用场景
		* 线程池是如何工作的
		* 线程池中线程的数量
	* 线程间到底共享了哪些资源
		* 线程私有资源
		* 代码区：任何函数都可以放到线程中执行
		* 数据区：任何线程均可访问到数据区变量
		* 堆区：指针是关键
		* 栈区：公共的私有数据
		* 动态链接库与文件
		* 线程局部存储：TLS
	* 线程安全代码到底是怎么编写的
		* 自由与约束
		* 什么是线程安全
		* 线程的私有资源与共享资源
		* 只使用线程私有资源
		* 线程私有资源+函数参数
		* 使用全局变量
		* 线程局部存储
		* 函数返回值
		* 调用非线程安全代码
		* 如何实现线程安全代码
	* 程序员应该如何理解协程
		* 普通的函数
		* 从普通的函数到协程
		* 协程的图形化解释
		* 函数只是协程的一个特例
		* 协程的历史
		* 协程是如何实现的
	* 彻底理解回调函数
		* 一切要从这样的需求说起
		* 为什么需要回调
		* 异步回调
		* 异步回调带来新的编程思想
		* 回调函数的定义
		* 两种回调类型
		* 异步回调的问题：回调地狱
	* 彻底理解同步与异步
		* 辛苦的程序员
		* 打电话与发邮件
		* 同步调用
		* 异步调用
		* 同步、异步在网络服务器中的应用
	* 还有阻塞与非阻塞
		* 阻塞与非阻塞
		* 阻塞的核心问题：IO
		* 非阻塞与异步IO
		* 一个类比：点披萨
		* 同步与阻塞
		* 异步与非阻塞
	* 融会贯通：高并发、高性能服务器是如何实现的
		* 多进程
		* 多线程
		* 事件循环与事件驱动
		* 问题一：事件来源与IO多路复用
		* 问题二：事件循环与多线程
		* 咖啡馆是如何运作的：Reactor模式
		* 事件循环与IO
		* 异步与回调函数
		* 协程：以同步的方式进行异步编程
		* CPU、线程与协程
	* 计算机系统漫游：从数据、代码、回调、闭包到容器、虚拟机
		* 代码、数据、变量与指针
		* 回调函数与闭包
		* 容器与虚拟机技术
	* 总结
* 底层？就从内存这个储物柜开始吧
	* 内存的本质、指针及引用
		* 内存的本质？储物柜、比特、字节与对象
		* 从内存到变量
		* 从变量到指针
		* 指针的威力与破坏性
		* 从执行很到引用：隐藏内存地址
	* 进程在内存中是什么样子的
		* 虚拟内存
		* 页与页表
	* 栈区：函数调用是如何实现的
		* 程序员的好帮手：函数
		* 函数调用的活动轨迹：栈
		* 栈帧和栈区
		* 函数跳转与返回的实现
		* 参数传递与返回值的实现
		* 局部变量存在哪里
		* 寄存器的保存与恢复
		* Big picture
	* 堆区：内存动态分配是如何实现的
		* 为什么需要堆区
		* 自己动手实现一个malloc内存分配器
		* 从停车场到内存管理
		* 管理空闲内存块
		* 跟踪内存分配状态
		* 怎样选择空闲内存块
		* 分配内存
		* 释放内存
		* 高效合并空闲内存块
	* 申请内存时到底发生了什么
		* 三界与CPU运行状态
		* 内核态与用户态
		* 传送门：系统调用
		* 标准库：屏蔽系统差异
		* 堆区内存不够了怎么办
		* 向操作系统申请内存：brk
		* 冰山之下：虚拟内存才是终极Boss
		* 关于内存分配完整的故事
	* 高性能服务器内存池是如何实现的
		* 内存池vs通用内存分配器
		* 内存池技术原理
		* 实现一个极简内存池
		* 实现一个稍微复杂的内存池
		* 内存池的线程安全
	* 与内存相关的经典bug
		* 返回指向局部变量的指针
		* 错误地理解指针运算
		* 解引用有问题的指针
		* 读取未被初始化的内存
		* 引用已经被释放的内存
		* 数组下标是从0开始的
		* 栈溢出
		* 内存泄漏
	* 为什么SSD不能被当作内存使用
		* 内存读写与硬盘读写的区别
		* 虚拟内存的限制
		* SSD使用寿命的问题
	* 总结
* 从晶体管到CPU，谁能比我更重要
	* 你管这破玩意叫CPU
		* 伟大的发明
		* 与或非
		* 道生一...
		* 计算能力是怎么来的
		* 神奇的记忆能力
		* 寄存器与内存的诞生
		* 硬件还是软件？通用设备
		* 硬件的基本功：机器指令
		* 软件与硬件的接口：指令集
		* 指挥家：让我们演奏一曲
		* 大功告成，CPU诞生了
	* CPU空闲时在干嘛
		* 你的计算机CPU使用率是多少
		* 进程管理与进程调度
		* 队列判空：一个更好的指针
		* 一切都要归结到CPU
		* 空闲进程与CPU低功耗状态
		* 逃出无限循环：中断
	* CPU是如何识数的
		* 数字0与正整数
		* 有符号整数
		* 正数加上符号即对应的负数：原码
		* 源码的翻转：反码
		* 不简单的两数相加
		* 对计算机友好的表示方式：补码
		* CPU真的识数吗
	* 当CPU遇上if语句
		* 流水线技术的诞生
		* CPU：超级工厂与流水线
		* 当IF遇到流水线
		* 分支预测：尽量让CPU猜对
	* CPU核数与线程数有什么关系
		* 菜谱与代码，炒菜与编程
		* 任务拆分与阻塞式IO
		* 多核与多线程
	* CPU进化论（上）：复杂执行集诞生
		* 程序员眼里的CPU
		* CPU的能力图：指令集
		* 抽象：少就是多
		* 代码也是要占用存储空间的
		* 复杂指令集诞生的必然
		* 微代码设计的问题
	* CPU进化论（中）：精简指令集诞生
		* 化繁为简
		* 精简指令集哲学
		* CISC和RISC的区别
		* 指令流水线
		* 名扬天下
	* CPU进化论（下）：绝地反击
		* 打不过就加入，像RISC一样的CISC
		* 超线程的绝技
		* 取人之长，补己之短：CISC与RISC的融合
		* 技术不是全部：CISC与RISC的商业之战
	* 融会贯通：CPU、栈与函数调用、系统调用、线程切换、中断处理
		* 寄存器
		* 栈寄存器
		* 指令地址寄存器
		* 状态寄存器
		* 上下文
		* 嵌套与栈
		* 函数调用与运行时栈
		* 系统调用与内核态栈
		* 中断调用与中断函数栈
		* 线程切换与内核态栈
	* 总结
* 四两拨千斤，cache
	* cache，无处不在
		* CPU与内存速度的差异
		* 图书馆、书桌与cache
		* 天下没有免费的午餐：cahce更新
		* 天下也没有免费的晚餐：多核cache的一致性
		* 内存作为磁盘的cache
		* 虚拟内存与磁盘
		* CPU是如何读取内存的
		* 分布式存储来帮忙
	* 如何编写对cache友好的程序
		* 程序的局部性原理
		* 使用内存池
		* struct结构体重新布局
		* 冷热数据分离
		* 对cache友好的数据结构
		* 遍历多维数组
	* 多线程的性能“杀手”
		* cache与内存交互的基本单位：cache line
		* 性能杀手一：cache乒乓问题
		* 性能杀手二：伪共享问题
	* 烽火戏诸侯与内存屏障
		* 执行乱序执行：编译器与OoOE
		* 把cache页考虑进来
		* 四种内存屏障示例
		* acquire-release语义
		* C++中提供的接口
		* 不同的CPU， 不同的秉性
		* 谁应该关心指令重排序：无锁编程
		* 有锁编程vs无锁编程
		* 关于指令重排序的争议
	* 总结
* 计算机怎能少得了IO
	* CPU是如何处理IO操作的
		* 专事专办：IO机器指令
		* 内存映射IO
		* CPU读写键盘的本质
		* 轮询：一遍遍地检查
		* 点外卖与中断处理
		* 中断驱动式IO
		* CPU如何检测中断信号
		* 中断处理与函数调用的区别
		* 保存并恢复被中断程序的执行状态
	* 磁盘处理IO时CPU在干嘛
		* 设备控制器
		* CPU应该亲自复制数据吗
		* 直接存储器访问：DMA
		* Put Together
		* 对程序员的启示
	* 读取文件时程序经历了什么
		* 从内存的角度看IO
		* read函数是如何读取文件的
	* 高并发的秘诀：IO多路复用
		* 文件描述符
		* 如何高效处理多个IO
		* 不要打电话给我，有必要我会打给你
		* IO多路复用
		* 三剑客：select，poll，epoll
	* mmap：像读写内存那样操作文件
		* 文件与虚拟内存
		* 魔术师操作系统
		* mmap vs 传统read/write操作
		* 大文件处理
		* 动态链接库与共享内存
		* 动手操作一下mmap
	* 计算机系统中各个部分的时延有多少
		* 以时间为度量来算
		* 以距离为度量来算
	* 总结

