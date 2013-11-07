---
author: liangzhongxing
comments: true
date: 2013-05-23 02:30:54+00:00
layout: post
slug: linux%e7%b3%bb%e7%bb%9f%e5%86%85%e5%ad%98%e7%9b%91%e6%8e%a7%e5%85%a8%e9%9d%a2%e8%ae%b2%e8%a7%a3%ef%bc%9afree%e5%91%bd%e4%bb%a4
title: Linux系统内存监控全面讲解：free命令
wordpress_id: 279
categories:
- 操作系统
---

在Windows系统中查看内存的使用情况很简单，想必大家都已经耳熟能详了，那么在Linux系统如何查看内存使用情况呢？下面和大家分享在Linux系统下查看内存使用情况的free命令：

[root@scs-2 tmp]# free
total used free shared buffers cached
Mem: 3266180 3250004 16176 0 110652 2668236
-/+ buffers/cache: 471116 2795064
Swap: 2048276 80160 1968116

下面是对这些数值的解释：

total:总计物理内存的大小。

used:已使用多大。

free:可用有多少。

Shared:多个进程共享的内存总额。

Buffers/cached:磁盘缓存的大小。

第三行(-/+ buffers/cached):

used:已使用多大。

free:可用有多少。

第四行就不多解释了。

区别：第二行(mem)的used/free与第三行(-/+ buffers/cache) used/free的区别。 这两个的区别在于使用的角度来看，第一行是从OS的角度来看，因为对于OS，buffers/cached 都是属于被使用，所以他的可用内存是16176KB,已用内存是3250004KB,其中包括，内核（OS）使用+Application(X, oracle,etc)使用的+buffers+cached.

第三行所指的是从应用程序角度来看，对于应用程序来说，buffers/cached 是等于可用的，因为buffer/cached是为了提高文件读取的性能，当应用程序需在用到内存的时候，buffer/cached会很快地被回收。

[Linux Buffers和Cached的区别](http://blog.chinaunix.net/uid-10697776-id-3292165.html)：

buffers是为块设备设计的缓冲。比如磁盘读写，把分散的写操作集中进行，减少磁盘I/O，从而提高系统性能。比如入U盘里cp一个文件，但是U盘读写指示灯未闪动，过了一会儿才闪动。卸载时会清空缓冲，所以有时卸载一个设备需要等待几秒。

    cached是缓存读取过的内容，下次再读时，如果在缓存中命中，则直接从缓存读取，否则读取磁盘。由于缓存空间有限，过一段时间以后没用的缓存会被移动到swap里面，所以有时看到物理内存还有很多，swap就被利用了。

所以从应用程序的角度来说，可用内存=系统free memory+buffers+cached。

如上例：

2795064=16176+110652+2668236

接下来解释什么时候内存会被交换，以及按什么方交换。 当可用内存少于额定值的时候，就会开会进行交换。

如何看额定值：

cat /proc/meminfo
[root@scs-2 tmp]# cat /proc/meminfo
MemTotal: 3266180 kB
MemFree: 17456 kB
Buffers: 111328 kB
Cached: 2664024 kB
SwapCached: 0 kB
Active: 467236 kB
Inactive: 2644928 kB
HighTotal: 0 kB
HighFree: 0 kB
LowTotal: 3266180 kB
LowFree: 17456 kB
SwapTotal: 2048276 kB
SwapFree: 1968116 kB
Dirty: 8 kB
Writeback: 0 kB
Mapped: 345360 kB
Slab: 112344 kB
Committed_AS: 535292 kB
PageTables: 2340 kB
VmallocTotal: 536870911 kB
VmallocUsed: 272696 kB
VmallocChunk: 536598175 kB
HugePages_Total: 0
HugePages_Free: 0
Hugepagesize: 2048 kB

用free -m查看的结果：

[root@scs-2 tmp]# free -m
total used free shared buffers cached
Mem: 3189 3173 16 0 107 2605
-/+ buffers/cache: 460 2729
Swap: 2000 78 1921

查看/proc/kcore文件的大小（内存镜像）：

[root@scs-2 tmp]# ll -h /proc/kcore
-r——– 1 root root 4.1G Jun 12 12:04 /proc/kcore

备注：占用内存的测量

测量一个进程占用了多少内存，Linux系统为我们提供了一个很方便的方法，/proc目录为我们提供了所有的信息，实际上top等工具也通过这里来获取相应的信息。

/proc/meminfo 机器的内存使用信息
/proc/pid/maps pid为进程号，显示当前进程所占用的虚拟地址。
/proc/pid/statm 进程所占用的内存
[root@localhost ~]# cat /proc/self/statm
654 57 44 0 0 334 0

输出解释

CPU 以及CPU0。。。的每行的每个参数意思（以第一行为例）为：

参数 解释 /proc//status

Size (pages) 任务虚拟地址空间的大小 VmSize/4

Resident(pages) 应用程序正在使用的物理内存的大小 VmRSS/4

Shared(pages) 共享页数 0

Trs(pages) 程序所拥有的可执行虚拟内存的大小 VmExe/4

Lrs(pages) 被映像到任务的虚拟内存空间的库的大小 VmLib/4

Drs(pages) 程序数据段和用户态的栈的大小 （VmData+ VmStk ）4

dt(pages) 04

查看机器可用内存

/proc/28248/>free
total used free shared buffers cached
Mem: 1023788 926400 97388 0 134668 503688
-/+ buffers/cache: 288044 735744
Swap: 1959920 89608 1870312

我们通过free命令查看机器空闲内存时，会发现free的值很小。这主要是因为，在Linux系统中有这么一种思想，内存不用白不用，因此它尽可能的cache和buffer一些数据，以方便下次使用。但实际上这些内存也是可以立刻拿来使用的。

所以 空闲内存=free+buffers+cached=total-used
