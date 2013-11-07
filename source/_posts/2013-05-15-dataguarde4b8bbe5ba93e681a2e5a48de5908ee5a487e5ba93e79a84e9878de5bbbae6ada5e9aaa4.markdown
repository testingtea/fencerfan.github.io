---
author: wangsx
comments: true
date: 2013-05-15 10:18:15+00:00
layout: post
slug: dataguard%e4%b8%bb%e5%ba%93%e6%81%a2%e5%a4%8d%e5%90%8e%e5%a4%87%e5%ba%93%e7%9a%84%e9%87%8d%e5%bb%ba%e6%ad%a5%e9%aa%a4
title: dataguard主库恢复后备库的重建步骤
wordpress_id: 270
categories:
- 数据库
---


	
  1. 主库操作操作(open+archived_log)
$ rman target=/
RMAN>BACKUP DATABASE PLUS ARCHIVELOG;
$ sqlplus sys/dingjia as sysdba
SQL>ALTER DATABASE CREATE STANDBY CONTROLFILE AS '/tmp/orcl_stby.ctl';
将orcl_stby.ctl拷贝到备库的/tmp目录下
将主库rman备份之后的文件拷贝到备库的恢复日志目录下，如：/u01/app/oracle/flash_recovery_area/ORA10G/backupset

	
  2. 备库机器操作
$ sqlplus sys/dingjia as sysdba
SQL>shutdown immediate;
删除备库的控制文件control*
$ rman
RMAN>connect target
RMAN>restore controlfile from '/tmp/orcl_stby.ctl';
RMAN>startup force mount;
RMAN>restore database;

	
  3. 最后重启主备库，按顺序启动dataguard即可！


