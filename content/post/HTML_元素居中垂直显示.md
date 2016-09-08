+++
date = "2016-09-08T19:42:29+08:00"
description = "CSS的小技巧"
title = "元素垂直居中"

+++

# 一般方法

## 单行文字设置

```

 {line-height = 外部容器高度} 
 
```

## 多行文字，图片

 - 父容器

```

div {
    display:table-cell;
    vertical-align:middle
    } 
    
```

并设置固定高度

 - 内部

```

span {
    display:inline-block;
    vertical-align:middle
    } 

```

或

```

img {
    vertical-align:middle
    } 

```

## 或者
 - 内部
 
```

#content { 
    position:absolute; 
    top:50%; 
    height:240px; 
    margin-top:-120px/*内部高的一半*/ 
    } 

```

> 其他类似方法也是在固定高度的情况下设置top:50%以及margin为负。注意内部元素溢出overflow的情况。

# 补充
## 使用transform
可以使用

```

{transform: translate(-50%,-50%);} 

```

取代设margin为负。

## 固定高度的内部元素
设置

```

{ 
    top：0; 
    bottom：0; 
    margin: auto; 
} 

```

## 参考
[前段观察](https://www.qianduan.net/css-to-achieve-the-vertical-center-of-the-five-kinds-of-methods/)

