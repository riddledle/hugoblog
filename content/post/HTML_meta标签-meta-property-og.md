+++
date = "2016-09-08T19:42:29+08:00"
description = "h5的新标签"
title = "meta标签和-meta-property-og"

+++
#TITLE: meta标签-meta-property-og

# meta标签
 - 位于 `<head>` 与 `<title>` 之间
 - 用户不可见
 - 为搜索引擎robots定义页面主题，定义用户浏览器上的cookie
 - 鉴别作者，设定格式，标注内容，定义行为等

# name 属性
 - “Generator” 说明生成工具
 - “KEYWords” 网页关键词
 - “Description”
 - “Author”
 - “Robots”
  content=
     - "all" 文件将被检索，且页面上的链接可以被查询
     - “none” 文件将不被检索，且页面上的链接不可以被查询
     - “index”文件将被检索 
     -  “follow”页面上的链接可以被查询
     -  “noindex”文件将不被检索，但页面上的链接可以被查询
     -  “nofollow”文件将被检索，但页面上的链接不可以被查询
  
# http-equiv属性
 - “Content-Type” 字符集
 - “Content-Language”语言
 - “Refresh”跳转
 - “Expires”指定到期时间
 - “set-cookie”设定cookie
 - “windows-Target”页面显示

# og = [Open Graph Protocol](http://www.ogp.me/)
The Open Graph Protocol enables any web page to become a rich object in a social graph
——此协议使网页成为富媒体对象。2010年F8会议上Facebook提出。同意网站内容被其他社会化网站引用，提高站外内容传播效率。

og:
 - url
 - title
 - image
 - description
 - type
 - video
  - secure_url
  - type
  - width
  - height

