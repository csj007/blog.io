---
layout: post
title: Linux第五堂课
date: 2017-08-04
categories: blog
tags: [Linux]
description: 第五堂课bash的基础特性及基础命令

---

<center>
<font size="7" ><b>第五堂课bash的基础特性及基础命令</b></font>
</center>
### 一、bash的基础特性(1)：     
- 命令历史：     
&emsp;&emsp;&emsp;history       
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;环境变量：       
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;HISTSIZE：命令历史记录的条数       
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;HISTFILE：~/.bash_history      
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;HISTFILESIZE：命令历史文件记录历史的条数            
&emsp;&emsp;&emsp;调用上一条命令的最后一个参数：        
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;!$；       
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;ESC，.；       
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;Alt＋.；   
&emsp;&emsp;&emsp;控制命令历史的记录方式：          
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;环境变量：HISTCONTROL         
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;ignoredups：忽略重复的命令(连续且完全相同)       
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;ignorespace：忽略空格开头的命令     
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;ignoreboth：ignorespace，ignoredups             
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;修改环境变量的方式：export&emsp;变量名＝"值"     
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;变量赋值：把赋值符号后面的数据存储于变量名指向的内存空间       
- 命令补全：             
&emsp;&emsp;&emsp;直接补全：Tab，用户给定的字符串只有一条唯一对应的命令；       
&emsp;&emsp;&emsp;简介补全：Tab敲两次，则给出列表；           
- 路径补全：         
&emsp;&emsp;&emsp;把用户给出的字符串当作路径开头，并在指定上级目录下搜索以指定字符串开头的文件名。如果唯一，则直接补全；不唯一再次敲Tab，则给出列表         
- 命令行展开：     
&emsp;&emsp;&emsp;~：展开为用户的主目录      
&emsp;&emsp;&emsp;~USERNAME：展开为指定用户的主目录     
&emsp;&emsp;&emsp;{}：可承载一个以逗号分隔的列表，并将其展开为多个路径    
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;如：/tmp{a,b}＝/tmp/a, /tmp/b      
- 命令执行的状态结果：      
&emsp;&emsp;&emsp;成功／失败      
&emsp;&emsp;&emsp;bash使用**特殊变量$?**保存最近一条命令的执行状态结果：        
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;0：成功       
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;1-255：失败      
&emsp;&emsp;&emsp;**注意，程序执行有两类结果，一类是程序返回值，一类是程序执行的状态结果。**     

### 二、再谈目录类管理命令：        
- 之前学过cd，pwd，ls；      
- mkdir：          
&emsp;&emsp;&emsp;mkdir [options] /path/to/somewhere    
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;－p：存在时不报错，不存在时可自动创建所需的各目录；    
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;－v：显示创建时的详细信息；      
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;－m：MODE，创建目录时直接指定权限；      
- tree：树状显示指定目录下的所有目录和文件；       
&emsp;&emsp;&emsp;－d：只显示目录      
&emsp;&emsp;&emsp;－L ＃：显示指定＃级的层级数目        
&emsp;&emsp;&emsp;－P：只显示由指定pattern匹配到的路径      

- rmdir：删除空目录       
&emsp;&emsp;&emsp;mkdir [options]...directory                
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;－v：显示删除过程；       
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;－p：递归删除上层的空目录；    
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;－r：全部删除；      

### 三、再谈文本文件查看类命令：
- 之前学过cat，tac      
- more：    
&emsp;&emsp;&emsp;more [OPTIONS]...FILE...     
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;－d：显示翻页及退出提示    
- less：     
&emsp;&emsp;&emsp;less [OPTIONS]...FILE...     
- head：     
&emsp;&emsp;&emsp;head [OPTIONS]...FILE...     
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;－c ＃：指定获取前＃字节     
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;－n ＃或者直接－＃：指定获取前＃行    
- tail：
&emsp;&emsp;&emsp;tail [OPTIONS]...FILE...     
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;－c ＃：指定获取后＃字节      
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;－n ＃或者直接－＃：指定获取后＃行    
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;－f：跟踪显示文件新追加的内容      

### 四、文件的时间戳管理命令：   
- 文件有两类数据：metadata，data     
- 查看文件状态命令：stat      
- 文件的三个时间戳：      
&emsp;&emsp;&emsp;access time(atime)：最近一次访问时间(读取文件内容或者执行可执行文件)      
&emsp;&emsp;&emsp;modify time(mtime)：最近一次修改时间(改变文件内容或者数据)      
&emsp;&emsp;&emsp;change time(ctime)：最近一次改变时间(元数据发生改变)
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;**注意，atime和mtime都是元数据**              
- touch：可修改三个时间戳的前两个(也可创建文件)       
&emsp;&emsp;&emsp;touch [OPTIONS]...FILE...     
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;－a：only atime     
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;－m：only mtime     
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;－t STAMP：    
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;[[CC]YY]MMDDhhmm[.ss]      
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;－c：如果文件不存在则不予创建     


#### 本节命令总结：mkdir，rmdir，tree，!$，{}，Tab            

