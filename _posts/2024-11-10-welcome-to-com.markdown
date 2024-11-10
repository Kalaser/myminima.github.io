---
layout: post
title:  "程序设计介绍"
date:   2024-11-10 19:36:59 +0800
categories: jekyll update


---

**计算机程序**

计算机技术发展的早期，[软件开发](https://zh.wikipedia.org/wiki/軟件開發)主要就是程序设计。但随着技术的发展，软件系统越来越复杂，逐渐分化出许多专用的软件系统，如[操作系统](https://zh.wikipedia.org/wiki/操作系统)、[数据库系统](https://zh.wikipedia.org/wiki/数据库系统)、[应用服务器](https://zh.wikipedia.org/wiki/应用服务器)，而且这些专用的软件系统愈来愈成为普遍的系统环境的一部分。这种情况下[软件开发](https://zh.wikipedia.org/wiki/軟件開發)的内容越来越丰富，不再只是纯粹的程序设计，还包括[数据库设计](https://zh.wikipedia.org/w/index.php?title=数据库设计&action=edit&redlink=1)、[用户界面设计](https://zh.wikipedia.org/wiki/用户界面设计)、[通信协议](https://zh.wikipedia.org/wiki/通信协议)设计和复杂的系统配置过程。

空间方面，在早期，由于机器资源比较昂贵，如何缩小存储空间往往是设计关心的首要重点；而随着[硬件](https://zh.wikipedia.org/wiki/计算机硬件)技术的飞速发展，电脑上资料存储媒体的价格降低，空间不再是考虑的第一要点，一些较耗时的运算也渐渐发展出以空间换取时间的模式。

时间方面，在早期，如何加强程序效率、缩短程序执行时间是程序员的共同目标；而在硬件性能进步、效率差距缩小，软件规模与复杂度却日益增加的现在，程序的结构、可维护性、重复使用性、弹性等因素更显得重要。在多人合作的程序设计项目里，程序员们会加上各种注解以协助其他参与者理解代码，此行为虽然对执行时间的缩短没有帮助，还会加重存储空间的负担[[来源请求\]](https://zh.wikipedia.org/wiki/Wikipedia:列明来源)，但却因能达到较好的沟通并提高代码的可维护性，而成为目前的主流。

然而，随着智能手机等携带设备的兴起，执行时间的缩短与存储空间的有效运用再次成为焦点，形成与主机服务器类型应用程序不同的重点考虑方向。

为了一个程序运行，计算机加载程序代码，可能还要加载数据，从而[初始化](https://zh.wikipedia.org/wiki/初始化)成一个开始状态，然后调用某种启动机制。在最低层上，这些是由一个[加载器](https://zh.wikipedia.org/wiki/載入器)开始的。

在大多数计算机中，[操作系统](https://zh.wikipedia.org/wiki/操作系统)例如[Windows](https://zh.wikipedia.org/wiki/Windows)等，加载并且执行很多程序。在这种情况下，一个计算机程序是指一个单独的[可执行](https://zh.wikipedia.org/wiki/可执行)的映射，而不是当前在这个计算机上运行的全部程序。

程序里的指令都是基于机器语言。程序通常由一个计算机程序设计语言编写，然后由该语言的编译器（或者，有时由汇编程序）编译为机器语言。

[C](https://zh.wikipedia.org/wiki/C语言)的[Hello World](https://zh.wikipedia.org/wiki/Hello_World)程序样例

```C
#include <stdio.h>
int main(void) {
    printf("Hello world!\n");
    return 0;
}
```

#### **冯诺依曼体系结构（普林斯顿结构）**

冯·诺伊曼结构又做普林斯顿结构，在一台基于最常见的冯诺依曼体系结构的计算机上，程序从某种外部设备，通常是[硬盘](https://zh.wikipedia.org/wiki/硬盘)，被加载到计算机之内。 如果计算机选择冯诺依曼体系结构，那么程序就被加载入内存。 指令序列顺序执行，直到一条跳转或转移指令被执行，或者一个[中断](https://zh.wikipedia.org/wiki/中断)出现。所有这些指令都会改变[指令寄存器](https://zh.wikipedia.org/wiki/指令寄存器)的内容。

基于这种体系的计算机，如果没有程序的支持，将无法工作。一个计算机程序是一系列指令的集合。

程序里的指令都是基于[机器语言](https://zh.wikipedia.org/wiki/机器语言)；程序通常首先用一种计算机[程序设计语言](https://zh.wikipedia.org/wiki/程序设计语言)编写，然后用[编译器](https://zh.wikipedia.org/wiki/編譯器)或者[解释器](https://zh.wikipedia.org/wiki/直譯器)翻译成机器语言。 有时，也可以用[汇编语言](https://zh.wikipedia.org/wiki/汇编语言)编程，汇编语言实质就是表示机器语言的一组记号－在这种情况下，用于翻译的程序叫做[汇编程序](https://zh.wikipedia.org/wiki/汇编程序)。

#### **操作系统**

**操作系统**（英语：Operating System，缩写：**OS**）是一组主管并控制[计算机](https://zh.wikipedia.org/wiki/电子计算机)操作、运用和运行[硬件](https://zh.wikipedia.org/wiki/计算机硬件)、[软件](https://zh.wikipedia.org/wiki/软件)[资源](https://zh.wikipedia.org/wiki/資源_(計算機科學))和提供公共[服务](https://zh.wikipedia.org/wiki/守护进程)来组织用户交互的相互关联的[系统软件](https://zh.wikipedia.org/wiki/系统软件)[程序](https://zh.wikipedia.org/wiki/程序)，同时也是计算机系统的内核与基石。操作系统需要处理如管理与配置[内存](https://zh.wikipedia.org/wiki/内存)、决定系统资源供需的优先次序、控制输入与输出设备、操作[网络](https://zh.wikipedia.org/wiki/计算机网络)与管理[文件系统](https://zh.wikipedia.org/wiki/文件系统)等基本事务。操作系统也提供一个让用户与系统交互的操作界面。

操作系统的类型非常多样，不同机器安装的操作系统可从简单到复杂，可从[移动电话](https://zh.wikipedia.org/wiki/移动电话)的[嵌入式系统](https://zh.wikipedia.org/wiki/嵌入式系统)到[超级计算机](https://zh.wikipedia.org/wiki/超级计算机)的[大型操作系统](https://zh.wikipedia.org/wiki/超级计算机#.E6.93.8D.E4.BD.9C.E7.B3.BB.E7.BB.9F)。许多操作系统制造者对它涵盖范畴的定义也不尽一致，例如有些操作系统集成了[图形用户界面](https://zh.wikipedia.org/wiki/图形用户界面)，而有些仅使用[命令行界面](https://zh.wikipedia.org/wiki/命令行界面)，将图形用户界面视为一种非必要的应用程序。

操作系统理论在[计算机科学](https://zh.wikipedia.org/wiki/计算机科学)中，为历史悠久而又活跃[[1\]](https://zh.wikipedia.org/wiki/操作系统#cite_note-1)的分支；而操作系统的设计与实现则是软件工业的基础与内核[[2\]](https://zh.wikipedia.org/wiki/操作系统#cite_note-2)。

![img](https://upload.wikimedia.org/wikipedia/commons/thumb/d/d8/Operating_system_architecture.svg/400px-Operating_system_architecture.svg.png)
