---
author: wangsx
comments: true
date: 2013-07-18 08:26:00+00:00
layout: post
slug: firefoxselenium-ide
title: Firefox+Selenium IDE
wordpress_id: 341
categories:
- 自动化测试
---

安装：
刚开始在windows上安装，firefox5，selenium1.2。装完之后点击Selenium IDE buttons，总是说You don't have installed Selenium IDE!现在发现原来是selenium1.2版本不支持firefox5引起的。后来到公司，看到firefox是18.0，又在addons那里安装，l列表中显示的是selenium1.2版本的，装完还是有一样问题，最后到Selenium IDE的官网上查看，现在selenium已经更新到2点多的版本了，上面也写了那个版本新增了对firefox*的支持，最后现在目前的最新版本Selenium2.2，解决了问题！
[Selenium IDE官网下载](http://docs.seleniumhq.org/download/)

source的format问题
刚开始，以为在format clipboard那里选择source的语言，但是无论我选了什么，source显示的都是HTML语言。在options的format里看到的是 want the formats back?Click to read ....。后来打开options，将Enable experimental features勾上即可！
