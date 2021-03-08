---
title: "百度图片检索api"
date: 2021-03-08T11:43:25+08:00
tags: []
featured_image: ""
description: ""
---


因项目需求，需要图片检索

本打算从百度图片检索中网页抓取，但是无意间看到了一个api

多次测试、删减参数，剩余参数如下：

```
https://image.baidu.com/search/acjson?tn=resultjson_com&ipn=rj&word=火爆鱿鱼&rn=100&pn=1

tn=resultjson_com 必填，不填404，应该是定义返回格式的
ipn=rj 必填，不填404，功能未知。。。

word=关键字 填入要检索的内容
rn=100  range number 每页条数
pn=1  page number 当前页
```


查询结果：

![官网 demo 截图](/images/百度图片检索api.jpg)

然后就可以根据查询的图片地址，愉快的选图了 O(∩_∩)O哈哈~