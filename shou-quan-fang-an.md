---
description: 详细介绍IoT厂商的授权方案及流程
---

# 授权方案

## 概述

采用通用的OAuth2.0的开放协议授权（**目前仅支持授权码模式**），可以让USH在IoT厂商的授权下访问资源，协议规范：[https://oauth.net/2/](https://oauth.net/2/)

## 鉴权流程

1. IoT厂商为USH分配一个授权应用，获得相应的client id及client secret
2. USH向IoT厂商发起一个授权请求
3. IoT厂商生成code，并通过\#2中的USH callback URL返回
4. USH携带\#3生成的code调用IoT厂商获取token URL，换取access token
5. USH使用access token访问IoT厂商提供的服务

## 示例

### 1.发起授权

```http
http://www.xxxx.com/auth/authorize?redirect_url=
http%3a%2f%2fgw-std.hivoice.cn%2fauth%2fcallback%3ffactory_code%3dXXX&client_id=XXX&
response_type=code&state=XXX
```

#### 1.1 参数说明

`redirect_url` : USH的回调地址，该地址上会附加USH相关参数，并进行URLEncode，IoT厂商需在此URL上添加code参数返回。

`client_id` : IoT厂商分配的应用id

`response_type` : 固定值code

`state` : 客户端状态，认证服务器原样返回，用于抵制CSRF攻击

