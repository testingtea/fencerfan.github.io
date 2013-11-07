---
author: lusl
comments: true
date: 2013-08-21 01:09:23+00:00
layout: post
slug: python%e5%a4%9a%e7%89%88%e6%9c%ac%e7%ae%a1%e7%90%86-pythonbrew
title: Python多版本管理-pythonbrew
wordpress_id: 377
---

## 一、安装Pythonbrew


**安装前确保系统有以下包，在Ubuntu11.10中测试通过，其他系统可能依赖的包会有所不同**(参考：[https://github.com/utahta/pythonbrew/issues/81](https://github.com/utahta/pythonbrew/issues/81))




    
    $ sudo apt-get install curl build-essential libbz2-dev libsqlite3-dev zlib1g-dev libxml2-dev libxslt1-dev libreadline5 libgdbm-dev libgdb-dev libxml2 libssl-dev tk-dev libgdbm-dev libexpat1-dev libncursesw5-dev







1、使用easy_install工具安装，用命令：which easy_install查看是否安装该工具；没有输出则没安装，需要先安装easy_install




    
    $ sudo easy_install pythonbrew





2、或者使用[官网](https://pypi.python.org/pypi/pythonbrew/)推荐的方法安装：




    
    curl -kL http://xrl.us/pythonbrewinstall | bash





以上命令把Pythonbrew自动安装在~/.pythonbrew目录下；




## 二、Pythonbrew配置


运行：




    
    $ pythonbrew_install





会提示把下面内容添加到~/.bashrc文件中（Please add the following line to the end of your ~/.bashrc）,不用运行上面的命令手动把下面内容添加到文件中就可以了；




    
    [[ -s "$HOME/.pythonbrew/etc/bashrc" ]] && source "$HOME/.pythonbrew/etc/bashrc"








## 三、使用Pythonbrew


1、查看可安装的Python版本




    
    $ pythonbrew list --know





2、安装需要的Python版本，需要安装curl工具；安装会自动完成；




    
    $ pythonbrew install 2.7.5





3、查看已经安装的Python版本，后面有*号表示正在使用的版本




    
    $ pythonbrew list





4、选择一个python版本使用，只在当前终端有效




    
    $ pythonbrew use 2.7.5





5、选择python2.7.5版本作为系统默认版本使用，会把该版本的路径添加到PATH中




    
    $ pythonbrew switch 2.7.5





6、取消pythonbrew选择的版本




    
    $ pythonbrew off





7、清理安装后的版本的源码和安装包




    
    $ pythonbrew cleanup





8、指定Python版本运行文件




    
    $ pythonbrew py -p 2.7.5 test.py





9、删除制定Python版本




    
    $ pythonbrew uninstall 2.7.5








## 四、使用virtualenv的功能，创建虚拟环境




**确保系统中安装有zlib包，否则创建过程中会报错：**

**Traceback (most recent call last): File “/home/username/.pythonbrew/etc/virtualenv/virtualenv.py”, line 19, in <module> import zlib ImportError: No module named zlib**

在Ubuntu11.10 64bit系统，使用以下命令安装




    
    $ sudo apt-get install zlib1g-dev







1、首先选择一个python版本




    
    $ pythonbrew switch 2.7.5





2、创建虚拟环境




    
    $ pythonbrew venv create test_env





3、启用虚拟环境，启用后会显示：`(test_env)alexzhou@alexzhou:~``/python_workspace``$`




    
    $ pythonbrew venv use test_env





4、退出虚拟环境




    
    $ deactivate





5、虚拟环境列表




    
    $ pythonbrew venv list





6、在虚拟环境中使用pip工具安装Python工具，为了避免使用到系统环境的pip工具，也就是说只能在虚拟环境中使用，在~/.bashrc文件末尾加入以下内容




    
    export PIP_REQUIRE_VIRTUALENV=true





或者也可以用下面的设定，让系統的 `pip` 自动使用启动中的虚拟环境。




    
    export PIP_RESPECT_VIRTUALENV=true



