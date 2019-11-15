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

IoT厂商授权URL为：[http://www.xxxx.com/auth/authorize](http://www.xxxx.com/auth/authorize)

IoT厂商获取tokenURL为：[http://www.xxxx.com/auth/token](http://www.xxxx.com/auth/token)

### 1.发起授权

```http
http://www.xxxx.com/auth/authorize?redirect_url=
http%3a%2f%2fgw-std.hivoice.cn%2fauth%2fcallback%3ffactory_code%3dXXX&client_id=XXX&
response_type=code&state=XXX
```

#### 1.1 请求参数说明

| 参数名 | 说明 |
| :--- | :--- |
| redirect\_url | USH的回调地址，该地址上会附加USH相关参数，并进行URLEncode，IoT厂商需在此URL上添加code参数返回 |
| client\_id | IoT厂商分配的应用id |
| response\_type | 固定值code |
| state | 客户端状态，可以是任意值，认证服务器原样返回，用于抵制CSRF攻击 |

#### 1.2 授权返回code

授权成功后，通过`redirect_url`使用query string返回code

```http
http://gw-std.hivoice.cn/auth/callback?factory_code=XXX&code=03cQZu
```

### 2. 通过code获取token

```http
http://www.xxxx.com/auth/token?grant_type=authorization_code&code=03cQZu
&client_id=client&client_secret=secret&redirect_uri=http://example.com
```

#### 2.1 请求参数说明

| 参数名 | 说明 |
| :--- | :--- |
| client\_id | IoT厂商分配的应用id |
| client\_secret | IoT厂商分配应用秘钥 |
| grant\_type | 授权模式，固定值authorization\_code |
| code | 上一步授权时返回给USH的授权code |
| redirect\_uri | USH回调地址 |

#### 2.2 正确响应结果（响应格式必须为application/json）

| 参数名 | 参数类型 | 参数说明 |
| :--- | :--- | :--- |
| access\_token | String | 访问令牌 |
| token\_type | String | 令牌类型 |
| expires\_in | long | 令牌过期时间，长度为秒 |
| refresh\_token | String | 刷新令牌，用以换取下次访问令牌 |

#### 2.3 正确响应示例

```javascript
{
    "access_token":"10337f46-fe9b-4914-9f1b-15d3bfd6227b",
    "token_type":"bearer",
    "refresh_token":"1cc55626-9fc0-47ac-8f3f-685abd11deaf",
    "expires_in":7200
}
```

{% hint style="info" %}
access\_token有效期请设置成1天以上（2-3天最佳）
{% endhint %}

#### 2.4 错误响应结果（响应格式必须为application/json）

| 参数名 | 参数类型 | 参数说明 |
| :--- | :--- | :--- |
| error | String | 错误响应码 |
| error\_description | String | 错误详情描述 |

#### 2.5 错误响应示例

```javascript
{
    "error":"errorCode",
    "error_description":"description"
}
```

### 3. 通过refresh\_token刷新access\_token

```http
http://www.xxxx.com/auth/token?grant_type=refresh_token
&refresh_token=8b6c262d-22cb-4e5b-af08-a32cbee5c5c2
```

#### 3.1 请求参数说明

| 参数名 | 参数说明 |
| :--- | :--- |
| grant\_type | 授权模式，固定值refresh\_token |
| refresh\_token | 刷新令牌 |

#### 3.2 正确响应结果（响应格式必须为application/json）

| 参数名 | 参数类型 | 参数说明 |
| :--- | :--- | :--- |
| access\_token | String | 访问令牌 |
| token\_type | String | 令牌类型 |
| expires\_in | long | 令牌过期时间，长度为秒 |
| refresh\_token | String | 刷新令牌，用以换取下次访问令牌 |

#### 3.3 正确响应示例

```javascript
{
    "access_token":"10337f46-fe9b-4914-9f1b-15d3bfd6227b",
    "token_type":"bearer",
    "refresh_token":"1cc55626-9fc0-47ac-8f3f-685abd11deaf",
    "expires_in":7200
}
```

{% hint style="info" %}
access\_token有效期请设置成1天以上（2-3天最佳）
{% endhint %}

#### 3.4 错误响应结果（响应格式必须为application/json）

| 参数名 | 参数类型 | 参数说明 |
| :--- | :--- | :--- |
| error | String | 错误响应码 |
| error\_description | String | 错误详情描述 |

#### 3.5 错误响应示例

```javascript
{
    "error":"errorCode",
    "error_description":"description"
}
```

