第一章 基本概念
==============

提纲
------------
* 性能与结构
* 结构、组成与实现
* 计算机中的并行技术
* 性能评估指标


1.1 性能与结构
--------------

### 体系结果对性能的作用
1. CPU提升速度比不过整体性能提升速度（体系结构提升影响大）
2. 单核提升空间有限，多核提升速度（体系结构起作用）

### 体系结构核心思想
1. 加快经常性事件（什么意思？）
2. 并行处理加快速度 

### 计算机的层次结构
1. 应用语言机器
2. 高级语言机器
3. 汇编语言机器
4. 操作系统机器
5. 逻辑机器
6. 微程序机器

体系结构研究的是软件和硬件的交界处，即操作系统机器和逻辑机器之间。


1.2 结构、组成与实现
---------------------------------------------------

关心__数据流__和__控制流__的组成和逻辑实现。

### 主要关心的方面
1. 数据通路宽度（总线上一次传输的数据位数）
2. 专用部件的安排（乘法器，字符处理部件等，安排多少个等）
3. 各个操作对部件的共享程度（数据依赖关系）
4. 部件的并行化
5. 控制机构的组成（是硬相连控制还是微程序控制）
6. 缓冲和排队（缓冲缓解速度差异， 排队就是各种调度算法）
7. 分支预测（预测下一步的指令）

### 可移植性的实现
1. 统一高级语言（所有程序员使用一种高级语言，有各种困难）
2. 采用系列机（不同机器统一机器语言和汇编语言，从体系结构上支持移植）
3. 模拟和仿真（虚拟机等，效率很低）

### 模拟和仿真的区别
* 模拟 -- 机器语言 -- 代码存在主存
* 仿真 -- 微指令  -- 代码存放在控制器

模拟更容易实现，仿真更底层速度更快

### 操作系统兼容性 POSIX("Portable Operating System Interface")
希望统一操作系统。


1.3 并行技术
---------------------------------------------------
区分并行和并发（同一时间段内发生）

### 执行程序的并行级别
1. 指令内部（指令内部各个微操作之间的并行）
2. 指令之间（多条指令并行）
3. 任务或进程之间
4. 作业和程序之间

### 处理数据的并行级别
1. 位串字串。只对一个字的一位进行处理，串行单处理机
2. 位并字串。对同一字的全部位进行处理，并行单处理机
3. 位片串字并。对许多字的同一位（称为：位片）进行处理
4. 全并行。对许多字的许多位进行处理。

### 从信息处理的各个步骤来看的并行级别
1. 存储器操作并行（单体多字、多体单字、多体多字等方式访问存储器）
2. 处理器操作步骤并行（一条指令有：取值、分析、执行等步骤，把他们并行化）
3. 处理器操作并行（支持向量、数组运算。对多个数组同时操作，阵列处理机等）
4. 指令、任务、作业并行（高级别的并行）

### 并行的途径
1. 时间重叠（同一时间干若干事）
2. 资源重复
3. 资源共享
（2、3的区别？）

### 并行处理计算机根据结构分类
1. 流水线计算机（时间重复）
2. 阵列处理机（资源重复）
3. 多处理机（资源共享。又分为紧耦合和松耦合两类）
4. 数据流计算机

### 多机系统的耦合度
多级系统是多台处理机组合形成的单一计算机系统，耦合度用来衡量不同处理机联系的紧密程度。
* 松散耦合：通过网络等通信线路连接
* 紧密耦合：通过系统总线连接

### Flynn 分类法 (对计算机系统进行分类)
* SISD - Single instruction, single data (流水线计算机，冯.诺依曼机)
* SIMD - Multiple instruction, single data (这种比较少见)
* MISD - Single instruction, multiple data (向量机，阵列机)
* MIMD - Multiple instruction, multiple data (多处理机，多机系统)

David J.Kuck和冯泽云也分别提出了其他的分类方法，（见P83，P84）  
P85有对上述分类的图形描述。


1.4 性能评估指标
---------------------------------------------------

### 基本参数
* [CPI](http://en.wikipedia.org/wiki/Cycles_per_instruction) - Cycles per instruction
* [IPS](http://en.wikipedia.org/wiki/Instructions_per_second) - Instructions per second (or MIPS, million instructions per second)
* [FLOPS](http://en.wikipedia.org/wiki/FLOPS) - FLoating-point Operations Per Second

### 加速比性能定律 / 定量设计原理 (为何这么叫？)
1. Amdahl 原理 - 增加处理机性能改善有极限，加速比降低
2. Gustafson 定律
3. Sun Ni 定律
这部分pdf没讲清楚，看教科书。uwhpc讲了Amdahl原理。  


进度
-----------------------
2014年 05月 28日 星期三 19:47:50 HKT  
p73  
2014年 05月 28日 星期三 23:49:09 HKT  
Done  
