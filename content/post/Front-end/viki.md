+++
date = "2016-09-08T19:42:29+08:00"
description = "纪念一下我曾经使用过的viki"
title = "VIKI页面"

+++

# 安装VIKI
## 配置
Vim+deplate

## 使用
 - 编辑一套模板，可参考[edyfox](http://edyfox.codecarver.org/html/viki_template.html)的。
 - 创建.viki文件，可以TAG_FILENAME.VIKI格式命名。
 - 使用Vim编辑。可在开头第一行加入#TITLE: TITLE 指定页面标题，第二行加入#KEYWORDS: KEYWORDS 指定该页标签
 - 使用VIKI语法撰写页面内容
 - 在命令行执行deplate -t TEMPLATE.html --css CSSNAME FILENAME.viki生成html文件；也可执行此[编译脚本](http://edyfox.codecarver.org/html/viki_script.html#labVikiScript)批量编译
   + 注意输出目录。可修改TARGET_DIR一行
   + 注意文字编码。可修改ARGS一行
   
