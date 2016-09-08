+++
date = "2016-09-08T19:42:29+08:00"
description = "响应式布局"
title = "Responsive Design"

+++

# [Responsive Design Tutorial](http://webdesignerwall.com/tutorials/responsive-design-with-css3-media-queries)

# 导语
如今屏幕分辨率从320px（iPhone）到2560px(大显示器)甚至更高。用户不仅仅通过桌面电脑浏览网页。用户会使用手机，小型笔记本，或是iPad，Playbook来上网。所以传统页面再也不适用了。网页设计要自适应。布局需要自动适应不同分辨率设备。这是一篇让你用H5和CSS3 media queries来设计跨浏览器响应式布局的指导。

# 先来看看效果
![](http://o7o0hlenq.bkt.clouddn.com/image/hexo/final-demo.jpg)
开始之前来看看[最终小样](http://webdesignerwall.com/demo/adaptive-design/final.html),改变你的浏览器大小查看页面是如何适应不同的视口宽度。

# 概览
这个页面的container宽为980px，为任何大于1024px的分辨率达到最优。Media queary检查视口是否窄于980px,是则转固定宽度为流动宽度。低于650px，内容框和侧框将占满屏宽，并形成一列。
![](http://o7o0hlenq.bkt.clouddn.com/image/hexo/design-overview.jpg)
# HTML CODE
我不会详细分析这个代码，这是布局的结构。我用pagewrap来包含header,content,sidebar,footer。

![](http://o7o0hlenq.bkt.clouddn.com/recode.png)

我在小样里用了H5，为IE9以下版本增加html5.js:

```

<!--[if lt IE 9]>

<script src="http://html5shim.googlecode.com/svn/trunk/html5.js"></script>

<![endif]-->

```

# CSS
用以下的CSS将H5元素重设为block。

```

article, aside, details, figcaption, figure, footer, header, hgroup, menu, nav, section { 

    display: block;

}

```

主pagewrap宽980px，header固定高160px，content是600px宽，左浮动。sidebar是280px宽右浮动。

```

#pagewrap {

	width: 980px;

	margin: 0 auto;

}

#header {

	height: 160px;

}

#content {

	width: 600px;

	float: left;

}


#sidebar {

	width: 280px;

	float: right;

}

#footer {

	clear: both;

}

```

# CSS3&media query
现在来到有趣的部分 - Media query。
IE8以下不支持,因而加入Media queries javascript:

```

<!--[if lt IE 9]>

	<script src="http://css3-mediaqueries-js.googlecode.com/svn/trunk/css3-mediaqueries.js"></script>

<![endif]-->

```

创建media queries的新样式表：

```

<link href="media-queries.css" rel="stylesheet" type="text/css">

```

窄于980px的视口(流动布局)

应用以下规则：

pagewrap = 重设宽为 95%

content = 重设为 60%

sidebar = 重设为 30%

提示：用百分比设置来使容器流动。

```

@media screen and (max-width: 980px) {

	#pagewrap {

		width: 95%;

	}

	#content {

		width: 60%;

		padding: 3% 4%;

	}

	#sidebar {

		width: 30%;

	}

	#sidebar .widget {

		padding: 8% 7%;

		margin-bottom: 10px;

	}

}

```

小于650Px的视口(单独成列布局)

header = 重设高度为auto

searchform = 将searchform重定位于据顶部5px

main-nav = 重设position为static

site-logo = 重设position为static

site-description = 重设position为static

content = 重设宽度为auto(这将使宽度为满宽)并且脱离流

sidebar = 重设宽度为100%并且脱离流


```
@media screen and (max-width: 650px) {

	#header {

		height: auto;

	}


	#searchform {

		position: absolute;

		top: 5px;

		right: 0;

	}


	#main-nav {

		position: static;

	}

	#site-logo {

		margin: 15px 100px 5px 0;

		position: static;

	}

	#site-description {

		margin: 0 0 15px;

		position: static;

	}

	#content {

		width: auto;

		float: none;

		margin: 20px 0;
	}

	#sidebar {

		width: 100%;

		float: none;

		margin: 0;
	}

}

```

窄于480px的视口

iPhone横置状态下

html = 禁用字体自适应。iPhone默认自动调节字体使你阅读得更舒服。你可以禁用它，用-webkit-text-size-adjust: none;语句。

main-nav = 重设字体大小为90%

```

@media screen and (max-width: 480px) {

	html {

		-webkit-text-size-adjust: none;

	}

	#main-nav a {

		font-size: 90%;

		padding: 10px 8px;

	}

}

```

灵活的图片

为了使图片灵活，只需设置max-width = 100%，height = auto。

IE8不支持，添加width:auto\9；

```

img {

	max-width: 100%;

	height: auto;

	width: auto\9; /* ie8 */

}

```

灵活的音频

如上。

Safari用width:100%代替。

```

.video embed,

.video object,

.video iframe {

	width: 100%;

	height: auto;

}

```

初始化scale meta标签(iPhone)

默认下iPhone的Safari收缩HTML页面来适应屏幕。以下标签使之将设备屏宽定为页面视口宽度，取消初始规模。

```

<meta name="viewport" content="width=device-width; initial-scale=1.0">

```

# 总结

不支持media queries的浏览器添加此js：

```

<!--[if lt IE 9]>
	
<script src="http://css3-mediaqueries-js.googlecode.com/svn/trunk/css3-mediaqueries.js"></script>

<![endif]-->

```

响应式设计的技巧即是根据视口宽度重载布局结构的CSS

```

@media screen and (max-width: 560px) {

	#content {

		width: auto;

		float: none;

	}


	#sidebar {

		width: 100%;

		float: none;
	}

}

```

灵活的图片&音频 

```

max-width:100% height:auto

img {

	max-width: 100%;

	height: auto;

	width: auto\9; /* ie8 */

}

-webkit-text-size-adjust:none来应付iPhone的字体调节

html {

	-webkit-text-size-adjust: none;

}

```

重置iPhone的视口和初始规模

```

<meta name="viewport" content="width=device-width; initial-scale=1.0">

```