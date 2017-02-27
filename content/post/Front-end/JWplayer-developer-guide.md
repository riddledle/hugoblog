+++
date = "2016-09-08T19:42:29+08:00"
description = "音频播放器"
title = "JWplayer"

+++

# JWplayer

 - 注册一个账号
 - 本地上传MP4/FLV/AVI格式的视频或通过视频的URL上传，至Playlist
 - 修改视频的description、tag等信息；修改Player的样式信息
 - 调出publish mode，把EMBED处的代码复制粘贴至code里（分script和iframe两种）
 - 运行调试没有问题后，在dashboard板块下的analytics里追踪视频的信息。

# [JW Player Developer Guide](https://developer.jwplayer.com/jw-player/docs/developer-guide/)

jwplayer说明文档的developer guide的Introduction和Intro to Javascript API部分。

## 介绍
Hello world！我们是JWPLAYER。我们致力于使（你这样的）开发者与设计者为网页、手机、OTT电视的观众建设、个性化、发布最佳观赏体验的视频。

### 目标
我们希望提供一份使用JWPLAYER高级功能的说明文档。你将获得巩固的API和设计资源检索以加快你的播放器开发进程。

### 目标用户
此页主要面向在工程中使用JWPLAYER的开发者和设计者。需了解标准设定和如何嵌入播放器，请参考[支持文档](https://support.jwplayer.com/)。如果你要浏览开发者页，则需要基础的JAVASCRIPT能力以使用API，且需要CSS知识以丰富基础的模型。

### 结构
此开发指导分为两块：JAVASCRIPT API（即将到来）和视觉优化。每部分包含起步、说明文档、示例代码、小样链接、附加资源。

### 联系我们
如果在开发者页找不到你需要的资源：
 - 我们定期管理[StackOverflow](https://stackoverflow.com/questions/tagged/jwplayer)上的问题。
 - 我们欢迎你为[GITHUB](https://github.com/jwplayer/jwplayer)上的开源代码做贡献。
 - 联系我们的TWITTER[JWDevelopers](https://twitter.com/JWDevelopers)。
 - 我们会通过邮件给予反馈（或者一个新的喵视频！）devrelation@jwplayer.com

## JAVASCRIPT API简介
此文简介了如何使用JWPLAYER的[JAVASCRIPT API](http://www.jwplayer.com/products/jwplayer/javascript/)。它可以使你增强你嵌入的播放器的功能，或者实现丰富的页面级别的交互。除非标注，否则Flash和HTML5 的API命令没有区别，因此你的代码可以跨技术域工作。
注：我们强烈建议所有API命令在播放器准备完毕后运行。

### 通过JWPLAYER API获取信息
特定的API命令使用“get”前缀，标明它们的直接目的是返回特定信息。可以是对象，数组，字符串，数字。参考[Javascript API Reference](https://developer.jwplayer.com/jw-player/docs/developer-guide/api/javascript_api_reference/)查看返回形式。

#### "GET"API命令返回如下形式信息：
 - 用jwplayer().getPlaylist()获得播放列表项目的数组；
 - 用jwplayer().getDuration()获得视频时长；
 - 用jwplayer().getsState()获得播放器状态；
 - 用jwplayer().getHeight()和jwplayer.getWidth()获得当前播放器的像素规模。
 
#### 控制和设置JWPLAYER API
以下命令用来控制播放器行为。大部分命令需要一个传入值。比如，setVolume()需要一个1-100的数字传入。

#### API命令可以使播放器：
 - 用jwplayer().pause(true)停止播放；
 - 用jwplayer().setVolume(50)设置音量为50%；
 - 用jwplayer().seek(120)获得视频2分钟的位置。
 
### 通过JWPLAYER API实现事件监听
播放器做什么的时候会触发特定事件。JWP7基于[backbone.events](http://backbonejs.org/#Events)实现事件结构。使一个播放器实例成为事件引导并给予开发者更好的选项和控制。特定事件同样返回信息。指定信息在[javascript API reference](https://developer.jwplayer.com/jw-player/docs/developer-guide/api/javascript_api_reference/)文档中。
目前JWP支持以下事件驱动：
![](http://o7o0hlenq.bkt.clouddn.com/listener.png)

以下事件驱动在每次音量改动时触发，并返回一个带名叫"volume"的数字的对象。

```

jwplayer().on('volume', function(e) {

    alert("Volume is changed to: "+ e.volume);

                                    });

```

### 示例：使用JWP
player setup需要在实现播放器互动前安装。[Embedding Section](https://support.jwplayer.com/customer/portal/topics/601065-embedding/articles)包含许多例子。这是一个基础播放器嵌入的标准语法：

```

<div id='myElement'>Loading the player...</div> 

<script type='text/javascript'>

jwplayer("myElement").setup({ 

    "file": "/uploads/example.mp4", 

    "image": "/uploads/example.jpg"

});

</script>

```

一旦实现setup，API立刻就能用。如果你的页面内有一个播放器，它总能被playerInstance函数获取。比如：

```

<script>

jwplayer("myElement").on('complete', function(){

    alert("Complete fired - Your content has completed!");

});

</script>

<a href="javascript:jwplayer('myElement').play();">Toggle playback</a>

<a href="javascript:alert('The volume of the player is: ' + jwplayer('myElement').getVolume());">Report volume</a>

```

### 多个播放器下指定
当页面内有多个播放器，你需要指定你要和哪个交互。假设我们一个页面内嵌入了两个不同的播放器：

```

<div id='myFirstPlayer'>Loading the first player...</div>

<div id='mySecondPlayer'>Loading the player...</div>


<script type='text/javascript'>

jwplayer("myFirstPlayer").setup({ 

    "file": "/uploads/example.mp4", 

    "image": "/uploads/example.jpg"

});

jwplayer("mySecondPlayer").setup({ 

    "file": "/uploads/example2.mp4", 

    "image": "/uploads/example2.jpg"

});

</script>

```

有两种方法来指定一个播放器：
 * 使用div的id

```

// ID references the first player

jwplayer("myFirstPlayer").play();

```

 * 使用播放器index

```

// An index of 1 targets the second player on the page 

jwplayer(1).play();

```

注：什么都不标明的话，将指向页面内第一个播放器。

### Require.js和JWPLAYER
JWPLAYER目前不被require js支持因为JWPLAYER需要自己的命名空间。避免require和jwplayer.js在同一页面时的问题，在require.js之前加载jwplayer.js。
例：

```

<script src='jwplayer.js'>

<script src='requirejs.js'>

```

### 小记表
这张表是所有API命令的小抄。[JAVASCRIPT API Reference](https://developer.jwplayer.com/jw-player/docs/developer-guide/api/javascript_api_reference/)包含了所有API命令的参数。点击相应类名转到对应查询。为了简化，我们只介绍on事件。如上所述，还可以是off,once,trigger事件。

![](http://o7o0hlenq.bkt.clouddn.com/QQ%E5%9B%BE%E7%89%8720160524153029.png)

![](http://o7o0hlenq.bkt.clouddn.com/sheet2.png)






