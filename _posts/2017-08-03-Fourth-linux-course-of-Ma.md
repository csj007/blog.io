---
layout: post
title: Linux第四堂课
date: 2017-08-03
categories: blog
tags: [Linux]
description: 第四堂课Linux文件系统及文件类型。

---

<center>
<font size="7" ><b>Linux文件系统及文件类型</b></font>
</center>
### 一、Linux的文件系统。
- 根文件系统(rootfs)：
&emsp;&emsp;&emsp;root filesystem       

- LSB，FHS：(Filesystem Heirache Standard)   
&emsp;&emsp;&emsp;/boot：引导文件的启动目录，内核文件，引导加载器都存档于此目录中；    
&emsp;&emsp;&emsp;/bin：供所有用户使用的基本命令，不能关联至独立分区，OS启动即会用到的程序；    
&emsp;&emsp;&emsp;/sbin：管理类的基本命令，不能关联至独立分区，OS启动即会用到的程序；     
&emsp;&emsp;&emsp;/lib：基本共享库文件，以及内核模块文件(/lib/modules)；    
&emsp;&emsp;&emsp;/lib64：专用于x86_64系统上的辅助共享库文件存放位置；           
&emsp;&emsp;&emsp;/etc：配置文件目录(纯文本文件)；           
&emsp;&emsp;&emsp;/home/USERNAME：普通用户家目录；     
&emsp;&emsp;&emsp;/root：管理员的家目录；     
&emsp;&emsp;&emsp;/media：便携式移动设备挂载点：    
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;cdrom      
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;usb      
&emsp;&emsp;&emsp;/mnt：临时文件系统挂载点；     
&emsp;&emsp;&emsp;/dev：设备文件及特殊文件存放位置：      
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;b：block device(通常指可随机访问设备)      
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;c：character device(通常是线性访问设备)    
&emsp;&emsp;&emsp;/opt：第三方应用程序的安装位置；        
&emsp;&emsp;&emsp;/srv：系统上运行的服务用到的数据；     
&emsp;&emsp;&emsp;/tmp：临时文件的存放位置；      
&emsp;&emsp;&emsp;/usr：universal shared, read-only data:       
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;bin：存放完成某些基本功能的目录，保证系统拥有完整功能；          
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;lib：Libraries；       
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;sbin：Non-vital system binaries；     
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;include：Header file included by C programs；     
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;share：结构化文件存放位置，比如doc，man，背景图片等；     
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;local：取代了opt，第三方应用程序的安装位置     
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;包含bin，sbin，lib，lib64，share，etc等（完全的独立王国）       
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;var：variable data files，包含：
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;cache：应用程序缓存数据；    
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;lib：应用程序状态信息数据；   
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;local：专用于为/usr/local下的应用程序存储可变数据；      
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;lock：应用程序的锁文件；      
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;log：日志目录及文件；     
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;opt：专用于为/opt下的应用程序存储可变数据；      
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;run：运行中进程的相关数据，通常用于存储进程的pid文件；        
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;spool：应用程序缓冲池；     
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;tmp：专用于存储系统两次重启间的临时数据；   
&emsp;&emsp;&emsp;/proc：用于输出内核与进程信息相关的虚拟文件系统；      
&emsp;&emsp;&emsp;/sys：用于输出当前系统上硬件设备相关信息的虚拟文件系统；      

### 二、Linux应用程序的组成部分：
- 二进制程序：如可运行的命令       
&emsp;&emsp;&emsp;一般放在/bin，/sbin，/usr/bin，/usr/sbin，/usr/local/bin，/usr/local/sbin    
- 库文件：         
&emsp;&emsp;&emsp;一般放在/lib，/lib64，/usr/lib，/usr/lib64，/usr/local/lib，/usr/local/lib64      
- 配置文件：       
&emsp;&emsp;&emsp;一般放在/etc，/etc/DIRECTORY，/usr/local/etc        
- 帮助文件：       
&emsp;&emsp;&emsp;一般放在/usr/share/man，/usr/share/doc，/usr/local/share/man，/usr/local/share/doc        

### 三、Linux下的文件类型(以文件的存储机制来划分)：        
- －(f)：普通文件；      
- d：目录文件；     
- b：块设备；       
- c：字符设备；     
- l：符号链接文件(软连接)；   
- p：管道文件；      
- s：套接字文件；            

