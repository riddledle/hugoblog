+++
date = "2016-09-08T19:42:29+08:00"
description = "音频播放器"
title = "Fullpage.js"

+++

# 简介
[Fullpage.js](https://github.com/riddledle/fullPage.js) (github repository)是一个多浏览器兼容的插件

# 使用
 - 包括jQuery library
 - 包括jquery.fullpage.js/jquery.fullpage.min.js
 - 包括jquery.fullpage.css

* HTML结构

```

 <div id="fullpage"> 
    <div class="section active">Some section</div> 
    <div class="section">Some section</div> 
    <div class="section">Some section</div> 
    <div class="section">Some section</div> 
 </div> 
 
 ```

* 使用slider

```

 <div class="section"> 
    <div class="slide"> Slide 1 </div> 
    <div class="slide"> Slide 2 </div> 
    <div class="slide"> Slide 3 </div> 
    <div class="slide"> Slide 4 </div> 
 </div> 
 
 ```

* 初始化

```

 $(document).ready(function() { 
    $('#fullpage').fullpage(); 
 }); 
 
 ```

* 插入音频/视频
使用 ```data-autoplay``` 属性使音频/视频能够自动播放, `data-keepplaying` 属性使离开某页时音频/视频继续播放。

```

 <audio data-autoplay> 
    <source src="http://metakoncept.hr/horse.ogg" type="audio/ogg"> 
 </audio> 
 
 ```

* 实例
[google](http://www.yourprimer.com/) 
[McDonalds](https://mcdonalds.com.au/create-your-taste)
[sony](http://www.sony-asia.com/microsite/mdr-10/#ncPage)

