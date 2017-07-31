---
layout: post
title: Linux第二堂课
date: 2017-07-29
categories: blog
tags: [Linux]
description: 第二堂课Linux命令帮助获取详解。

---

<center>
# Linux命令帮助获取详解
</center>
### 一、Linux命令帮助的获取。
- 内部命令：help+COMMAND
- 外部命令:
1.COMMAND&emsp;－－help        
&emsp;&ensp;COMMAND&emsp;－h         
2. 使用手册（manual）         
&emsp;&ensp;man&emsp;COMMAND        
3. 信息页(支持超链接)         
&emsp;&ensp;info&emsp;COMMAND        
4. 程序自身的帮助文档           
&emsp;&ensp;README，INSTALL，ChangeLog              
5. 程序官方文档           
&emsp;&ensp;官方站点：Documentation         
6. 使用发行版的官方文档        
&emsp;&ensp;例如：Redhat官方文档        
7. Google                          
**注意：外部命令都有一个可执行程序位于文件系统某目录下。shell程序可搜寻该文件路径定义在PATH环境变量中。**   
- 内部命令帮助：             
&emsp;&emsp;&emsp;help&emsp;COMMAND        
1. hash命令：          
&emsp;&emsp;&emsp;shell搜寻到的外部命令的路径结果会缓存至kv(key-value)存储中。     

2. history命令：         
&emsp;&emsp;&emsp;作用一、管理命令历史：          
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;登录shell时读取命令历史文件中的记录：~/.bash_history               
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;登录后新执行的命令只记录在缓存中，在用户退出时“追加”至历史文件中。

&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;history:        
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;-a：追加本次会话新执行的命令历史列表至历史文件中；        
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;-d：删除历史中指定偏移位置的命令；     
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;-c：清空命令历史；        
&emsp;&emsp;&emsp;作用二、进行快捷操作：     
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;!# ：调用历史中的第＃条命令；          
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;!string：调用历史中最近一个以string开头的命令；        
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;!!：重复运行上一条命令。        
- 外部命令帮助：           
&emsp;&emsp;&emsp;1. COMMAND －－help        

&emsp;&emsp;&emsp;2. man&emsp;COMMAND       
&emsp;&emsp;&emsp;&emsp;手册页:/usr/share/man        
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;man1～man8          
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;man1：用户命令       
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;man2：系统调用      
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;man3：c库调用       
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;man4：设备文件及特殊文件    
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;man5：配置文件格式     
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;man6：游戏        
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;man7：杂项       
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;man8：管理类的命令     
&emsp;&emsp;&emsp;&emsp;**注意：有些关键字在不止一个章节中存在帮助手册；要查看需man # COMMAND**                        
&emsp;&emsp;&emsp;&emsp;man命令自身的配置文件：/etc/manpath.config                
&emsp;&emsp;&emsp;&emsp;帮助手册中的常用段落说明：         
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;NAME：完整全名及简单用途；             
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;SYNOPSIS：基本语法：         
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;[&ensp;]：可选项            
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;<&ensp;>：必选项            
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;a|b：二选一            
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;...：可重复出现               
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;DESCRIPTION：详细说明语法规则；         
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;OPTIONS：选项；      
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;EXAMPLES：示例；          
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;SEE ALSO：参考；          
&emsp;&emsp;&emsp;&emsp;man命令的操作方法：       
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;Space，^V，^F：向文件尾翻屏；      
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;b，^B：向文件首翻屏；       
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;d，^D：向文件尾翻半屏；       
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;u，^U：向文件首翻半屏；      
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;j，e：向文件尾翻一行；     
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;y，k：向文件首翻一行；         
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;/string：向下查询string字符串；        
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;?string：向上查询string字符串；        
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;n，N：查询字符串时用此来继续查询下一个该字符串；      
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;q：退出。         

&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;练习：date命令         
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;显示今天为周几？       
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;设定当前系统时间？        
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;显示今天日期，形如：17/07/30？    
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;显示当前时间，形如：17:01:56？   

&emsp;&emsp;&emsp;3. info&emsp;COMMAND            

&emsp;&emsp;&emsp;4. 程序自身的帮助文档           
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;一般在/usr/share/doc/COMMAND-VERSION       

&emsp;&emsp;&emsp;5. 程序官方文档       

&emsp;&emsp;&emsp;6. 发行版的官方文档         
&emsp;&emsp;&emsp;7. Google(可参考Google hacks)       
&emsp;&emsp;&emsp;8. www.slideshare.net                 


#### 本节命令总结：help，man，info，hash，history。

