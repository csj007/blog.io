---
layout: post
title: Linux第六堂课
date: 2017-08-05
categories: blog
tags: [Linux]
description: 第六堂课文件管理、命名别名和glob

---

<center>
<font size="7" ><b>文件管理、命名别名和glob</b></font>
</center> 
### 一、文件管理：     
- 复制命令cp：copy     
&emsp;&emsp;&emsp;cp SRC DEST            
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;SRC是文件：     
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;如果目标不存在，新建DEST并将SRC中内容覆盖至DEST中             
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;如果目标存在：      
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;如果DEST是文件，将SRC中的内容覆盖至DEST中（此时建议用户使用－i选项）                
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;如果DEST是目录，在其下新建与源文件同名的文件，并将SRC中的内容填充至新文件中。            
&emsp;&emsp;&emsp;cp SRC... DEST      
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;SRC...：多个文件           
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;DEST必须存在且必须为目录，否则均会出错            
&emsp;&emsp;&emsp;cp SRC DEST     
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;如果SRC是目录，则要使用选项－r         
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;如果DEST不存在，创建之并复制SRC目录中的所有文件至其中。           
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;如果DEST存在：    
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;如果DEST是文件，报错        
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;如果DEST是目录，复制源目录至其中                   
&emsp;&emsp;&emsp;常用选项：     
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;－i：交互式     
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;－r：递归复制目录及内部的所有内容     
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;－a：归档，相当于－dR －－preserv＝all     
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;－d：不追踪符号链接      
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;－－preserv＝[ATTR_LIST]     
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;mode：权限    
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;ownership：属主属组   
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;timestamp：时间戳    
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;links：链接属性       
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;xattr：扩展属性   
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;context：安全上下文   
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;all：以上所有    
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;－p：等效于－－preserv＝mode，ownership，timestamp    
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;－v：显示复制过程     
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;－f：force
- 移动文件命令mv：move               
&emsp;&emsp;&emsp;如果SRC是单个文件：          
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;如果DEST不存在，新建此文件并将源移动           
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;如果DEST存在：    
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;如果是文件， 覆盖之    
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;如果事目录，将源移入其中    
&emsp;&emsp;&emsp;如果SRC是目录：    
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;如果DEST不存在，新建此目录并将源移动          
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;如果DEST存在，则必须为目录并将源移入    
&emsp;&emsp;&emsp;如果SRC是多个文件或者目录，DEST必须存在且必须为目录，否则均会出错       
&emsp;&emsp;&emsp;常用选项：
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;－i：交互式     
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;－f：force                
- 删除命令rm：remove              
&emsp;&emsp;&emsp;常用选项：      
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;－i：交互式      
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;－f：强制删除       
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;－r：递归      
- 文件编辑器：nano            
&emsp;&emsp;&emsp;全屏编辑器               

### 二、bash的基础特性(2)：        
- 命令别名(alias)：                      
&emsp;&emsp;&emsp;通过alias命令实现(bash内建命令)    
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;alias：显示当前shell进程中所有可用的命令别名       
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;alias NAME＝'VALUE'：定义别名NAME，其相当于执行命令VALUE    
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;**注意：在命令行中定义的别名仅对当前shell进程有效**    
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;如果想永久有效，要定义在配置文件中：      
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;仅对当前用户：~/.bashrc     
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;对所有用户：/etc/bashrc    
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;重新读取配置文件：    
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;source /path/to/config_file     
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;. /path/to/config_file    
&emsp;&emsp;&emsp;撤销别名：unalias    
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;unalias －a：撤销所有别名     
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;unalias NAME：撤销某别名      
&emsp;&emsp;&emsp;**注意：如果别名和原名相同，想执行原命令可用"\COMMAND"(反斜线)**      
&emsp;&emsp;&emsp;－L ＃：显示指定＃级的层级数目        
&emsp;&emsp;&emsp;－P：只显示由指定pattern匹配到的路径      
- glob（globbing）：bash用于实现文件名“通配”           
&emsp;&emsp;&emsp;通配符：＊，？，［］                
&emsp;&emsp;&emsp;＊：       
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;任意长度的任意字符         
&emsp;&emsp;&emsp;&en  sp;?：    
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;任意单个字符      
&emsp;&emsp;&emsp;［］：    
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;匹配指定范围内的任意单个字符     
&emsp;&emsp;&emsp;［^］：          
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;匹配指定范围之外的任意单个字符     
&emsp;&emsp;&emsp;专用字符集合（外面还要再加一个中括号）：     
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;[:digitt:]：任意数字，相当于0-9      
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;[:lower:]：任意小写字母     
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;[:upper:]：任意大写字母    
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;[:alpha:]：任意大小写字母     
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;[:alnum:]：任意数字或字母       
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;[:space:]：任意空格     
&emsp;&emsp;&emsp;&emsp;&emsp;&emsp;[:punct:]：任意标点符号      


#### 本节命令总结：cp，mv，rm，nano，source，alias                 

