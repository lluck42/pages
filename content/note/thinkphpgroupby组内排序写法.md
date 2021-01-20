---
title: "kubeadm config image 阿里云镜像"
date: 2017-12-20T15:32:57+08:00
draft: false
---

有时候会遇到需要对分组内 group by 的数据进行排序。比如，一对多联表查询后，列表显示 A 表，需要关联显示 B 表的最新一条数据。

这个时候就是比较不常见的 组内排序 group by 的例子了。
<!--more-->

直接上例子：

```
$list=M('order')->field('a.is_refunded,a.is_closed,a.total,a.express,a.refunded_money,b.*')->alias('a')->join('work_order b ON a.order_code = b.order_code')->order('b.id desc')->group('a.order_code')->select();
```
```
$list=M('order')->field('a.is_refunded,a.is_closed,a.total,a.express,a.refunded_money,b.*')->alias('a')->join('(select * from work_order order by id desc) b ON a.order_code = b.order_code')->order('b.id desc')->group('a.order_code')->select();
```
关键点：

查询语句的对象 ```select * from bear_work_order order by id desc``` 代替了原生表对象 work_order

就是这么简单，灵感来源于 
>http://bbs.csdn.net/wap/topics/80276095

```select * from StudentGrade a where (select count(1) from studentGrade where subId=a.subId and grade>=a.grade)<=2```

虽然是是有些凌乱，但是 mysql **对象** 的反复操作还是很好的


