---
author: jane
comments: true
date: 2013-03-14 10:57:59+00:00
layout: post
slug: '%e5%ae%89%e8%a3%85sql2000%e5%87%ba%e7%8e%b0command-line-option-syntax-errortype-command-for-help%e8%a7%a3%e5%86%b3%e5%8a%9e%e6%b3%95'
title: 安装SQL2000出现command line option syntax error!type command /? for help解决办法
wordpress_id: 195
---

原文来自于：[http://hi.baidu.com/ncicnkzonpkmqvr/item/599526fe284cec18e2e3bd1b](http://hi.baidu.com/ncicnkzonpkmqvr/item/599526fe284cec18e2e3bd1b)

command line option syntax error!type command /? for help

当安装程序安装到：
安装程序正在安装ms数据访问组件
时，屏幕出现错误提示：
command line option syntax error,type command/? for help

然后点确定继续，结果到：
安装程序正在安装HTML帮助
时，屏幕又出现标题为html help 1.32 update错误警对话框提示：
command line option syntax error,type command/? for help

然后我再点确定继续，安装程序开始复制文件，复制完文件后又出现错误提示：
无法找到动态连接库sqlunirl.dll（sqlunirl.dll是MDAC的一个组件），于指定路径
点确定后安装程序停止运行，让查看安装日志



解决方法:
引起这问题的原因是,SQLServer的安装文件,放在中文目录下.

将SQLServer的安装文件,拷到英文目录,安装就OK

比如将:

D:\软件\Sqlserver

中的"软件"去掉.

注:

MDAC （Microsoft Data Access Components）是微软数据库访问组件，Netpise和许多利用数据库的软件都需要操作系统安装MDAC。很多用户的操作系统中已经存在了MDAC，有些是操作系统内置的、有些是其它应用程序安装的。

补充方法(未测试)

1.重装MDAC
2.修改注册表:
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion\setup
删除ExceptionComponents
重启,安装.
很多时候不需要 第一步 操作。

二

电脑安装SQL出现错误： command line option syntax error!type command /? for help

都说是安装目录是中文引起的，可是我检查了好几遍我的安装目录的确是英文的

一、情况说明

SQL Server 2000以前的版本，例如7.0一般不存在多个版本，只有标准版跟桌面版，用户如果不清楚该装什么版本的话，可按安装上的

安装先决条件指示安装，一般在WIN2000 服务器版上装标准版，其他的系统装桌面版的就可以；而SQL Server 2000安装问题就比较大，时常

见到的问题如下：

1、配置服务器时中断.

2、注册 ActiveX 时中断.

3、显示到100%的时候中断.

4、提示：command line option syntax error, type command /? for help，继续安装,最后在配置服务器的时候出现：无法找到动态链接

SQLUNIRL.DLL于指定的路径……

5、以前进行的程序创建了挂起的文件操作，运行安装程序前，必须重新启动

二、情况1，2，3的解决办法：

提醒：为避免误操作，先备份注册表和数据库进不了SQL Server 2000，可以备份C:Program Files\Microsoft SQL Server\Mssql\Data

(默认路径)文件夹的文件.

1)、先把SQL Server卸载(卸载不掉也没有关系，继续下面的操作)；

2)、把Microsoft SQL Server文件夹整个删掉；

3)、运行注册表,删除如下项：

HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server

HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MssqlServer

HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\MssqlSERVER

HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\SQLSERVERAGENT

HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\MssqlSERVERADHELPER

HKEY_CURRENT_USER\Software\Microsoft\Microsoft SQL Server

4)、需要的话就重新启动系统；

5)、重新安装。

另外也可尝试单步运行安装 SQL Server 2000的方法：

1)、放入 SQL Server 2000 光盘.

2)、在"开始"--"运行"键入 "F:\x86\setup.exe k=dbg" (F是光盘)

注意：

1)、不同的操作系统支持的SQL Server 2000版本(参见：SQL Server 2000 各版本的区别简介及版本情况查询一文)。

Windows 2000 Server可以安装SQL Server 2000的任何版本.

Windows 2000 Professional只能安装SQL Server 2000的个人版、开发版、评估版、MCDE

2)、SQL Server 2000各版本以及对软硬件的要求(参见：SQL Server 2000 的硬件和软件安装要求一文)。

三、情况4的解决办法

因为安装文件的路径(完整路径)里有中文.

比如 c:\SQLSERVER中文企业版\

改成 c:\SQLSERVER\

四、情况5的解决办法

1)、重启机器，再进行安装，如果发现还有该错误，请按下面步骤；

2)、在开始--运行中输入regedIT；

3)、到HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Session Manager位置找到

PendingFileRenameOperations项目，并删除它。这样就可以清除安装暂挂项目。

4)、选择文件--倒出,保存；

5)、在右边窗口右击PendingFileRenameOperations，选择删除，然后确认；

6)、重启安装，问题解决

五、如果问题依旧，试试先修复操作系统：

命令提示符下执行: sfc /scannow 。

最后的方法：换 Windows 2000 安装盘和 SQL Server 2000 安装盘，有时候问题的原因很奇怪，有人曾更换了一个电源就解决了问题。

1)、先卸载您的 SQL Server 2000,必要的时候删除 Program Files\Microsoft SQL Server 文件夹；

2)、打开注册表；

在"开始"--"运行"键入"regedIT"

3)、按下列顺序点击打开；

+ HKEY_LOCAL_MACHINE

+ SOFTWART

+ Microsoft

+ Windows

+ CurrentVersion

+ Setup

+ ExceptionComponents

4)、将 ExceptionComponents 下面的文件夹全部删除；

如 {60BFF50D-FB2C-4498-A577-C9548C390BB9}

{60BFF50D-FB2C-4498-A577-C9548C390BB9}

{60BFF50D-FB2C-4498-A577-C9548C390BB9}

{60BFF50D-FB2C-4498-A577-C9548C390BB9}

5)、重新启动；

6)、重新安装 SQL Server 2000 。

六、其他说明

1)、Windows目录中的SQLstp.log文件，该文件列出了安装程序所执行的操作的详细信息，并包含安装期间遇到的所有错误。

通过检查该文件，可以详细了解安装在什么地方失败、为什么失败。

2)、SQL安装的时的错误信息保存在一个叫Errorlog的日志文件中，默认情况下该文件位于Program Files\Microsoft SQL Server\Mssql\Log

目录中。该错误日志包含安装程序试图启动SQL-Server时SQL-Server所遇到的错误，这些信息可以帮助您深入检查错误原因。

3)、需要检查的另一个组件是Microsoft数据访问组件(MDAC)安装程序，它作为SQL-Server2000安装程序的一部分启动。

SQL-Server2000安装程序会安装MDAC2.6。MDAC安装程序会创建名为DASEtup.log的单独的日志文件；您可以查看此日志文件并确保MDAC

安装程序没有出现问题。
SQL或msde安装问题－Command line option syntax error. Typ
SQL 2000安装问题－－Command line option syntax error

当安装程序安装到：

安装程序正在安装ms数据访问组件

时，屏幕出现错误提示：

---------------------------

SQL Redist

---------------------------

Command line option syntax error. Type Command /? for Help.

---------------------------

确定

---------------------------

然后点确定继续，安装程序开始复制文件，复制完文件后又出现错误提示：

无法找到动态连接库sqlunirl.dll于指定路径“…\sqlunirl.dll”（超级长的路径！）

点确定后安装程序停止运行，查看安装日志。

解决方法:

引起这问题的原因是,SQLServer的安装文件被放在了中文目录下.

将SQLServer的安装文件,拷到英文目录,安装就OK

比如将:

“D:\Sqlserver安装盘”中的"安装盘"去掉。就行了！

什么？还是不行？！别急，嘿嘿。

看看您的用户名是不是中文的，改成英文的吧。这个用户名指的就是您登录windows的时候使用的用户名，系统默认的是administrator。

您不舍的修改这个用户名？那就重新创建一个英文的用户吧，用这个用户登录然后安装就行了。

再多嘴说一说原因吧：

软件在安装的时候会先解压，生成一些临时文件，系统调用这些文件进行安装。有时候这些文件放在当前的目录下，有时候放在“C:\Documents and Settings\用户名\Local Settings\Temp”文件夹中，这时候如果您的“用户名”是中文的话，就可能失败了。看来还是支持中文不够好啊！无奈！
