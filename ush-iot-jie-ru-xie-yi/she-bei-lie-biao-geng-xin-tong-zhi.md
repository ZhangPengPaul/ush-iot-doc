---
description: 接入的设备列表发生变动时（新增、删除、更新等）需要通知USH更新设备列表信息
---

# 设备列表更新通知

## 设备列表更新通知

### 设备列表更新通知API

接入的设备列表发生变动时（新增、删除、更新等）需要通过此API通知USH更新设备列表信息，USH收到请求后会发起设备同步请求到IoT云

#### Http Method

POST

#### URL

http://gw-std.hivoice.cn/v2/iot/device-sync

#### 请求参数

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| header | JSON Object | 请求头 | true |
| body | JSON Object | 请求体 | true |

header信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| sourceCode | String | 接入渠道，由云知声提供 | true |
| requestId | String | 请求流水号 | true |
| timestamp | long | 请求时间戳，单位ms | true |

body信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| gatewayId | String | IoT网关唯一ID，即在USH酒店管家绑定到房间的网关ID | true |

#### 请求示例

```javascript
{
    "header":{
        "sourceCode":"XXX",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "timestamp":1234567890123
    },
    "body":{
        "gatewayId":"xxxxxxxxxxxxxxx"
    }
}
```

#### 响应结果

<table>
  <thead>
    <tr>
      <th style="text-align:left">&#x53C2;&#x6570;&#x540D;</th>
      <th style="text-align:left">&#x53C2;&#x6570;&#x7C7B;&#x578B;</th>
      <th style="text-align:left">&#x53C2;&#x6570;&#x8BF4;&#x660E;</th>
      <th style="text-align:left">&#x662F;&#x5426;&#x5FC5;&#x586B;</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">code</td>
      <td style="text-align:left">int</td>
      <td style="text-align:left">
        <p>&#x8FD4;&#x56DE;&#x72B6;&#x6001;&#x7801;&#xFF1A;</p>
        <p>0&#xFF1A;&#x6210;&#x529F;</p>
        <p>500&#xFF1A;&#x5931;&#x8D25;</p>
      </td>
      <td style="text-align:left">true</td>
    </tr>
    <tr>
      <td style="text-align:left">message</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x7CFB;&#x7EDF;&#x54CD;&#x5E94;&#x63CF;&#x8FF0;</td>
      <td style="text-align:left">true</td>
    </tr>
    <tr>
      <td style="text-align:left">businessCode</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x4E1A;&#x52A1;&#x72B6;&#x6001;&#x7801;</td>
      <td style="text-align:left">true</td>
    </tr>
    <tr>
      <td style="text-align:left">businessMessage</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x4E1A;&#x52A1;&#x72B6;&#x6001;&#x8BF4;&#x660E;</td>
      <td style="text-align:left">true</td>
    </tr>
    <tr>
      <td style="text-align:left">data</td>
      <td style="text-align:left">JSON Object</td>
      <td style="text-align:left">&#x4E1A;&#x52A1;&#x8FD4;&#x56DE;&#x6570;&#x636E;</td>
      <td style="text-align:left">false</td>
    </tr>
  </tbody>
</table>#### 响应结果示例

```javascript
{
    "code":0,
    "message":"SUCCESS",
    "businessCode":"0000",
    "businessMessage":"success"
}
```

