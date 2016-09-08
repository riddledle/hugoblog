+++
date = "2016-09-08T19:42:29+08:00"
description = "一款转换md/html文件的软件"
title = "Pandoc"

+++

# 使用[Pandoc](http://www.pandoc.org/getting-started.html)实现markdown文件和html文件之间的转换。

# 参考官方文档，以windows系统为例。

 * 安装。（WIN8系统下建议在命令提示符下以管理员身份运行安装程序）
 * 打开命令提示符
 * 切换目录。
  - cd Documents 至文档目录下
  - mkdir <目录名> 新建目录文件夹
 * 在命令行转换。
  - 输入pandoc
  - 输入markdown/html语法文档
  - 按下Ctrl-Z，回车
 (默认是认为传入markdown语法，转换为html语法)
 * 使用编辑器在目录下编辑一个文件
 * 使用语法 
 
 ```
 
 pandoc test1.md -f markdown -t html -s -o test1.html 
 
 ```
 
 转换

# 查看[User's Guide](http://www.pandoc.org/README.html)获取更多关于转换格式的内容。 
若是想转为PDF格式，需要[Latex](http://www.latex-project.org/)支持。

# 将markdown文件转换为pdf文件则可以使用[MdCharm](http://www.mdcharm.com/)。

