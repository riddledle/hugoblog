+++
date = "2016-12-01T20:20:27+08:00"
description = "主要浏览一下别人的项目，看看有哪些有趣的地方"
title = "发现之旅onTaiga"

+++

通过浏览Taiga上面有趣的敏捷开发项目，从外部也就是很表层的地方来稍微了解一下Agile开发的一些“行业规范”和其他人的习惯等。

比如首先看到的是这个：

![](http://o7o0hlenq.bkt.clouddn.com/ustory.png)

这是一个叫做AppStructurio的项目，没有Description。这个US说的是：

> 描述：
>
> 在主页面，我希望能够通过Facebook或者Github登入。
>
> 成功认证后，我希望看到我的公认头像。
>
> 分配：
>
> - 在auth0.com上建立项目
> - 开发登入功能

[Gravatar](https://cn.gravatar.com/)是提供用户公认头像的网站，[auth0](https://auth0.com/)是一款身份认证系统。

这儿的US描述遵循了“谁＋需要什么功能＋期望获得什么效果”的规范，以帮助理解。

在这个项目的US里又看到了下面这个：

![](http://o7o0hlenq.bkt.clouddn.com/ustory2.png)

这个US是希望为Angular 2.0找到一套性感的UI组件，说的是：

> 分配：
>
> - UI控件库之间的比较
> - 对最佳选择的理由陈述
> - 提交依赖到前端项目

这是一个产品相关的US，包含对UI产品的分析和选择。

顺着这个项目找到其Product Owner：

![](http://o7o0hlenq.bkt.clouddn.com/productowner.png)



从Timeline来看是个专业的项目经理，创建了许多从前端到后端的开发任务。

以上这个项目Issues很少，接着从Most Active项目里面挑了一个叫做Smart Home的项目：

![](http://o7o0hlenq.bkt.clouddn.com/issues.png)

如此多的Issues，是个很庞大且系统化的智能家居项目，参与人员有39人。

打开其中一个Issue,是个US：

![](http://o7o0hlenq.bkt.clouddn.com/smarthomeissue.png)

这是一个涉及可视化建设的US，简单的描述是：

> 描述：
>
> 作为一个顾客
>
> 我希望浏览构造器
>
> 这样我就可以创造一个控制面板

它包含4个Action：

> AC-1-添加一个组件
>
> AC-2-移除一个组件
>
> AC-3-保存一个组件
>
> AC-4-取消添加一个组件

第一条评论是这样的：

![](http://o7o0hlenq.bkt.clouddn.com/comment.png)

说的是：

> 1. 询问Taras或者Lurii我们是否需要像在地图里一样上传背景图片（？）
> 2. 添加控制面板整体布局和风格
> 3. 加载已有组件列表并根据布局排列
> 4. 从列表拖拽组件到控制面板的地图中
> 5. 展示组件信息：组件名称；当前值（摄氏度, 湿度, 开／关等）；最后更新时间；“数据”图标
> 6. 展示地图上组件的删除按钮（“X”）并通过点击删除
> 7. 处理取消动作。使用确认信息并在确认后重导页面到主页

处理后的面板看起来是这样的：

![](http://o7o0hlenq.bkt.clouddn.com/smarthome.jpg)

无论是US的描述还是Comment都是尽量详尽和规范的，因为规范化所以阅读和理解起来快速、没有歧义。

另外，发现Taiga不是自适应的，或许应该考虑推出客户端或者升级到自适应网页。