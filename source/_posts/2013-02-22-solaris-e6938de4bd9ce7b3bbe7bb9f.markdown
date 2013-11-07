---
author: jane
comments: true
date: 2013-02-22 08:37:14+00:00
layout: post
slug: solaris-%e6%93%8d%e4%bd%9c%e7%b3%bb%e7%bb%9f
title: Solaris 操作系统(马美玲)
wordpress_id: 76
categories:
- 英文翻译
---

来自维基百科，自由百科全书

Solaris是最初由IT及互联网技术服务公司开发的一种Unix操作系统。在1993年，它取代了Sun最初的操作系统SunOS。自从2010年1月Sun由甲骨文公司收购后，现在大家所知道的Oracle Solaris已经归属于美国甲骨文软件公司。

Solaris以其可扩展性闻名，特别是在sun公司的工作站系统中；同时它产的一些创新的特征也是非常有用的，例如DTrace动态跟踪、ZFS动态文件系统以及Time Slider。Solaris支持基于SPARC与x86的工作环境和来自Sun与其他供应商的服务，并正在努力提供更多的附加平台。Solaris被注册作为Unix单一的被承认的规范说明。

Solaris原本是作为专利性的软件发展的，然而在2005年6月Sun Microsystems发布了其大部分基于CDDL许可的代码，且建立了OpenSolaris开源项目。基于OpenSolaris，Sun希望可以建立一个围绕软件的开发者与用户讨论社区团体。在2010年1月收购Sun后，甲骨文公司决定停止支持OpenSolaris项目的发展。在甲骨文公司内部宣布这个决定前的十天，消息已经泄露出去了；Garrett D’ Amore宣布illumos项目，产生了许多Solaris内核与声明甲骨文Solaris之前的一些常用的功能。

在2010年8月，甲骨文公司停止提供Solaris内核的公用升级资源，有效地推动Solaris11变成一个闭源的专利性操作系统。然后通过OTN，工业伙伴仍可以得到升级的Solaris源代码，而用户则可以到甲骨文公司网站下载Solaris 11的开源部分源代码。


**目录**




**1 ****历史………………………………………………………………………………………………****3**




**2 ****支持机构…………………………………………………………………………………………****3**




**2.1 ****其他平台……………………………………………………………………………………******…******3**




**3 ****安装与使用选择…………………………………………………………………………………****3**




**3.1 ****安装的使用…………………………………………………………………………………******…******4**




**3.2 ****无需安装的使用……………………………………………………………………………******…******5**




**4 ****桌面环境…………………………………………………………………………………………****5**




**5 ****许可证………………………………………………………………………………………******…********…******6**




**6 ****版本历史…………………………………………………………………………………………****7**




**7 ****开发版本…………………………………………………………………………………………****10**




**8 ****另见………………………………………………………………………………………………****11**




**9 ****其他链接…………………………………………………………………………………………****11**




**历史**

在1987年，AT&T和Sun宣布他们将合作做一个项目，关于合并当时在市场上最出名的Unix系统：BSD，System V以及Xenix。这个后来便成为了Unix System V Release4（SVR4）。

在1991年9月4日，Sun宣布基于SVR4的系统会替代现存的BSD衍生的Unix系统SunOS 4。其被内部认定为SunOS 5，但是同时出现了一个新的市场名称Solaris 2 。当SunOS4.1.x由Sun命名为Solaris 1之后，Solaris的名称几乎都参考使用SVR4衍生的SunOS 5.0和之后版本。

为这个的辩护就是其不仅包含了SunOS，还包含了openwindows图形用户界面与ONC功能。这个小版本的SunOS包括在Solaris的发布版本号中；例如，Solaris 2.4合并到SunOS 5.4中。在Solaris 2.6之后，Sun丢弃了版本号中的“2.”，所以Solaris 7合并到SunOS 5.7中，而最近发布的SunOS 5.11.1则构成了Solaris 11.1的核心。



**支持机构**

Solaris用的是一个基于其支持的平台SPARC与i86pc（包含x86和x86_64）的通用代码.

Solaris在适用于匀称多重处理方面有很好的信誉，支持多核CPU。它历来是紧密集成于Sun的SPARC硬件(包括支持64位应用程序从Solaris SPARC 7)，以一个组合包发布。这个曾经导出更多可信赖的的系统，而没有花费大量的资源在PC的硬件上。然而，自从Solaris 2.1发布之后它也支持x86系统；同时，Solaris 10之后它都包含了64位x86应用的支持，允许Sun利用可用的基于64位cpu 的x86 - 64体系结构的产品。Sun曾经非常热销Solaris的使用，关于其“x64”工作站与基于AMD Opteron和英特尔至强处理器的服务器以及由戴尔、惠普和IBM制造的x86系统。截至2009年，支持Solaris作为x86服务系统的有以下供应商：



	
  * 戴尔 ——将“测试、认证和优化Solaris和OpenSolaris其强大的服务器并将其提供作为在整个戴尔软件菜单几种选择之一”

	
  * IBM ——也对基于x86 IBM System x服务器与BladeCenter服务器的Solaris与Solaris认购作出了贡献

	
  * 因特尔

	
  * 休利特-帕卡德 ——贡献与提供在Proliant与blade系统的Solaris软件技术支持

	
  * 富士通 西门子


截至2010年，戴尔与惠普保证和重新发售在其各自的x86平台上的Oracle Solaris、Oracle Enterprise Linux、Oralce VM。同时，IBM停止直接支持x64的Solaris。

☆**其他平台**

Solaris 2.5.1包括对PowerPC平台的支持，但是其端口在Solaris 2.6发布前已经被取消。在2006年1月，一个Blastwave的开发团体开始为名为北极星的PowerPC端口工作。在2006年的10月，一个基于Blastwave成果与Sun的关于Solaris 2.5.1相关部分重整到OpenSolaris中的Pulsar实验室项目的OpenSolaris项目团体宣布其首次发布官方代码源。

一个通向因特尔安腾处理器架构的Solaris端口在1997年已发布，但从未投入市场中。

在2007年11月28日，IBM，Sun与Sine Nomine Associates示范了z系统OpenSolaris在IBM的基于z/VM的z系统主机上运行的预览，命名为天狼星（类似于北极星项目，同时也是归因于主要开发者的澳大利亚国籍：1786年的HMS Sirius是一艘开往澳大利亚第一舰队的船。）在2008年10月17日，一个标准的天狼星发布版本已经在提供；同年11月19日，IBM把天狼星在z系统的使用授权给IFL处理器。

Solaris也支持ABI的Linux平台，允许在x86系统上运行本土的双星Linux。这个特征命名为Solaris关于Linux的应用程序或者是SCLA，是基于由Solaris 10 8/07引进的品牌区域功能。



**安装与使用选择**

Solaris可以由不同预包装集团的软件安装，包括有从减少网络支持到全网络支持OEM。Solaris的安装并不一定需要个别使用系统。其他的软件如Apache，MySQL等也可以由sunfreeware、OpenCSW与Blastwave安装。

☆**安装的使用**

Solaris可以安装作为物理使用资源或者是在桌面上的网络使用或者是服务器功用。Solaris可以交互式地在无需图形与鼠标操作的命令行控制台安装。这个可能是在一个远程的数据中心选择服务器，从一个终端服务器甚至是拨号解调调制器中。

Solaris也可以交互式地利用图形界面安装。这个可能是选择个人工作环境或者是手提电脑的，在一个平常运行的控制台的本地环境中。

Solaris可以在网络上自动安装。系统管理员可以根据说明与配置文件定制安装，包括配置和自动安装第三方软件，而无需购买其他的软件管理功用。

当Solaris已经安装成功后，操作系统会属于同一个安装时配置的系统。应用程序可能会单独地在本地系统安装，或者可能会挂载到网络上远程的一个系统。

☆**无需安装的使用**

Solari可以在无需分开安装在操作系统的情况下作为桌面或者服务使用。

Solaris可以由一个在无磁盘环境下提供操作系统映像的远程服务中引导出，或者是一个其内部磁盘只用于分区的环境中引导出。在这个配置下，操作系统仍能在本地运行系统。应用程序可能或者不属于本地运行的。这个可能需要选择企业或者是教育机构，其快速设置是必需的（工作站可能会在运行中崩溃，那么新的MAC地址注册到一个中央服务器，插入到其中，便立即可用。），或者是其快速更换也是必需的（如果一个桌面发生硬件故障，一个新的工作站将从一个密室空间插入到其中，用户可用恢复他们的工作到上一次的保存点）。

Solaris也可以作为单客户端使用。应用程序、操作系统、窗户管理以及图形界面可以运行在一个或多个远程服务器上。管理员可以增加用户账户到一个中心Solaris系统中，同时一个单客户端可以在一个密室空间中运转与放置在桌面，而且一个用户可以马上开始工作。如果发生硬件故障，单客户端可以转换，再且不管工作是否有保存，用户都可以恢复他们的工作到准确的任务失败点。



**桌面环境**

Solaris早期发布使用的图形界面是以OpenWindows作为标准桌面环境。对于Solaris 2.0至Solari 2.2，OpenWindows既支持NeWS与X应用，也为来源于Sun的旧版桌面环境的SunView的应用提供向后兼容性。NeWS允许应用程序建立一个以面向对象方式使用附言（一种在1982年发布的常用印刷语言）。X窗口系统起源于1984年MIT的雅典娜项目，允许一个应用程序的显示是一个断开的机器正在运行应用程序，并被断开了网络连接。Sun的原始绑定的SunVies应用组合被移植到X系统中。

Sun后来放弃了对遗留的SunView应用与NeWS与OpenWindows 3.3的支持，其中NeWS承载着Solaris 2.3；转而支持X11R5的显示附言。图形界面与感觉保持了基于OPEN LOOK的本来面目。OpenWindows 3.6.2是在Solaris 8之后最后发布的版本。OPEN LOOK窗口管理器（OLWN）与其他OPEN LOOK具体应用都放弃了Solaris 9；但支持库仍绑定，提供现有应用的长期二进制向后兼容性。OPEN LOOK虚拟窗口管理器（OLVWM）仍然可以为Solaris下载来自sunfreeware的应用，也为最近的Solaris 10发布工作。

Sun与其他的Unix供应商创造了一个企业联盟来标准化Unix的桌面系统。作为COSE的一名成员，一个公共开源软件环境，Sun主动帮助完善公共桌面环境。CDE主动去创建一个标准的Unix桌面环境。每一个供应商作出了不同的贡献：Hewlett-Packard贡献了窗口管理器；IBM提高了文件管理系统，而Sun提供了邮件与日历功能以及拖放支持（tooltalk）。这个新的桌面环境是基于主题的外观和感觉的，而旧的OPEN LOOK桌面环境被认为有保留下来。CDE通过多家open system供应商统一了Unix桌面环境的标准。CDE有Solaris 2.4与2.5的附加绑定功能，包括在Solaris2.6至2.10。CDE应用程序不再包含在OpenSolaris和Solaris 11中，但许多库还保存着二进制的向后兼容性。

2001年，Sun发表了对Solaris8的基于GTK+工具包的开源桌面环境GNOME的预览版本Solaris 9 8/03介绍GNOME 2.0作为CDE的一个替代版本。Solaris 10包含Sun的Java桌面系统（JDS），它是基于GNOME的并带有一组庞大的应用程序，包括StarOffice（Sun的办公套件）。Sun描述JDS作为Solaris 10的主要部件。

开源桌面环境KDE与Xfce，以及众多其他的窗口管理器，也还编译和运行在Solaris的最新版本上。


20003年，Sun投资了一个名为Looking Glass的新的桌面环境项目。这个项目自2006年年底以来一直无所作为。




**许可证**

Solaris的源代码（除了少数例外）已经发布在通过OpenSolaris项目发布在共同发展和分配许可证（CDDL）上。CDDL是一份OSI认可的许可证。它被自由软件基金会认为是免费的但GPL并不符合它。

2005年6月14日，OpenSolaris起源于早期开发代码基；包括二进制和源版本都是免费下载与许可证免费的。而对于即将出现的特征资源，比如Xen现在理所当然地支持添加OpenSolaris项目，Sun曾表示现在的Solaris的版本将适合今后来自OpenSolaris的版本。



**版本历史**

Solaris的显著特征目前包括DTrace、Doors、服务管理功能、Solaris Containers、Solaris多路I/O、Solaris卷管理器、ZFS以及Solaris可信扩展。定期更新Solaris的版本发布，如Solaris 10 10/09.

按升序排列，Solaris发布的版本有如下：

其中红色代表版本不再支持，绿色代表发布并支持，蓝色代表将来的版本。











**Solaris****版本**








**SunOS****版本**








**发布日期**








**结束的支持**








**主要的新特性**












**SPARC**








**x86****的**












1.x中








4.1.x版








1991年至1994年








-








2003年9月








SunOS 4上的Solaris 1更名为营销目的。更多信息，请参阅SunOS文章。












2.0








5








1992年6月








-








1999年1月








初步版本（主要是提供给开发人员只），只有sun4c体系结构的支持。首先出场的NIS+。












2.1








5.1








1992年12月








1993年5月








1999年4月








支持的sun4和sun4m体系结构;第一Solaris x86的版本。首先Solaris 2的发布，支持SMP。












2.2








5.2








1993年5月








-








1999年5月








发布SPARC只。首先sun4d体系结构的支持。第一个支持多线程库（UI线程API在的Libthread）。












2.3








5.3








1993年11月








-








2002年6月








SPARC只发行。OpenWindows 3.3开关新闻显示PostScript和下降三源支持。支持增加了对autofs和CacheFS文件系统。












2.4








5.4








1994年11月








2003年9月








第一个统一的SPARC/x86释放。OSF/Motif的运行时支持。












2.5








5.5








1995年11月








2003年12月








首先，以支持UltraSPARC和包括CDE，NFSv3的 NFS / TCP。掉落的sun4（VME总线）的支持。POSIX.1c-1995pthreads的增加。门，但没有证件。












2.5.1








5.5.1








1996年5月








2005年9月








只有推出支持PowerPC平台;超企业的支持;用户ID和组ID（将uid_t，gid_t的）扩展到32位，也包括处理器集和早期资源管理技术。












2.6








5.6








1997年7月








2006年7月








包括的Kerberos 5，PAM的TrueType字体的WebNFS，大文件的支持，增强了procfs的。SPARCserver的600MP一系列支持下降。












7








5.7








1998年11月








2008年8月








第64位UltraSPARC释放。增加了原生支持的文件系统元数据记录（UFS日志记录）。在x86平台上掉落MCA的支持。太阳下降的前缀“2”。在Solaris版本号，留下的“Solaris 7”。最近一次更新是Solaris 7的11/99。












8








5.8








2000年2月








2012年3月








包括多路径I/O的Solstice DiskSuitice，IPMP，第一款支持的IPv6和IPsec（手动密钥只有），MDB模块调试。介绍了基于角色的访问控制（RBAC）删除sun4c的支持。最后更新是Solaris 8 2/04。












9








5.9








2002年5月28日








2003年1月10日








2014年10月








iPlanet目录服务器，资源管理器，扩展的文件属性，IKE IPSec密钥，和Linux的兼容性; OpenWindows的下降，删除sun4d支持。目前，大多数的更新是Solaris 9 9/05 HW（“U9”）。












10








5.10








2005年1月31日








2018年1月








包括x86-64的（AMD64/Intel 64）的支持，使用DTrace（动态跟踪），Solaris容器、服务管理工具（SMF），取代初始化脚本，NFSv4的。最小权限的安全模型。支持sun4m和UltraSPARC I处理器的去除。支持EISA为基础的个人电脑中删除。添加Java桌面系统（基于GNOME）作为默认的桌面。






	
  * 


Solaris 10的1/06（内部称为“U1”）添加GRUB引导装载程序的x86系统，支持的iSCSI启动器和fcinfo命令行工具。




	
  * 


的Solaris 10 6/06（“U2”）增加了ZFS文件系统。




	
  * 


的Solaris 10 11/06（“U3”）增加了Solaris高可靠扩展和逻辑域。




	
  * 


的Solaris 10 8/07（“U4”）补充说：桑巴Active Directory支持， IP实例（OpenSolaris的网络虚拟化和资源控制项目的一部分），支持的Iscsi目标的Linux应用程序的Solaris容器（根据品牌区），的资源上限设置守护进程（rcapd）的增强版本。




	
  * 


的Solaris 10 5/08（“U5”）增加了CPU上限的Solaris Containers，性能改进[的](http://en.wikipedia.org/wiki/SpeedStep)[SpeedStep](http://en.wikipedia.org/wiki/SpeedStep)支持英特尔处理器[的](http://en.wikipedia.org/wiki/PowerNow!)[PowerNow](http://en.wikipedia.org/wiki/PowerNow!)[！](http://en.wikipedia.org/wiki/PowerNow!)对AMD处理器的支持。




	
  * 


从ZFS的Solaris 10 10/08（U6）添加启动，可以使用ZFS作为根文件系统。Solaris 10 10/08中还包括虚拟化增强功能，包括能够为Solaris容器自动更新它的环境中，当从一个系统移动到另一个，逻辑域支持可动态重新配置的磁盘和网络I / O，和半虚拟化支持时使用的Solaris 10[]](http://en.wikipedia.org/wiki/Solaris_(operating_system)#cite_note-53)作为一个客户操作系统在基于Xen的环境中，如Sun xVM服务器。




	
  * 


的Solaris 10 5/09（“U7”）更好的性能和电源管理支持英特尔[的](http://en.wikipedia.org/wiki/Nehalem_(microarchitecture))[Nehalem](http://en.wikipedia.org/wiki/Nehalem_(microarchitecture))处理器，集装箱克隆使用ZFS克隆的文件系统，ZFS的[固态驱动器](http://en.wikipedia.org/wiki/Solid-state_drive)的性能增强。




	
  * 


的Solaris 10 10/09（“U8”）添加用户和组级的ZFS配额，ZFS缓存设备和nss_ldap shadowAccount支持的的，修补性能的改进。




	
  * 


的Solaris 10 9/10（“U9”）增加物理区域迁移，ZFS三重奇偶校验RAID-Z和Oracle Solaris自动注册。




	
  * 


的Solaris 10 8/11（“U10”）增加了ZFS的速度提升和新功能，Oracle数据库优化，更快的SPARC系统上重新启动。















11快2010.11








5.11








十一月15，2010








-








添加新的包装系统（IPS -映像包管理系统）和相关的工具，Solaris 10容器，网络虚拟化和QoS，虚拟控制台，ZFS加密和重复数据删除，重新启动快，更新[GNOME](http://en.wikipedia.org/wiki/GNOME)。删除[Xsun](http://en.wikipedia.org/wiki/Xsun)[的](http://en.wikipedia.org/wiki/Xsun) CDE。












11








5.11








11月9日








2024年11月








在软件包装，网络虚拟化，服务器虚拟化，存储，安全性和硬件支持的新功能和增强功能（相比于Solaris 10）：






	
  * 


包装：映像包管理系统，网络和本地软件包系统信息库中自动安装，自动配置，包括区域发行版构造函数来创建[ISO 9660](http://en.wikipedia.org/wiki/ISO_9660)文件系统映像;




	
  * 


网络：网络虚拟化（的VNIC，的vSwitch的，vRouters，）和[服务质量](http://en.wikipedia.org/wiki/Quality_of_Service)，专用IP默认情况下，为区域，使用dladm实用程序来管理数据链路，ipadm实用程序来管理[IP](http://en.wikipedia.org/wiki/Internet_Protocol)配置（包括[IPMP](http://en.wikipedia.org/wiki/IP_network_multipathing)），[ProFTPD](http://en.wikipedia.org/wiki/ProFTPD)[的](http://en.wikipedia.org/wiki/ProFTPD)和增强的;




	
  * 


区域：不可变的（只读）区，NFS服务器的区域中，委托管理，P2V飞行前检查，的zonestat工具，加上libzonestat动态链接库;




	
  * 


根的作用，netcat的和增强的安全性;




	
  * 


存储：ZFS影子迁移，ZFS备份/恢复NDMP，递归ZFS发送;




	
  * 


硬件支持：SPARC T4，关键线程，SDP启用和优化，包括支持区，SR-IOV，英特尔AVX;




	
  * 


删除的UltraSPARC II，III，IV系列支持删除; [IA-32](http://en.wikipedia.org/wiki/IA-32)体系结构的支持。














**开发版本**

自1980年代后期开始的关于后来发布的Solaris 2.0的工作后，Solaris底层的代码就一直在发展着。每个版本如Solaris 10是基于发展的代码库的快照，在拍摄时间附近发布版本，然后作为一个派生的项目。这个项目的更新建立并交付了一年几次，直到下一个官方版本的发布出来为止。

自2005年发布的Solaris10的代号为内华达之后，由Sun开发的Solaris版本是由现在的OpenSolaris代码基衍生出来的。

在2003年，另外的Solaris开发过程已经启动。在程序名为Solaris快速软件（或Solaris快递）之中，一个基于当前发展基础的二进制版本在每月底可以允许任何人下载来尝试新的功能与测试其操作系统的质量和稳定性，以使其进展到下一个官方的Solaris版本的发布。后来该计划改变为推出一个季度的发行模式，并改名为Solaris Express开发版（SXDE）。

在2007年，Sun公司宣布该印第安纳州项目有以下几个目标，包括提供一个开放源码的二进制分发版的OpenSolaris项目，以取代SXDE。其第一个发布版本为OpenSolaris 2008.05.

Solaris Express社区版（SXCE）是专门为OpenSolaris的开发人员发布的。它每两周更新一次，直到它在2010年1月被中断了，并建议用户迁移到OpenSolaris发行版。虽然下载许可接受许可协议的形式显示出来，当用户安装这些图像下载文件时，它的使用仅限于个人、教育以及评估的目的。

SXCE发布终止于build 130，而OpenSolaris发布终止于几个星期后的build 134。下一个基于build 134的OpenSolaris发布版本在2010年3月到期，即使安装包有存储库的包，但它从未完全发布。相反，甲骨文更名为Solaris 11 Express的二进制分发版本，修改了许可条款并作为2010.11在2010年11月发布为build 151a。



**另见**



	
  * Blastwave ——生产Sparc和x86/AMD64的Solaris 8以上的软件套件

	
  * 操作系统的比较

	
  * Illumos

	
  * OpenCSW ——软件分叉Blastwave中

	
  * OpenSolaris

	
  * 操作系统时间表

	
  * Sun Management Center

	
  * Sun xVM




**其他链接**



	
  * 


Solaris官方主页




	
  * 


开放式目录项目的Solaris




	
  * 


在Solaris 10 JDS截图




	
  * 


Sun/Solaris上的新闻、引用和信息




	
  * 


Solaris博客





