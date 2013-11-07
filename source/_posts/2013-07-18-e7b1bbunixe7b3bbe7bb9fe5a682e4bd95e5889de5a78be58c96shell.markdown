---
author: lusl
comments: true
date: 2013-07-18 02:36:29+00:00
layout: post
slug: '%e7%b1%bbunix%e7%b3%bb%e7%bb%9f%e5%a6%82%e4%bd%95%e5%88%9d%e5%a7%8b%e5%8c%96shell'
title: 类unix系统如何初始化shell
wordpress_id: 337
---

## Shell的配置文件


当我们在linux中打开一个shell的时候，系统会读取相关的配置文件来初始化shell(其他unix-like OS也一样)。配置文件包括以下这些：


### 1. 全局配置(对所有用户都有效)






    
    /etc/profile
    /etc/bash.bashrc







### 2. 当前用户配置(仅对当前登录用户有效)






    
    ~/.bashrc
    ~/.bash_profile
    ~/.bash_login
    ~/.profile








## Shell的分类


shell分为login shell和non-login shell两种


### 1.Login Shell


[借用《鸟哥的linux私房菜》中的定义](http://www.thegeekstuff.com/2008/10/execution-sequence-for-bash_profile-bashrc-bash_login-profile-and-bash_logout/)：取得 bash 時需要完整的登入流程的，就稱為 login shell。舉例來說，你要由 tty1 ~ tty6 登入，需要輸入使用者的帳號與密碼，此時取得的 bash 就稱為『 login shell 』囉；

除过上面获取login shell的方式外，我们还可以通过在non-login shell中运行




    
    bash --login





来得到一个login shell。login shell启动时的配置文件读取流程如下：
借用另一博客 [‘Execution sequence for .bash_profile, .bashrc, .bash_login, .profile and .bash_logout’](http://www.gnu.org/software/bash/manual/bash.html#Bash-Startup-Files) 中的伪代码示例：





![复制代码](http://common.cnblogs.com/images/copycode.gif)



    
    execute /etc/profile
    IF ~/.bash_profile exists THEN
        execute ~/.bash_profile
    ELSE
        IF ~/.bash_login exist THEN
            execute ~/.bash_login
        ELSE
            IF ~/.profile exist THEN
                execute ~/.profile
            END IF
        END IF
    END IF




![复制代码](http://common.cnblogs.com/images/copycode.gif)





当我们退出或者注销login shell时，也有需要执行如下流程：




    
    IF ~/.bash_logout exists THEN
        execute ~/.bash_logout
    END IF







### 2.Non-Login Shell


继续借用《鸟哥的linux私房菜》中的定义：取得 bash 介面的方法不需要重複登入的舉動，舉例來說，(1)你以 X window 登入 Linux 後， 再以 X 的圖形化介面啟動終端機，此時那個終端介面並沒有需要再次的輸入帳號與密碼，那個 bash 的環境就稱為 non-login shell了。(2)你在原本的 bash 環境下再次下達 bash 這個指令，同樣的也沒有輸入帳號密碼， 那第二個 bash (子程序) 也是 non-login shell 。

譬如在Ubuntu中，我们启动的Gnome Terminal，在默认情况下就是一个non-login shell。non-login shell启动时的配置文件读取流程：




    
    execute /etc/bash.bashrc
    IF ~/.bashrc exists THEN
        execute ~/.bashrc
    END IF



