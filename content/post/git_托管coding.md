+++
date = "2016-09-08T19:42:29+08:00"
description = "翻越度娘"
title = "托管coding"

+++

# 百度无法收录托管在Github上的blog,可以考虑同时托管在github和coding上。

 - 注册coding
  - 创建和用户名同名的repo。将已有的github的公钥部署到项目中
 - 更改_config.yml
  - 在deploy项目下添加repo“coding:[repo-url],master”
 - 输入$ssh -T git@git.coding.net验证是否成功
  - 此处可能显示faild.可删除.ssh/known_hosts内的内容重试
 - hexo d -g 
 - 设置pages服务
  - 在source目录下添加Staticfile空白文件。pages分支选择master。等待一段时间后，可访问专用域名
 - 设置域名解析以绑定个人域名
  - 可为github选择海外线路，coding国内线路
