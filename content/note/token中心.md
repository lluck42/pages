---
title: "token-centre"
date: 2022-02-09T10:46:42+08:00
tags: []
featured_image: ""
description: "token中心、微信公众号、低延迟、零依赖、可扩展、流程简单"
---

# token-centre

#### 介绍

- token-centre token中心
- 低延迟、零依赖、可扩展、流程简单
- 支持 微信公众号
- 场景
- 用于单个公司多个产品，多平台 token 中心存储
- 只需填写 appid appsecret 等关键信息
- 延迟2ms~3ms

#### 软件架构
gin、内存缓存、sqlite3
零依赖
可直接运行
#### 安装教程

1.  git clone https://gitee.com/lluck42/token-centre.git

#### 使用说明

1.  cd token-centre
2.  go run .
3.  curl http://127.0.0.1:8080/api/tokenGet?PlateformName=微信公众号&AppName=我的应用-订阅号
