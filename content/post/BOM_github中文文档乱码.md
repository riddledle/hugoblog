+++
date = "2016-09-08T19:42:29+08:00"
description = "解决了一个乱码问题"
title = "github中文文档乱码"

+++

# markdown文件转html之后在firefox里显示乱码

firefox判断编码：

 - 根据HTML文件的BOM
 - 根据HTML中命令指定的编码
 - 用户在编辑时手动在菜单中指定

# 解决：

 - 编辑时指定encoding - utf-8
 - 在头部加入 
 
 ```
 
 <meta http-equiv="Content-Type" content="text/html;charset=utf-8">
 
 ```

