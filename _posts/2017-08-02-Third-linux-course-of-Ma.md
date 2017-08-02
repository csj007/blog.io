---
layout: post
title: Linux第三堂课
date: 2017-08-02
categories: blog
tags: [Linux]
description: 第三堂课Linux基础命令。

---

<center>
<font size="7" ><b>Linux基础命令</b></font>
</center>
### 一、基础命令。
- Linux系统中的两种时钟：
1. 系统时钟：由linux内核通过cpu的工作频率计时；              
2. 硬件时钟；         
3. 要使两者同步，用命令：hwclock；                 
&emsp;&emsp;－s，&emsp;－－hctosys                   
&emsp;&emsp;－w，&emsp;－－systohc              

### 二、目录相关的命令
- 当前目录或工作目录        
- 主目录（家目录，home）     
&emsp;&emsp;&emsp;root：/root          
&emsp;&emsp;&emsp;普通用户：/home/USERNAME     
&emsp;&emsp;&emsp;~：用户的主目录      
- cd：        
&emsp;&emsp;&emsp;cd或cd ~：回当前用户的主目录    
&emsp;&emsp;&emsp;cd  ~USERNAME：切换至指定用户的主目录               
&emsp;&emsp;&emsp;cd －：可以在上一个目录和当前目录来回切换            
&emsp;&emsp;&emsp;cd .：当前目录       
&emsp;&emsp;&emsp;cd ..：上一级目录         
&emsp;&emsp;&emsp;相关的环境变量：        
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;PWD：保存了当前目录路径       
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;OLDPWD：上一次所在的目录路径      
- pwd：显示当前目录       
- ls：显示指定路径下的文件列表；       
&emsp;&emsp;&emsp;ls [OPTIONS]... [DIR]...        
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;－a，－－all：显示所有文件，包括隐藏文件；     
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;－l：使用长格式；        
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;－h：单位换算；      
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;－d：显示目录自身的相关属性，通常与－l一起使用；     
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;－r：逆序显示；      
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;－R：递归；        
- stat /PATH/SOMEFILE：获取指定文件的元数据   

### 三、文件查看命令：              
- cat：         
&emsp;&emsp;&emsp;cat [OPTIONS]... [FILE]...      
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;－E：显示行结束符$          
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;－n：对显示出的每一行进行编号（从1开始）      
- tac:逆序查看，选项与cat都一样      
- less：可向前向后翻页查看      
- more：向后翻页查看              

### 四、文件内容类型查看文件：file
### 五、显示相关的命令：         
- echo：回显命令                     
&emsp;&emsp;&emsp;－n：禁止自动添加换行符号；        
&emsp;&emsp;&emsp;－e：允许使用转义符；         
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;\n：换行             
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;\t：制表符            
&emsp;&emsp;&emsp;echo "$VAR_NAME"：变量会替换，双引号表示弱引用；                
&emsp;&emsp;&emsp;ehco "$VAR_NAME"：变量不会替换，单引号表示强引用。        
- which：显示命令对应的程序文件路径         
&emsp;&emsp;&emsp;which [OPTIONS] COMMAND            
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;－－skip－alias：跳过别名           
- whatis：       
&emsp;&emsp;&emsp;使用mkwhatis命令可将当前系统上所有的帮助手册及与之对应的关键字创建为一个数据库；     

### 六、系统管理类命令：
- 关机：          
&emsp;&emsp;&emsp;halt，poweroff，shutdown，init 0          
- 重启：          
&emsp;&emsp;&emsp;reboot，shutdown，init 6        
- 跟用户登录相关：         
&emsp;&emsp;&emsp;who，whoami，w        


#### 本节命令总结：date，hwclock，cd，pwd，ls，stat，cat，tac，less，more，file，echo，which，whatis，halt，poweroff，shutdown，init，reboot，who，whoami，w
