---
author: liangzhongxing
comments: true
date: 2013-03-29 08:04:49+00:00
layout: post
slug: vboxmanage%e5%91%bd%e4%bb%a4%e8%af%a6%e8%a7%a3
title: VBoxManage命令详解
wordpress_id: 214
categories:
- 虚拟机
tags:
- VBoxManage
---

VBoxManage [-v|-version] 显示virtualbox的版本号
VBoxManage -nologo 隐藏logo
VBoxManage -convertSettings 允许自动转换设置文件
VBoxManage -convertSettingsBackup 允许自动转换设置文件，并在转换前作备份
VBoxManage -convertSettingsIgnore 允许自动转换设置文件，但是不保存结果

VBoxManage list vms|runningvms 显示列表虚拟机|正在运行的虚拟机
|ostypes|hostdvds virtualbox支持的系统类型|宿主机的光盘驱动器
|hostfloppies 宿主机的软盘驱动器
|hostifs|hostinfo 宿主机的网络接口|宿主机的信息
|hdds|dvds 已注册的虚拟硬盘|已注册的虚拟光盘
|floppies|usbhost 已注册的虚拟软盘|宿主机的USB设备
|usbfilters USB筛选器
|systemproperties 虚拟机的基本信息

VBoxManage showvminfo |显示指定虚拟机的信息
[-details] 显示详细信息
[-statistics] 显示统计信息
[-machinereadable] 以清晰的格式显示虚拟机信息

VBoxManage registervm将指定文件所在的虚拟机添加到列表

VBoxManage unregistervm |从虚拟机列表清除指定的虚拟机
[-delete] 从虚拟机列表删除指定的虚拟机

VBoxManage createvm -name 创建指定名称的虚拟机
[-register] 将创建的虚拟机添加到列表
[-basefolder 指定虚拟机的基础目录
[-settingsfile ] 指定虚拟机配置文件的基础目录
[-uuid] 创建指定uuid的虚拟机

VBoxManage modifyvm 编辑指定的虚拟机的配置
[-name ] 修改虚拟机的名称
[-ostype ]修改虚拟机的操作系统类型
[-memory ] 修改虚拟机的内存大小
[-vram ] 修改虚拟机的显存大小
[-acpi on|off] 启动或禁止acpi电源管理接口
[-ioapic on|off] 启动或禁止I/O APIC电源管理接口
[-pae on|off] 启动或禁止CPU的PAE支持，PAE是
Physical Address Extension : 物理地址扩展
[-hwvirtex on|off|default]启动或禁止CPU的硬件虚拟化支持
[-nestedpaging on|off] 开启或关闭CPU的嵌套页面列表支持
[-monitorcount ] 设置显示器数目，VRDP多用户模式时 [-bioslogofadein on|off] 开启或关闭bioslogo渐显效果
[-bioslogofadeout on|off] 开启或关闭bioslogo渐隐效果
[-bioslogodisplaytime ]设置bioslogo显示时间（以毫秒为单位)
[-bioslogoimagepath ]设置bioslogo图像路径，用于自定义bioslogo
[-biosbootmenu disabled| 设置是否显示bios启动菜单 关闭
menuonly| 只菜单
messageandmenu] 信息和菜单
[-biossystemtimeoffset ] 设置bios系统时间补偿（以毫秒为单位）
[-biospxedebug on|off] 打开或关闭biospxe调试
[-boot none|floppy|dvd|disk|net>] 设置启动顺序
[-hd none||] 为虚拟机添加三个IDE设备之一（第2个主盘被vm保留作为光驱，不能占用）在三个IDE中，你可以指定（硬盘）的vdi文件名或者它的UUID
[-idecontroller PIIX3|PIIX4] 设置IDE控制器的类型
[-sata on|off] 开启或关闭SATA硬盘控制器
[-sataportcount ] 设置虚拟机最多支持的SATA控制器数目
[-sataport none| 没有硬盘连接到SATA控制器
| 指定uuid的硬盘连接到SATA控制器
] 指定文件名的硬盘连接到SATA控制器
[-sataideemulation ] 指定一个SATA设备工作在IDE兼容模式，IDE设备编号是1-4，SATA设备编号是1-30
[-dvd none| 不连接DVD光驱
| 指定UUID的DVD光驱连接
| 将指定的光盘映像文件挂接到DVD光驱
host:] 将宿主机的DVD光驱挂接到虚拟机的DVD光驱
[-dvdpassthrough on|off]打开|关闭虚拟机里光盘的刻录功能
[-floppy disabled| 不连接软驱
empty| 连接软驱但不插入软盘
| 指定UUID的软驱连接
| 将指定的软盘映像文件挂接到软驱驱
host:] 将宿主机的软驱驱挂接到虚拟机的软驱
[-nic none| 虚拟机不添加网卡
null| 虚拟机有网卡但不连接
nat| 网络连接使用NAT模式
hostif| 网络连接使用桥接模式
intnet] 网络连接使用内部网络模式
[-nictype Am79C970A| 虚拟机连接AMD PCNet PCI II网卡
Am79C973| 虚拟机连接AMD PCNet FAST III网卡（默认）
82540EM| 虚拟机连接Intel PRO/1000 MT Desktop网卡
82543GC] 虚拟机连接Intel PRO/1000 T Server网卡
[-cableconnected on|off]插入或拔出网线
[-nictrace on|off] 开启或关闭网络追踪
[-nictracefile ] 将网络流量追踪数据保存到文件
[-nicspeed ] 设置网络连接的速度
[-hostifdev none| 不连接到主机网络接口
] 桥接模式下连接到指定的主机接口
[-intnet ] 内网模式下为虚拟机指定内部网络名称
[-natnet | 配置NAT网络接口的地址
default] 默认NAT网络接口的地址是10.0.x.0/24
[-macaddress auto| 自动生成虚拟网卡的MAC地址
] 指定虚拟网卡的MAC地址
[-uart off| 不启用虚拟串口
_ ]启用虚拟串口，并设置虚拟串口的I/O参数和IRQ参数
[-uartmode disconnected| 启用虚拟串口，但不连接到宿主机的串口
server | 在宿主机创建PIPE通道，并将虚拟机串口连接到这个通道
client | 不创建PIPE通道，而是将虚拟机串口连接到已存在的通道
] 将虚拟机串口连接到宿主机的串口
[-gueststatisticsinterval ] 配置虚拟机静态时间间隔
[-audio none| 虚拟机不连接声卡
null| 将虚拟机的声卡连接到空的声音设备
dsound] 将虚拟机的声卡连接到宿主机的声卡
[-audiocontroller ac97| 将虚拟机声卡虚拟为ICH AC97声卡
sb16] 将虚拟机声卡虚拟为soundblaster 16声卡
[-clipboard disabled| 不共享剪贴板
hosttoguest| 将宿主机的剪贴板共享给虚拟机
guesttohost| 将虚拟机的剪贴板共享给宿主机
bidirectional] 宿主机和虚拟机共使用一个剪贴板
[-vrdp on|off] 开启|关闭virtualbox内置的VRDP服务器
[-vrdpport default| 使用默认的vrdp端口3389_

] 指定vrdp端口
[-vrdpaddress ] 指定VRDP主机地址
[-vrdpauthtype null| 不用授权，任何客户机都可以连接到VRDP服务器
external| 只有宿主机的用户才可以连接到VRDP服务器
guest] 只有虚拟机的用户才可以连接到VRDP服务器
[-vrdpmulticon on|off] 打开|关闭VRDP多用户连接模式
[-vrdpreusecon on|off] 打开|关闭VRDP断线重连
[-usb on|off] 打开|关闭虚拟USB控制器
[-usbehci on|off] 打开|关闭虚拟USB2.0控制器
[-snapshotfolder default| 将系统快照保存到默认文件夹] 将系统快照保存到指定文件夹

VBoxManage startvm |开启指定UUID|名称的虚拟机
[-type gui|vrdp] 设置虚拟机标准显示设备GUI界面|VRDP

VBoxManage controlvm |改变正在运行的虚拟机的状态
pause| 暂停，这时虚拟机窗口显示灰色
resume| 恢复暂停的虚拟机
reset| 复位
poweroff| 强行关闭
acpipowerbutton| 关机
acpisleepbutton| 使虚拟机处于睡眠状态
savestate| 保存状态然后关闭，相当于休眠
keyboardputscancode [ ...] 键盘扫描码设置
setlinkstate on|off 连接|断开网络连接
usbattach |

连接到指定UUDI|地址的USB设备
usbdetach |断开指定UUDI|地址的USB设备
dvdattach none| 不连接虚拟DVD光驱
| 连接到指定UUID的DVD光驱
| 连接到指定名称的DVD映像文件
host: 连接到宿主机的DVD光驱
floppyattach none| 不连接虚拟软驱
| 连接到指定UUID的虚拟软驱
| 连接到指定名称的软盘映像文件
host: 连接到宿主机的软驱setvideomodehint 设置虚拟机的屏幕分辨率 水平像素
垂直像素
颜色深度
[display] 刷新频率
setcredentials 指定VRDP自动连接参数 用户名

密码
域
[-allowlocallogon] 允许|禁止本地登陆

VBoxManage discardstate|丢弃指定UUID|名称的虚拟机的保存状态

VBoxManage adoptstate|将虚拟机从指定的保存状态中恢复

VBoxManage snapshot |为指定的虚拟机拍快照
take 为快照取名
[-desc ]| 给快照添加描述
discard | | 丢弃指定的快照
discardcurrent -state| 恢复到最近的快照
-all | 恢复到倒数第二个快照
edit || 编辑指定的快照
-current 编辑当前快照
[-newname ] 修改快照名称
[-newdesc ] 修改快照描述
showvminfo| 显示快照的虚拟机信息

VBoxManage registerimage disk|dvd|floppy 注册硬盘、光盘、软盘映像文件
[-type normal| 注册为普通类型（可创建快照，可读写）
immutable| 注册为只读类型（相当于加了硬盘卡）
writethrough] 注册为可写类型（这种类型不能创建快照）
(disk only) (注册类型选项只适用于硬盘）

VBoxManage unregisterimage disk| 从虚拟介质管理器删除指定的硬盘
dvd| 从虚拟介质管理器删除指定的DVD光盘
floppy 从虚拟介质管理器删除指定的软盘
| 删除时指定UUID
删除时指定映像文件

VBoxManage showvdiinfo|显示指定UUID|名称虚拟硬盘的信息

VBoxManage createvdi -filename 创建指定名称的虚拟硬盘
-size 指定虚拟硬盘的大小（以兆为单位）
[-static] 创建固定大小的虚拟硬盘
[-comment ] 添加一段解释性文字
[-register] 注册新创建的虚拟硬盘
[-type normal| 注册类型 普通（可以创建快照）
writethrough] 注册类型 可写（不能创建快照）
(default: normal) 默认是普通类型
VBoxManage modifyvdi| compact 压缩指定的虚拟硬盘

VBoxManage clonevdi|克隆指定的VDI虚拟硬盘

VBoxManage convertdd [-static] 将raw硬盘转换成vdi虚拟硬盘
VBoxManage convertdd [-static] stdin 将标准输入参数指定的设备转换成vdi虚拟硬盘，比如：dd if=/dev/sda1 | VBoxManage convertdd stdin /media/disk/C.vdi
