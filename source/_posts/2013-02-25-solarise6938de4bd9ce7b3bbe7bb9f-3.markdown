---
author: zhengzhiteng
comments: true
date: 2013-02-25 02:30:50+00:00
layout: post
slug: solaris%e6%93%8d%e4%bd%9c%e7%b3%bb%e7%bb%9f-3
title: Solaris操作系统(郑志腾)
wordpress_id: 136
categories:
- 英文翻译
---

Solaris(操作系统)

Solaris是最初由Sun公司开发的一款Unix操作系统。在1993年，Solaris主要用于取代之前的SunOS(另一款由Sun公司开发的Unix操作系统)。而今，众所周知，自从2010年1月Sun公司被Oracle公司收购之后，Solaris已归Oracle公司所有，并更名为Oracle Solaris。

Solaris以良好的可扩展性而著称，特别是在SPRAC的系统上，创造了许多创新性特征，如DTrace、ZFS、Time Slinder。Solaris支持基于SPARC和基于x86的由Sun公司或其他提供商提供的工作站和服务器，并且持续增加对其他平台的支持。Solaris也注册并遵守Single Unix Specification(一套标准)。

Solaris曾经是一款专有软件，直到2005年6月Sun公司基于CDDL许可证发布了大部分的代码库，并且建立了名为OpenSolaris的开源项目。依靠OpenSolaris，Sun公司想要建立一个围绕着软件的开发者与用户社区。自从2010年1月Oracle公司收购了Sun公司后，Oracle决定中止OpenSolaris的发布与开发模式。就在一场向员工宣布这个决定的Oracle内部通知泄露的十天之前，Garrett D'Amore已经宣布了illumos计划，该计划用于创建一个Solaris内核的分支以及开展一个健壮的Oracle Solaris备用。

在2010年8月，Oracle中止了对Solaris内核源码公开更新的支持，实际上将Solaris11转变为一款闭源的专有操作系统。但是，通过Oracle在线技术支持，行业伙伴仍然能够获取正在开发的Solaris源码。Solaris11的开源部分在Oracle官网能够下载。



内容



	
  1. 历史

	
  2. 支持架构


其他平台

	
  1. 安装与使用指引


安装使用

免安装使用

	
  1. 桌面环境

	
  2. 许可证

	
  3. 版本历史

	
  4. 开发版本

	
  5. 参见

	
  6. 引用

	
  7. 外部链接






历史

1987年，AT&T公司和Sun公司联合宣布，他们将合作推出一个项目用于融合当时市场上最流行的Unix衍生操作系统，如BSD、System V和Xenix，这就是后来的Unix System V Release 4 (SVR4)。

1991年9月4日，Sun公司宣布即将以一个基于SVR4的操作系统来代替它现有由BSD衍生出的名为SunOS 4的Unix系统。这个操作系统内部命名为SunOS 5，但是一个与此同时一个新的市场名称出现了，那就是Solaris 2。当SunOS 4.1._x_ 微版本被Sun公司追溯为Solaris 1时，Solaris名称几乎被专有地用于有关由SVR4衍生出来的SunOS 5及其后续版本。

这种新品牌的合理解释是这种现象不仅包括SunOS，而且包括开放窗口可视化用户界面和开放网络计算功能。SunOS迷你版包括在Solaris发布版中，例如Solaris2.4包括SunOS5.4。在Solaris 2.6后，Sun公司将“2”从版本号中去掉，如此一来，Solaris 7便包括了SunOS 5.7，最新发布的SunOS 5.11是组成了Solaris 11的核心部分。





支持架构

Solaris提供了一个共同的代码库给与它所支持的平台，包括了SPARC和i86pc(x86和x86_64)。

Solaris以兼容symmetic multiprocessing和支持大多数CPU而出名。Solaris曾经被紧密地嵌入到Sun公司的SPARC硬件中(从Solaris 7开始还支持64位SPARC应用)，同时作为一个组合包而销售。这样会导致出现更多可靠的系统，但是会造成在商用个人电脑硬件上的额外开支。但是，从Solaris 2.1开始有了对x86系统的支持，同时从Solaris 10开始有了对64位x86应用的支持，这使得Sun公司能够估算基于x86_64体系的64位CPU的有利价值。Sun销售了大量基于AMD Opteron和Intel Xeon处理器的自产x64工作站和服务器，而x86系统由Dell、Hewlett-Packard和IBM制造。在2009年时，以下销售商的x86服务器系统支持Solaris：

Dell:将在它的主干和分支服务器上测试、认证、优化Solaris 和 OpenSolaris，并将这些服务器作为他们的软件菜单的几大选择之一

IBM：在基于x86的 IBM System x 服务器和BladeCenter服务器上发布Solaris及其收费版本

Hewlett-Packard：在Proliant服务器和分支系统上发布并提供对Solaris的软件技术支持

2010年7月，Dell和HP在他们各自的x86平台上认证并转售Oracle Solaris、Oracle Enterprise Linux 和Oracle VM，而IBM停止了对Solaris x64平台工具集的指导支持。



其他平台

Solaris 2.5.1提供了对PowerPC平台的支持，但在Solaris 2.6发布之前该接口又被取消了。2006年1月，在Blastware的一个开发者社区开始着手PowerPC接口的工作，并命名为Polaris。2006年10月，在Blastware的努力诞生的一个OpenSolaris社区计划和Sun公司实验室计划Pulsar，重新整合了Solaris中的重要部分到OpenSolaris中，宣布了他们的第一份官方源码发布。

支持Intel Itannium架构的Solaris部分在1997年就曾声明过，在从未在市场上流通。

2007年11月28日，IBM、Sun和Sine Nomine Associates展示了一份演示，这份演示是有关于在一台IBM System z 主机下的z/VM运行针对System z的OpenSolaris，称之为Sirius。2008年10月17日，一个Sirius原型版本开发成功，并于同年11月19日，IBM授权在System z IFL处理器上使用Sirius。

Solaris同样支持Linux平台ABI，ABI允许Solaris在x86系统上允许本地Linux二进制版本。基于2007年10月8日在Solaris上引入的品牌区功能，这个特征被称为Solaris提供给Linux应用的容器，或者简称为SCLA。





安装和使用指引

Solaris能够用各种打包好的软件包安装，从一个最小的缺乏网络支持版本到完整的OEM版本。不需要安装Solaris为个人使用的系统。附加软件，比如Apache、MySQL等能够用从sunfreeware、OpenCSW、Blastware下载的包来安装。

安装使用

Solaris能够在一个桌面版或服务器版上使用物理媒介或者网络进行安装。

Solaris能够在无图形界面和鼠标的文本控制台环境下进行交互式安装。这种方式适用于一个远程数据中心的服务器安装，无缝契合，来自一台终端服务器或甚至拨号调制解调器。

Solaris也能够在图形界面环境下安装。这种方式适用于个人工作站或笔记本，在一个控制台经常被使用的的本地区域。

Solaris也能够通过网络自动安装。系统管理员能够定制脚本和配置文件，包括第三方软件的自动安装和配置，无需购买其他附加软件管理工具。

当Solaris安装完成，操作系统就变成了你所安装的系统。应用可以在本地系统逐个安装，也可以通过网络上的远程系统安装。



免安装使用

Solaris能够在桌面或服务器环境上进行免安装使用。

Solaris能够由一台远程服务器提供一份无磁盘环境的操作系统拷贝来加载，或者由一个只用于交换空间的内部磁盘环境。在这种配置情况下，操作系统依旧在本地运行。应用软件在运行的时候既可存储于本地，也可不存储于本地。这种方式适用于快速安装或者经常快速更新的情况下，比如商业和教育机构。工作站只要挂载至加载区，将MAC地址注册到中央服务器上，插上电源，就能够使用了。或者当桌面环境无法提供，一个新的工作站从存储区拿出，插上电源，用户就能够从他们的上一次保存点恢复工作。

Solaris同样能够适用于轻客户端。应用程序、操作系统、窗口管理、图像查看能够运行在一台以上远程服务器。管理员可以给中央Solaris系统添加一个用户，然后一个轻客户端从存储区加载并通过桌面运行，一个用户就能够立即开始工作了。如果硬件奔溃，那么轻客户端能够被转换，用户能够从一个精确的时间点恢复工作，不论他们的工作是否被保存了。



桌面环境

Solaris的早起发布版本以OpenWindows作为桌面环境标准。从Solaris 2.0到2.2，OpenWindows支持NeWS和X应用，并且为Sun公司早期桌面环境上的SunView应用提供兼容支持。NeWS支持使用PostScript通过面向对象方式编写的应用。PostScript是在1982年发布的一种常见打印语言。X窗口系统最初来自于1984年MIT的Athena计划，用于支持一个仍在运行但被网络分割而断开的应用的显示。Sun公司的原始绑定SunView应用套件被迁移到X系统上。

后来，Sun公司推出了Solaris 2.3，不再支持附带OpenWindows3.3的遗留SunView应用和NeWS，转为附带着Display PostScript支持X11R5。图形的外观和感觉依然基于OPEN LOOK。OpenWindows 3.6.2是在Solaris 8下发布的最后一个版本。OPEN LOOK窗口管理和其他相关应用在Solaris 9都被去掉了，但是支持库仍然绑定着，用于长期提供二进制与现有应用程序的兼容。用户仍然能够从sunfreeware上下载适用于Solaris的OPEN LOOK虚拟窗口管理，而且最近发布的Solaris 10上使用。

Sun公司与其他Unix系统提供商为标准化Unix桌面而创造了一个行业条约。作为COSE(共同开放软件环境倡议)的一名成员，Sun公司推动了对于共同桌面环境的重新开放。CDE是一个关于创建一个标准Unix桌面环境的倡议。各个服务商提供不用的组件，Hewlett-Packard提供window manager，IBM提供file manage，Sun公司提供email和日历功能及其拖拉功能。这个新的桌面环境主要基于Motif的外观的感觉，而之前的OPEN LOOK桌面环境就被遗留了。CDE标准化了诸多开源系统服务商的Unix桌面环境。CDE在Solaris 2.4和Solaris 2.5中还只是可用的非绑定插件，而从Solaris 2.6到Solaris 10就被包括其中。在OpenSolaris和Solaris 11中，CDE不再被包括，但是许多库仍保留了对二进制的兼容。

2001年，Sun公司为Solaris 8发布了开源桌面环境GNOME1.4的预发布版。GNOME1.4是基于GTK+工具集的。Solaris 9引入GNOME2.0作为CDE的可替代者。Solaris 10引入了Sun公司的Java桌面系统，该系统基于GNOME并引入了一大堆应用软件，包括StarOffice，Sun公司的官方套装。Sun公司宣布JDS成为Solaris 10的重要组件。

在当前Solaris，开源桌面环境KDE、Xfce以及很多其他桌面管理器能够编译并运行于之上。

Sun曾经从2003年开始在一个称为Looking Glass计划的新桌面环境上投入，但在2006年年末，这个计划被搁浅了。





许可证

附带一些异常的Solaris源码在CDDL许可证下发布于OpenSolaris计划。CDDL是一个OSI批准许可证。该许可证是受Free Software Foundation认可的，但却与GPL不兼容。

OpenSolaris生成于2005年6月14日当时的Solaris开发代码库。二进制版本和源代码可以通过许可证免费下载。新功能如对Xon的支持的源码现在也被加入到OpenSolaris计划也是情理之中，而且Sun公司称从今以后Solaris的发布版将完全从OpenSolaris计划提取。





开发版本

从1980年代末期，Solaris基础代码库就一直在持续开发，并最终发布了Solaris 2.0版本。每一个版本，比如Solaris 10，都是基于这份开发代码库的该版本开发时段内的快照，并由此而衍生。这个项目每年更新并交付数次，知道下一个官方版本的发布。

2005年，由Sun公司开发的Solaris版本自从Solaris 10开始编号为Nevada，并且来源于现称为OpenSolaris的代码库。

2003年，一个新添加的Solaris 开发预处理程序被初始化。在Software Express for Solaris计划下，一个基于当时开发基础的二进制版本在数月内可以下载，允许任何人尝试新功能并同时测试系统的质量和稳定性，以助于下一个官方版本的发布。这个计划后来改为每季度发布一个版本模型，并重命名为Solaris Express Developer Edition。

2007年，Sun公司宣布了Indiana计划及其目的，包括了提供一份OpenSolaris的开源二进制版本，代替SXDE。这个版本的第一个发布版是OpenSolaris 2008.05。

Solaris Express Developer Edition是专为开发者而设定。它每两周更新一次，直到2010年1月终止，用户被建议移植到OpenSolaris发布版上。虽然下载许可证规定用户是受限的个人或教育评估目的，但当用户实际上安装在生成和商业活动时，这意味着用户接受许可证的内容。

SXCE发布至130次终止，数周后OpenSolaris发布至134次终止。在134发布后的OpenSolaris的下一次发布在2010年3月，但该版本并未完全发布，虽然安装包库提供安装包。作为代替，Oracle将二进制版本重命名为Solaris 11 Express，并修改了许可证内容，于2010年11月发布了基于151a的2010.11。
