---
layout: post
title: Linux第一堂课
date: 2017-07-27
categories: blog
tags: [Linux]
description: 搭好博客后的第一篇文章。

---

<center>
<font size="7" ><b>Linux系统基础使用入门</b></font>
</center>

### 一、终端：用户与主机交互，必然用到的设备。
- 物理终端：直接接入本机的显示器和键盘设备：console
- 虚拟终端：附加在物理终端之上的，以软件方式虚拟实现的终端，Ubuntu默认启动6个虚拟终端（control+alt+F1~F6)。
- 图形终端：图形界面的终端（control+alt+F7）
- 模拟终端：**纯粹软件实现**，不会附加在物理终端上，一般附加在图形终端上。如图形界面下打开的命令行接口。以及基于ssh协议或telnet协议等远程打开的界面。  

&emsp;&emsp;&ensp;**注意：一旦开机程序启动完成，就默认启动虚拟终端；只有在刚开机还未完成的时候，物理终端才起作用。**       

- 查看当前的终端设备：tty命令。              
其中:            物理终端设备即为console；            
&emsp;&emsp;&emsp;虚拟终端设备文件路径为：/dev/tty#；         
&emsp;&emsp;&emsp;模拟终端设备文件路径为：/dev/pts/# [0,oo]。        

### 二、交互式程序：终端本身没法交互，需要交互式程序。启动终端后，在终端设备附加的一个交互式应用程序。
- GUI:             
&emsp;&emsp;&emsp;X protcol(x协议）, window manager(窗口管理器), desktop(桌面系统)。                          
&emsp;&emsp;&emsp;Desktop:                     
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;GNOME (C, gtk)             
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;KDE   (C++, qt)              
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;XFCE  (轻量级桌面)             
- CLI:             
&emsp;&emsp;&emsp;shell程序：sh (bourn),csh,tcsh,ksh (korn),bash (bourn again shell),zsh              
&emsp;&emsp;&emsp;显示当前使用的shell：＃ ehco $SHELL                
&emsp;&emsp;&emsp;显示当前系统使用的所有shell：# cat /etc/shells                    
&emsp;&emsp;&emsp;命令提示符:[root@localhost ~]#                  

### 三、命令：
- 本质：提请shell程序找到键入命令所对应的可执行程序或代码，并由其分析后提交给内核分配资源将其运行起来；表现为一个或者多个进程。
- 分类：               
&emsp;&emsp;&emsp;内建命令：由shell程序自带的通过某命令形式提供；(COMMAND is a shell builtin)               
&emsp;&emsp;&emsp;外部命令：在当前某文件系统路径下有对应的可执行程序文件。(COMMAND is hashed)                
- 区别内部或外部命令：# type COMMAND                   
- 运行命令：         
&emsp;&emsp;&emsp;&emsp;命令格式：COMMAND [OPTIONS...] [AGRGUMENTS...]            
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&ensp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;|&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;｜                        
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&ensp;&emsp;&emsp;&emsp;&emsp;&emsp;选项&emsp;&emsp;&emsp;&emsp;&ensp;参数          
&emsp;&emsp;&emsp;&emsp;选项：用于启用或关闭命令的某个或某些功能。            
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&ensp;－短选项：－c，例如：－l，－h。多个短选项可合并，例如－lh。不合并则空白隔开。        
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&ensp;－长选项：－－word，例如：－－long，－－human－readable。一般不合并。        
&emsp;&emsp;&emsp;&emsp;参数：命令的作用对象。向命令提供数据。多个参数间也须用空白隔开。

### 四、文件系统：
- 例如  /etc/sysconfig/network-scripts/ifcfg-eth0
- 文件数据：             
&emsp;&emsp;&emsp;&emsp;&emsp;元数据：metadata(索引中的数据)            
&emsp;&emsp;&emsp;&emsp;&emsp;数据：data            
- 文件名：           
&emsp;&emsp;&emsp;&emsp;1. 严格区分字符大小写；          
&emsp;&emsp;&emsp;&emsp;2. 可使用除&ensp;**/**&ensp;外的任意字符，但不推荐使用特殊字符；          
&emsp;&emsp;&emsp;&emsp;3. **/:**&ensp;为根目录，**/**&ensp;为路径分隔符；          
&emsp;&emsp;&emsp;&emsp;4. 名字长度不能超过255个字符；                   
&emsp;&emsp;&emsp;&emsp;5. 所有以&ensp;**.**&ensp;开头的文件均为隐藏文件。
- 路径：            
&emsp;&emsp;&emsp;绝对路径：从根目录起始的路径；            
&emsp;&emsp;&emsp;相对路径：从当前位置起始的路径；            
&emsp;&emsp;&emsp;当前目录：current directory，也称作working directory(显示当前目录用命令pwd)；     
&emsp;&emsp;&emsp;当前位置表示方式：**./:**+路径或者直接输入路径               

&emsp;&emsp;&emsp;**注意：&ensp;..&ensp;表示当前目录的上一级目录**        

- LSB:Linux Standard Base 


#### 本节命令总结：ls,cd,type,tty,echo,whereis,which,cat,pwd.

