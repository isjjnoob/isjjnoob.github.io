---
layout: post
title: "操作系统复习"
date: 2019-04-26
author: jjnoob
category: 2019-04
tags: studying
finished: true
---

* content
{:toc}

> 为什么越来越觉得我们的教材就是"参考" <<深入理解操作系统>>这本书的.

> 掘金上好多好文章, 注册了一个账号, 嗯.

> 博客园上面的图片链接无法在博客中显示, 不知道为什么. 暂时复制图片链接打开看吧.


**目录:**
[复习一](#01)

[复习二](#02)

[段式页式](#03)

[第四章-设备管理](#04)

[第五章复习](#05)

***
# 复习一
[参考-掘金-操作系统概要](https://juejin.im/post/5acc3e93f265da239a60211d)
<div id="01"></div>

# 第二章 进程管理
### (1) PV 操作
* p(s)
将信号量s的值减一
   * s < 0 ,阻塞
   * s >= 0 , 运行
* v(s)
将信号量s的值加一
   * s <= 0 , 运行
   * s > =0 , 运行


### (2) 周转时间 等
* 周转时间 = 作业完成时间 - 作业提交时间
作业提交时间指 从 发出请求 到 开始运行 所花的时间
* 带权周转时间 = 作业周转时间 / 作业实际运行时间

### (3) 处理器调度 - 三种算法
* 先来先服务算法 (FCFS)
* 短作业优先算法 (SJF)
* 优先级高优先算法 (HPF)

### (4) 银行家算法
> 一开始有点不懂, ppt说的很迷...于是谷歌到一个说的很清楚的教程, 但是复制链接失败, 于是保存为截图, 再复制截图的链接.

[教程截图链接](https://s2.ax1x.com/2019/04/19/E9eCFS.png)

<br />



# 第三章 存储管理

[知识点参考](https://juejin.im/post/5bc5e39be51d450e597b9fdc)

### (1) 程序的链接和装入
#### 装入:
* 绝对装入
* 可重定位装入
* 运行时装入

#### 链接:
* 静态链接
* 装入时链接
* 动态链接

### (2) 程序存储空间的分配
#### 连续存储空间分配
* 单一连续存储分配
* 固定存储分配
* 动态存储空间分配
* 可重定位的分区分配

#### 离散存储空间分配
* 页式存储空间分配
* 段式存储空间分配
* 段页式存储空间分配


### (3) 虚拟存储器
#### 请求分页存储

#### 请求分段存储

#### 置换算法
* 最佳置换算法 (OPT)
* 先进先出置换算法 (FIFO)
* 最近最少未使用算法 (LRU)
* 时钟置换算法 (CLOCK)

### (4) 算法问题
> 知识点, 计算题(算法)..掘金上有很多很好的文章, 以前都没发现

[页面置换算法参考掘金文章](https://juejin.im/post/5a36854a6fb9a0450c497e0c)

[时钟置换算法参考简书](https://www.jianshu.com/p/417981b9379f)

[时钟置换算法参考](https://yuerer.com/%E6%93%8D%E4%BD%9C%E7%B3%BB%E7%BB%9F%E4%B9%8B-%E8%99%9A%E6%8B%9F%E5%AD%98%E5%82%A8%E9%A1%B5%E9%9D%A2%E7%BD%AE%E6%8D%A2%E7%AE%97%E6%B3%95/)

> 关于时钟置换算法, 貌似在一轮扫描之后, `0 1`会变成 `0 0`, 步骤中没有写, 但是谷歌到的例子中变了. 姑且这样认为吧.

<br />

# 第四章 设备管理

# 第五章 文件系统


*** 
<div id="02"></div>

# 复习二


[参考CSDN](https://blog.csdn.net/Thousa_Ho/article/details/77145422)

> 不写点东西我都快睡着了...



# 一. 操作系统的基本特征
* 并发
* 共享
* 虚拟
* 异步: 系统中的进程是以走走停停的方式执行的，且以一种不可预知的速度推进

<br />

# 二. 操作系统的主要功能
* 处理机管理: 处理机分配都是以进程位单位, 所以处理机管理也被看做是进程管理.
* 存储器管理
* 设备管理
* 文件管理

<br />

# 三. 进程和线程的区别
* 调度方面: 线程是独立的调度和分派单位, 而进程作为资源的拥有单位.
* 并发行: 一个进程内部有多个线程, 进程是可以并发的, 其内部的线程也是可以并发的.
* 拥有资源: 进程是基本的资源拥有单位, 而线程只拥有很少的基本资源.
* 系统开销: 
   * 创建或者撤销进程的时候，系统要为之创建或回收PCB，系统资源等，切换时也需要保存和恢复CPU环境。
   * 而线程的切换只需要保存和恢复少量的寄存器，不涉及存储器管理方面的工作，所以开销较小。

<br />

# 四. 进程的几种状态
* 就绪状态
* 执行状态
* 阻塞状态

<br />

# 五. 进程同步
### 同步机制需要遵循的原则:
* 空闲让进
* 忙则等待
* 有限等待
* 让权等待

### 经典的进程同步问题:
* 生产者-消费者问题
* 哲学家进餐问题
* 读者-写者问题

<br />

# 六. 进程间通信
### (1) 低级通信存在的问题 (进程间同步互斥)
* 通信的数据量太少
* 通信对用户不透明

### (2) 高级通信机制
高级通信的通信的通信细节被OS隐藏, 因此使用起来增加方便而且可以传送大量的数据, 尤其是管道通信

#### 共享存储器系统
相互通信的进程共享某些数据结构或者是存储区，进程之间可以通过这些共享空间进行通信
* 基于共享数据结构的通信
* 基于共享存储区的通信

#### 消息传递系统
进程间通信采用的是格式化的消息，可以直接使用OS提供的消息发送或者接受原语进行通信。由于隐藏了通信细节，所以简化了通信程序的复杂性

#### 管道通信
管道是连接一个读进程和一个写进程之间用于实现数据交换的一个共享文件

管道机制需要的功能有:
* 互斥
* 同步
* 确定对方的存在性: 只有同时有读端和写端, 管道才有存在的意义.

<br />

# 七. 进程/任务调度算法
> 该教程说了一大堆. 不过, 我看学长的总结, 只有三种算法. 具体算法看例题. 做题才有体会 


* 先来先服务算法 (FCFS)
* 短作业优先算法 (SJF)
* 优先级高优先算法 (HPF)

<br />

# 八. 死锁的必要条件以及处理方法
死锁是指多个进程在运行过程中，因为争夺资源而造成的一种僵局，如果没有外力推进，处于僵局中的进程就无法继续执行。

### (1) 死锁原因:
* 竞争资源
* 进程推进顺序非法

### (2) 死锁产生的必要条件:
* 互斥条件
* 请求和保持条件
* 不可剥夺条件
* 环路等待条件

### (3) 死锁处理:
* 预防死锁
* 避免死锁
* 检测死锁
* 解除死锁

<br />

# 九. 内存管理方式 - 段式页式和段页式
由于连续内存分配方式导致的内存利用率偏低以及内存碎片的问题，进而引出离散的内存分配方式。

离散内存分配可以从OS的**内存管理角度引出页式**(离散分配的基本单位是页)管理，也可以从**程序编制角度引出段式**(离散分配的基本单位是段)管理。

<br />

# 十. 基本分页存储管理

<br />

# 十一. 基本分段存储管理方式

<br />

# 十二. 段页式存储管理
> 该部分, 教程说的不太清楚, 看样子是重点, 应当单独拎出来学习一下, 下午吧. 先回去吃饭.


<br />

# 十三. 虚拟内存及页面置换算法
* 如果存在一个程序，所需内存空间超过了计算机可以提供的实际内存，那么由于该程序无法装入内存所以也就无法运行。单纯的增加物理内存只能解决一部分问题，但是仍然会出现无法装入单个或者无法同时装入多个程序的问题。但是可以从逻辑的角度扩充内存容量，即可解决上述两种问题。

* 虚拟存储器就是具有请求调入功能和置换功能，可以从逻辑上对内存容量加以扩充的一种存储器系统。虚拟存储器都是建立在离散内存管理的基础上

### 虚拟存储器的特征:
* 多次性
* 对换性
* 虚拟性: 虚拟性体现在其从逻辑上扩充了内存的容量

<br />

联系:
* 虚拟性建立在多次性和对换性的基础上行
* 多次性和对换性又建立在离散分配的基础上

<br />

# 十四. 页面置换算法
* 最佳置换算法
* 最近最久未使用算法 (LRU)
* 最少使用算法 (LFU)
* 时钟算法 (CLOCK)
* 改进型CLOCK算法

***
<div id="03"></div>

# 段式页式和段页式复习



[参考](http://www.cnblogs.com/suncoolcat/p/3400353.html)

[参考掘金-涂印](https://juejin.im/post/5bc5e39be51d450e597b9fdc)

# 一. 基础理解

* 由于连续分配方式会形成许多内存碎片，虽可通过“紧凑”功能将碎片合并，但会付出很大开销。于是出现离散分配方式：将一个进程直接分散地装入到许多**不相邻**的内存分区中。

![img](http://img.blog.csdn.net/20131031074819750?watermark/2/text/aHR0cDovL2Jsb2cuY3Nkbi5uZXQvd2FuZzM3OTI3NTYxNA==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70/gravity/Center)

<br />

# 二. 离散存储空间分配
离散存储空间分配是指，其能将任务分割成更小的存储单位。分割后的存储单位连续存储，而存储单位与存储单位之间并不要求连续。通过将任务拆分进行存储的方法，能极大的提高存储空间的利用率。


### (1) 页式存储空间分配
这里将页定义为一个固定大小的存储单位。在将任务载入内存时，一个完整的任务可以被划分成多页。每页独立的存储到内存空间中，内存空间中存储位置可用物理页号描述。每页的存储是连续，页与页之间的存储并不是连续的，而是离散存储的。
为了建立任务的地址与物理空间地址之间的联系。在内存表中将建立页表，完成页号到物理号的映射

![img](https://user-gold-cdn.xitu.io/2018/10/17/1667fd69ef8374a4?imageView2/0/w/1280/h/960/format/webp/ignore-error/1)



### (2) 段式存储空间分配
段式存储的方法和页式存储的方法手段都是一致。将任务以 **段为存储单位，将任务分成多段进而离散存储** 在内存中同样维护了一张段表。段表和页表结构是一致的。
![img](https://user-gold-cdn.xitu.io/2018/10/17/1667fd9bfdefea9e?imageView2/0/w/1280/h/960/format/webp/ignore-error/1)

### (3) 以下是页式存储和段式存储的差别:

* 页是信息的物理单位，分页式为了减少内存碎片，提高内存利用率而提出的。段是信息的逻辑单位，它包含一组完成的逻辑意义，其不仅能提高内存利用率，而且在方便编程，信息共享，信息保护等方面均有好处。
* 页的大小是有操作系统固定设计的，在系统中页的大小是固定且唯一的。段长度并不是固定的，取决于用户所编写的程序，通常由编译程序在对源程序进行编译时，根据信息的性质决定。


### (4) 段页式存储空间分配
该存储方式实际上是，分页存储和分段存储的组合。先将任务按照段进行划分，然后每段按照分页的方式进行存储，即为段页式存储。

<br />

# 四. 虚拟存储器
虚拟存储器是现在操作系统广泛使用的一种存储方式，虚拟存储能在不对物理内存扩容的基础上，保证能够运行更多更大的内存任务。虚拟存储器和常规存储器的不同之处在于，虚拟存储器不要求你任务一次性全部载入内存，而是按需载入内存。并且能在内存空间受限时，将闲置的内存作业调出内存，这种将内存作业调出内存的过程称为置换，完成置换过程的方式则称为置换算法。在上述过程中，不将作业一次性完全载入内存，显然是建立在分页存储或者分段存储的基础上，下文对这两种情况分别介绍


### (1) 请求分页存储
请求分页存储具有两点内容需要理解:

* 分页加载，按需加载
请求分页存储将任务以页为单位进行划分，在载入内存时，并不将全部页面载入。而是将部分必须的页面载入内存，其他的页面在程序运行中，若使用则按需载入内存。
* 分页置换
在内存空间紧张时，会将程序中某些使用或者近期不在使用的页面，从内存置换到磁盘中去。


在请求分页存储中，内存中维护的页表不再是简单的页号到内存物理号之间的映射了。其页表结构一般如下:
![img](https://user-gold-cdn.xitu.io/2018/10/17/16680159c53f6251?imageView2/0/w/1280/h/960/format/webp/ignore-error/1)

* 页号，这个字段代表分页顺序
* 物理块号，这个字段代表，该页在内存中的位置
* 状态位P，该状态位用来标识该页是否载入内存，true代表载入内存，false代表未载入内存
* 访问字段，该状态位是统计状态位，可以用来记录该页最近被访问的次数
* 修改位，该位用来标识，该页载入到内存后是否被修改过了。若内存中修改过后，其置换到外存时，需要回写回去。如果没有修改过，那么其置换到外存时，无须回写回去。
* 外存地址，该位存储该也在外存中的地址。一般来说，在载入内存后，外存上依旧会留有一一份拷贝信息。

### (2) 请求分段存储
请求分段存储与请求分页存储及其相似。唯一的区别便是，载入和置换的单位从页转换到了段。


### (3)置换算法
置换算法，在虚拟存储器中是非常重要的内容。在虚拟存储器设计理念中，当内存资源紧张的时候，会依据置换算法将内存中的页面置换到外存中
> 置换算法, 前面有提到

***

<div id="04"></div>

# 第四章 设备管理

[参考-博客园](http://www.cnblogs.com/leesf456/p/5622859.html)

[参考-掘金](https://juejin.im/post/5a643960f265da3e3a6de404)

> 先复习第四章和第五章, 因为有些教程一直没有详细讲这两章. 导致这两章很薄弱

# 一. I/O 系统
### (1) I/O设备
I/O设备类型繁多，在OS观点看，设备使用特性、数据传输速率、数据的传输单位、设备共享属性等都是重要的性能指标。可以按照不同角度对他们进行分类:
* 按设备使用特性分类
* 按数据传输速率分类
* 按数据的传输单位分类
* 按设备共享属性分类

通常，设备并不是直接与CPU进行通信，而是与设备控制器通信，因此，在I/O设备中应该含有与设备控制器之间的接口，在该接口有三种类型的信号，各对应一条信号线。
* 数据信号线
* 控制信号线
* 状态信号线


![img](https://images2015.cnblogs.com/blog/616953/201606/616953-20160628151650952-1466573946.png)

### (2) 设备控制器
* 其主要职责是控制一个或多个I/O设备，以实现I/O设备和计算机之间的数据交换，它是CPU与I/O设备之间的接口，它接收从CPU发来的命令，并去控制I/O设备工作
* 其是一个可编址的设备，当它仅控制一个设备时，它只有一个唯一的设备地址，若控制器可连接多个设备时，则应该含有多个设备地址，并使每个设备地址对应一个设备。
* 设备控制器可以分为用于控制字符设备的控制器和用于控制块设备的控制器。

#### 设备控制器的基本功能如下:
* 接受和识别命令
* 数据交换
* 标识和报告设备的状态
* 数据缓冲: 由于I/O设备的速率较低而CPU和内存速率很高，故在控制器中必须设置一个缓冲器
* 差错控制: 设备控制器监管对I/O设备传送来的数据进行差错检测，若发现传送中出现了错误, 则向CPU报告

#### 现有的大多数控制器都是由如下的三部分组成:
* 设备控制器与设备机的接口: 该接口用于实现CPU与设备控制器之间的通信
* 设备控制器与设备的接口: 设备控制器可以连接一个或多个设备，相应地，在控制器中便有一个或多个设备接口，一个接口连接一台设备.
* I/O逻辑: 每当CPU要启动一个设备时，一方面将启动命令发送给控制器，另一方面又同时通过地址线把地址发送给控制器，由控制器的I/O逻辑对收到的地址进行译码，再根据所译出的命令对所选设备进行控制。

![img](https://images2015.cnblogs.com/blog/616953/201606/616953-20160628155916327-714091848.png)

### (3) I/O通道
* CPU与 I/O设备 之间有**设备控制器**
* CPU和**设备控制器**之间有**通道**

在设置了通道后，CPU只需要向通道发送一条I/O指令，通道在收到该指令后，便从内存中取出本次要执行的通道程序，然后执行该通道程序，仅当通道完成了规定的I/O任务后，才向CPU发中断信号

#### 根据信息交换方式的不同，将通道分为以下三种:
* 字节多路通道
    这是一种按照字节交叉方式工作的通道，通常都含有许多非分配型子通道，其数量可以几十到数百个，每个子通道连接一台I/O设备，并控制该设备的I/O操作，这些子通道按照时间片轮转方式共享主通道。
    
![img](https://images2015.cnblogs.com/blog/616953/201606/616953-20160628165318109-1762635087.png)

* 数组选择通道
  字节多路通道不适合连接高速设备，数组选择通道按数组进行数据传送，其通常只含有一个分配型子通道，在一段时间内只能执行一道通道程序，控制一台设备进行数据传送，致使当某台设备占用了该通道后，便一直由它独占，即使是它无数据传送，通道被闲置，也不允许其他设备使用该通道，直至该设备传送完毕释放该通道，其利用率很低。

* 数组多路通道
  * 由于数组选择通道每次只允许一个设备传送数据，数组多路通道是将数组选择通道传输速率高和字节多路通道能使各子通道（设备）分时并行操作的优点相结合而形成的一种新通道，其含有多个非分配型子通道，具有很高的数据传输速率，其数据传输是按数组方式进行的。
  * 由于通道价格昂贵，计算所设置的通道较少，提高通道的利用率的一种很有效的方法是增加设备到主机间的通路而不增加通道。

![img](https://images2015.cnblogs.com/blog/616953/201606/616953-20160628170603827-1270043368.png)

<br />

# 二. I/O 控制方式
### (1) 程序I/O方式
在程序I/O方式中，由于CPU的高速性和I/O设备的低速性，致使CPU的绝大部分时间都处于等待I/O设备完成数据I/O的循环测试中，造成对CPU的极大浪费

### (2) 中断驱动I/O控制方式 
中断驱动I/O控制方式将CPU主动轮询的方式做出了改进，CPU处于被动的位置，等到有设备请求进行输入数据的时候，才去响应，从而提高了CPU的利用率。 也就是说，引入中断之后，每当设备完成I/O操作，便以中断请求方式通知CPU，然后进行相应处理。

### (3) 直接存储器访问(DMA) I/O 控制方式
#### 特点:
* 数据传输的基本单位是数据块，即在CPU与I/O设备之间，每次传送至少一个数据块。
* 所传送的数据是从设备直接送入内存的，或者相反。
* 仅在传送一个或多个数据块的开始和结束时，需要CPU干预，整块数据的传送是在控制器的控制下完成的。

DMA控制器由三部分组成，主机与DMA控制器的接口；DMA控制器与块设备的接口；I/O控制逻辑:
![img](https://images2015.cnblogs.com/blog/616953/201606/616953-20160628173514952-543939858.png)


#### DMA工作过程

![img](https://images2015.cnblogs.com/blog/616953/201606/616953-20160628174538171-789907791.png)

### (4) I/O 通道控制方式
* 而当我们需要一次去读多个数据块且将他们分别传送到不同的内存区域，或者相反时，则须由**CPU分别发出多条I/O指令及进行多次中断才能完成**
* I/O通道方式是DMA的发展，它可以进一步减少CPU的干预，即**把一个数据块的读（或写）为单位的干预减少为对一组数据块的读（或写）及有关的控制和管理为单位的干预。**
* 同时，可以实现CPU、通道、I/O设备的并行操作，提高资源利用率。

#### 通道指令与一般的机器指令不同，它的每条指令都包含下列的信息:
* 操作码，操作码规定了指令所执行的操作，如读、写、控制等操作。
* 内存地址，内存地址标明字符送入内存（读操作）和从内存取出（写操作）时的内存首址。
* 计数，该信息表示本条指令所要读（或写）数据的字节数。
* 通道程序结束位P，该位用于表示通道程序是否结束，P=1表示本条指令是通道程序的最后一条指令。
* 记录结束标志R，R=0表示本通道指令与下一条指令所处理的数据是同属于一个记录，R=1表示这是处理某记录的最后一条指令。

![img](https://images2015.cnblogs.com/blog/616953/201606/616953-20160628195526937-1209951630.png)

<br />

# 三. 缓冲管理
在设备管理部分，存在的主要矛盾是高速的CPU和低速I/O设备之间速度不匹配的问题。
对于这种问题，处理的方法一般是增加缓冲。
类似的，在计算机网络通信中，高速发送设备和低速接收设备之间为了防止数据的丢失，也会增加缓冲区。

* 缓和CPU和I/O设备速度不匹配的矛盾；
* 减少对CPU的中断频率，放宽对中断响应时间的限制；
* 提高CPU和I/O设备之间的并行性。


### (1) 单缓冲

### (2) 双缓冲

### (3) 循环缓冲
#### 循环缓冲区的组成如下:
* 多个缓冲区
  * 用于装输入数据的空缓冲区R
  * 已装满数据的缓冲区G
  * 计算进程正在使用的先行工作缓冲区C
  
* 多个指针
  * 指示计算进程下一个可用缓冲区G的指针Nextg
  * 指示输入进程下次可用的空缓冲区R的指针Nexti
  * 用于指示计算进程正在使用的缓冲区C的指针Current。
![img](https://images2015.cnblogs.com/blog/616953/201606/616953-20160628203538952-358207840.png)

#### 计算进程和输入进程可以 ***利用下述两个过程来使用循环缓冲区***
* Getbuf过程
* Releasebuf过程


#### 指针Nexti和指针Nextg顺时针移动过程中会出现以下两种情况:
* Nexti指针追赶上Nextg指针, 系统受计算限制.
* Nextg指针追赶上Nexti指针, 系统受I/O限制.

<br />

# 四. I/O 软件

### (1) 设备独立性软件
再实现了设别独立性功能后, 可带来以下好处:
* 设备分配时的灵活性
* 易于实现I/O重定向

### (2) 逻辑设备名到物理设备名映射的实现
* 逻辑设备表  (LUTLogical Unit Table)
* LUT的设置问题:
  * 在整个系统中设置一张LUT
  * 为每个用户设置一张LUT

<br />

# 五. 设备分配 (SPOOLing技术是重点)
### (1) 设备分配中的数据结构
在进行设备分配时，通常都需要借助于一些表格的帮助，在表格中记录了相应设备或控制器的状态及对设备或控制器进行控制所需的信息，在进行设备分配时所需要的数据结构有设备控制表、控制器控制表、通道控制表和系统设备表等。
* 设备控制表
* 控制器控制表
* 通道控制表
* 系统设备表

> 困😴

### (2) SPOOLing技术 (重点)
**通过SPOOLing技术可将一台物理I/O设备虚拟为多台逻辑I/O设备，允许多个用户共享一台物理I/O设备。**
* 虚拟设备技术假脱机操作(Simultaneous Peripheral Operations On-Line，SPOOLing)，利用专门的外围控制机，将低速I/O设备上的数据传送到高速磁盘上；或者相反。利用假脱机技术，可把独享设备转变成具有共享特征的虚拟设备，从而提高设备利用率。


####  SPOOLing 系统由以下三部分组成:
* 输入井和输出井
* 输入缓冲区和输出缓冲区
* 输入进程SPi和输出进程SPo
    利用两个进程来模拟脱机I/O时的外围控制机:
    * 进程SPi模拟脱机输入时的外围控制机，将用户要求的数据从输入机通过输入缓冲区再送到输入井，当CPU需要输入数据时，直接从输入井读入内存
    * 进程SPo模拟脱机输出时的外围控制机，把用户要求输出的数据先从内存送到输出井，待输出设备空闲时，再将输出井中的数据经过输出缓冲区送到输出设备上。

![img](https://images2015.cnblogs.com/blog/616953/201606/616953-20160628221859015-1173503029.png)

利用SPOOLing技术，可以将独占设备打印机改造为一台供多个用户共享的设备，从而提高设备的利用率，也方便了用户。当用户进程请求打印输出时 ，SPOOLing系统统一为它打印输出，但是并不真正立即把打印机分配给该用户进程，而只为它做两件事。
* 由输出进程在输出井中为之申请一个空闲磁盘块区，并将要打印的数据送入其中。
* 输出进程再为用户进程申请一张空白的用户请求打印表，并将该用户的打印要求填入其中，再将该表挂到请求打印队列上。

#### SPOOLing系统主要有如下的特点:
* 提高了I/O速度
* 将独占设备改造为共享设备
* 实现了虚拟设备功能

***
<div id="05"></div>

# 第五章复习

# 文件系统
[参考-博客园](https://www.cnblogs.com/leesf456/p/5626339.html)

# 一. 文件和文件系统
* 文件系统的管理功能是通过把它所管理的程序和数据组织成一系列文件的方法来实现的
* 文件则是指具有文件名的若干相关元素的集合。元素通常是记录，而记录是一组有意义的数据项的集合

#### 可以把数据组成分为数据项、记录、文件:
* 数据项，数据项是最低级数据组织形式。分为基本数据项组合数据项 (由若干个基本数据项组成)
* 记录, 是一组相关数据项的集合，用于描述一个对象在某方面的属性. 此外还有关键字.
* 文件，文件是具有文件名的一组相关元素的集合.

> 一个文件可对应若干个记录，一个记录可对应若干个数据项

文件系统管理的对象有: 文件, 目录 和 磁盘存储空间

### (1) 文件操作
> 相关的操作有很多, 其中截断文件硬干了解

* 截断文件，如果一个文件的内容已经陈旧而需要全部更新时，一种方法是将此文件删除，再重新创建一个新文件，但如果文件名和属性均无改变，则可采取截断文件的方法，其将原有的文件长度设置为0，放弃原有文件的内容。

<br />

# 二. 文件的逻辑结构
两种形式的结构:
* 文件的逻辑结构
* 文件的物理结构

### (1) 文件逻辑结构的类型:
* 一类是有结构文件，这是指由一个以上的记录构成的文件，故把他称为记录式文件
* 另一类是无结构文件，这是指由字符流构成的文件，又称为流式文件。

### (2) 顺序文件
* 串结构
* 顺序结构

### (3) 索引文件
* 为了**解决变长记录检索**问题，可为变长记录文件建立一张索引表，对主文件中的每个记录，在索引表中设有一个相应的表项，用于记录该记录的长度L及指向该记录的指针（指向该记录在逻辑地址空间的首址），由于索引表示按记录键排序的，因此，索引表本身是一个定长记录的顺序文件。从而可以方便实现直接存取。
* 在对索引文件进行检索时，首先根据用户（程序）提供的关键字，并利用折半查找检索索引表，从中找到相应的表项，再利用该表项给出的指向记录的指针值，去访问所需的记录。每当要向索引文件中增加一个新纪录时，便须对索引表进行修改。

![img](https://images2015.cnblogs.com/blog/616953/201606/616953-20160629142812609-701482299.png)

### (4) 索引顺序文件
**有效克服了变长记录不便于直接存取**的缺点，是顺序文件和索引文件相结合的产物，它将顺序文件中的所有记录分为若干个组，为顺序文件建立一张索引表，在索引表中为每组中的第一个记录建立一个索引项，其中含有该记录的键值和指向记录的指针。

![img](https://images2015.cnblogs.com/blog/616953/201606/616953-20160629143622906-56225907.png)

### (5) 直接文件
对于直接文件，则根据给定的记录键值，直接获得指定记录的物理地址，换言之，记录键值本身就决定了记录的物理地址，这种由记录键值到记录物理地址的转换被称为键值转换。

### (6) 哈希(Hash)文件
**利用Hash函数可将记录键值转换为相应记录的地址**，为了能实现文件存储空间的动态分配，通常由Hash函数所求得的并非是相应记录的地址，而是指向一目录表相应表目的指针，该表目的内容指向相应记录所在的物理块。

![img](https://images2015.cnblogs.com/blog/616953/201606/616953-20160629144528812-1046254793.png)

<br />

# 三. 外存分配方式

文件的物理结构和外存分配方式有关, 在采用连续分配方式时的文件物理结构是顺序式的文件结构, 在采用链接分配方式将形成链接文件结构, 而索引分配将形成索引式文件结构.

### (1) 连续分配
连续分配要求为每个文件分配一组相邻接的盘块，一组盘块地址定义了磁盘上的一段线性地址。采用连续分配方式时，可把逻辑文件中的记录顺序地存储到邻接的各物理盘块中，这样所形成的文件结构称为顺序文件结构，这种分配方式保证了逻辑文件中的记录顺序与存储器中文件占用盘块的顺序的一致性。下图为连续分配方式 (假设记录与盘块一样大)

![img](https://images2015.cnblogs.com/blog/616953/201606/616953-20160629152313437-1654504641.png)

#### 连续分配的优点如下:
* 顺序访问容易，访问一个占有连续空间的文件非常容易。
* 顺序访问速度快，因为由连续分配所装入的文件，其所占用的盘块可能是位于一条或几条相邻的磁道上，这是，磁头移动距离最少，这种对文件访问的速度使几种存储空间分配方式中最高的一种。

#### 连续分配的缺点如下:
* 要求又连续的存储空间，要为每个文件分配一段连续的存储空间，这样，便会产生许多外部碎片，严重地降低了外存空间利用率，定期紧凑会花费大量的机器时间。
* 必须实现知道文件的长度，事先知道文件的长度，然后根据其大小，在存储空间中找出一块其大小足够的存储区，将文件装入，对于动态增长的文件非常低效。
### (2) 链接分配
如果将一个逻辑文件存储到外存上，并不要求为整个文件分配一块连续的空间，而是可以将文件装到多个离散的盘块中，这样就可以消除连续分配的缺点。采用链接分配方式时，可通过在每个盘块上的链接指针，将同属于一个文件的多个离散盘块链接成一个链表，把这样形成的物理文件称为链接文件。链接分配采取离散分配方式，消除了外部碎片，故而显著地提高了外存空间的利用率，并且对文件的增、删、改、查十分方便。链接方式可分为隐式链接和显示链接两种形式。
#### 1. 隐式链接: 
在文件目录的每个目录项中，都须含有指向链接文件第一个盘块和最后一个盘块的指针。
![img](https://images2015.cnblogs.com/blog/616953/201606/616953-20160629152559140-1254602772.png)

#### 2. 显示链接: 
把用于链接文件各物理块的指针，显式的放在内存的一张链接表中，该表在整个磁盘仅设置一张。

![img](https://images2015.cnblogs.com/blog/616953/201606/616953-20160629153937109-1387268633.png)


表的序号从0开始，直至N-1，N为盘块总数，在每个表项中存放链接指针，即下一个盘块号，在该表中，凡是属于某一文件的第一个盘块号，或者说是每一条链的链首指针所对应的盘块号，均作为文件地址被填入相应的文件的FCB(File Control Block)的物理地址字段中，由于查找记录的过程是在内存中进行的，因而提高了检索速度，减少了访问磁盘的次数，由于分配给文件的所有盘块号都在该表中，故把该表称为文件分配表FAT（File Allocation Table）。

链接分配的问题如下：
* 不能支持高效的直接存储（要对一个较大的文件进行直接存取，须首先在FAT中顺序地查找很多盘块号）
* FAT需要占用较大的内存空间（由于一个文件所占用的盘块的盘块号是随机地分布在FAT中的，因而只有将整个FAT调入内存，才能保证FAT中找到一个文件的所有盘块号，当磁盘容量较大时，FAT占用的容量更大）

#### 3.  索引分配
事实上，在打开某个文件时，只需要把该文件占用的盘块号的编号调入内存即可，完全没有必要把整个FAT调入内存，为此，应该将每个文件所对应的盘块号集中地放在一起，索引分配方式就是基于这种想法所形成的一种分配方式。其为每个文件分配一个索引块（表），再把分配给该文件的所有盘块号都记录在该索引块中，因而该索引块就是一个含有许多磁盘块号的数组。在建立一个文件时，只需要在位为之建立的目录项中填上指向该索引块的指针（单级索引）。
![img](https://images2015.cnblogs.com/blog/616953/201606/616953-20160629155833984-2091692212.png)



　　说明：索引方式支持直接访问，可在索引块中找到第i个盘块，索引方式也不会产生外部碎片，当文件较大时，索引分配方式要优于链接分配方式。其主要问题在于：可能需要花费较多的外存空间，每当建立一个文件时，便须为之分配一个索引块，将分配给该文件的所有盘块号记录其中。对于小文件而言，索引块的利用率非常低。

　　当OS为一个大文件分配磁盘空间时，如果所分配的盘块的盘块号已经装满一个索引块时，OS便为该文件分配另一个索引块，用于将以后继续为之分配的盘块号记录于其中，以此类推，然后再通过链指针将各索引块按序链接起来，当文件太大时，索引块太多，效率是低效的。此时，应该为这些索引块再建立一级索引，称为第一级索引，还可再建立索引，称为第二级索引等等。称为多级索引分配。
![img](https://images2015.cnblogs.com/blog/616953/201606/616953-20160629161703031-708740708.png)

说明：在二级索引分配方式下，若每个盘块的大小为1KB，每个盘块号占4个字节，则在一个索引块可以存放256个盘块号，这样，在两级索引时，最多可以包括存放文件的盘块号总数为64K(256 * 256)个盘块号，所允许文件最大长度为64MB，若盘块号为4KB，则一级索引的最大文件大小为4MB，二级索引的最大文件大小为4GB。
> 这个计算没太看懂...


#### 4. 混合索引分配方式

将多种索引分配方式相结合而形成的一种分配方式，如直接地址（在索引结点中设置10个直接地址项，每项中所存放的是该文件数据所在盘块的盘块号，假如每个盘块大小为4KB，当文件不大于40KB时，可以**直接从索引结点中读出**该文件的全部盘号），**一次间接地址**（利用索引结点中的地址项来提供一次间接地址，其实质就是一级索引分配方式，在一次简直快中可存放1K个盘块号，允许最大文件为4MB），**多次间接地址**（当文件大于4MB + 40KB时，系统采用二次间址分配方式，其实质是两级索引分配方式，采用二次间址的最大文件大小为4GB，同理，可采用**三次间接地址**，允许文件最大大小为4TB）。

![img](https://images2015.cnblogs.com/blog/616953/201606/616953-20160629164020234-1658720371.png)

<br />

# 四. 目录管理
> 想睡觉, 感觉<<操作系统>>考试要凉了, 啥都不会..


### (1) 文件控制块
* 为了能对文件进行正确的存取，必须为文件设置用于描述和控制文件的数据结构，称之为文件控制块FCB，文件管理程序可借助于文件控制块中的信息，对文件施加各种操作.
* 而人们把文件控制块的有序集合称为文件目录，一个文件控制块就是一个文件目录项.
* 通常，一个文件目录也可被看成是一个文件，称为目录文件。
* 文件控制块包含基本信息、存取控制信息、使用信息

![img](https://images2015.cnblogs.com/blog/616953/201606/616953-20160629170530499-1935685549.png)



### (2) 索引节点
* 在检索目录文件时，只用到了文件名，仅当找到一个目录项（即其中的文件名与指定要查找的文件名相匹配）时，才需要从该目录项中读出该文件的物理地址，而其他一些对该文件进行描述的信息，在检索目录时一概不用，显然，这些信息在检索目录时不需要调入内存。
* 为此，在有的系统中，如UNIX系统，便采用了把文件名和文件描述信息分开的方法，亦即，使文件描述信息单独形成一个称为索引结点的数据结构，简称为i结点，在文件目录中的每个目录项由文件名和指向该文件所对应的i结点的指针所构成。

![img](https://images2015.cnblogs.com/blog/616953/201606/616953-20160629220451749-1048812791.png)


### (3) 目录结构

#### 1.  单级目录结构


![img](https://images2015.cnblogs.com/blog/616953/201606/616953-20160629192436109-1963104738.png)


#### 2. 两级目录结构
两级目录结构，为每个用户建立一个单独的用户文件目录UFD（User File Directory），这些文件目录具有相似的结构，由用户所有文件的文件控制块组成。此外，系统中还有一个主文件目录MFD（Master File Directory），在主文件目录中，每个用户目录文件都占有一个目录项，其目录项包括用户名和指向用户目录文件的指针。


![img](https://images2015.cnblogs.com/blog/616953/201606/616953-20160629191430843-2061259116.png)



#### 3. 多级目录结构
多级目录结构又称为树形目录结构，主目录被称为根目录，把数据文件称为树叶，其他的目录均作为树的结点。


![img](https://images2015.cnblogs.com/blog/616953/201606/616953-20160629194037327-113223554.png)

* 应该允许在一个目录文件中的目录项既是作为目录文件的FCB，又是数据文件的FCB
> 例如 /home目录下可以有目录文件也可以有数据文件


* 把从当前目录开始值得数据文件为止所构成的路径名称为相对路径名，而把从树根开始的路径名称为绝对路径名。
*  增加和删除目录:   
    * 不删除非空目录: 当目录不为空时，为了删除一个非空目录，必须先删除目录中所有的文件，使之称为空目录，然后再删除
    * 可删除非空目录: 将目录中的所有文件和子目录同时删除


### (4) 目录查询技术
* 线性检索法
> 个人理解就是顺着根目录一直往下查


* Hash方法，系统利用用户提供的文件名并将它转换为文件目录的索引值，再利用该索引值到目录中去查找，这将提高检索速度

<br />

# 五. 文件存储空间管理
> 这一章不是重点, 没仔细看.

### (1) 空闲表法

### (2) 空闲链表法

### (3) 位示图法

### (4) 成组链接法


