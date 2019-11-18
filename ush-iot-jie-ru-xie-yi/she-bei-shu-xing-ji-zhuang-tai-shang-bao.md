---
description: >-
  当IoT云设备属性或状态发生改变时（通过语音控制、用户手动控制、其他第三方app控制等），USH不会感知到设备状态的变更，需要IoT云主动上报设备的属性及状态信息
---

# 设备属性及状态上报

## 设备属性及状态主动上报

### 设备属性及状态主动上报API

当IoT云设备属性或状态发生改变时，需通过此接口上报设备的属性及状态信息

#### Http Method

POST

#### URL

http://gw-std.hivoice.cn/v2/iot/status-report

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
| devices | JSON Object Array | 设备列表 | true |

devices说明

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |
| properties | JSON Object Array | 设备变更的属性状态，详见：[设备属性说明](she-bei-shu-xing-shuo-ming.md) | false |

设备属性properties信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| name | String | 属性名 | true |
| value | String | 属性值 | true |

属性示例

```javascript
{
    "properties":[
        {
            "name":"PowerState",
            "value":"ON"
        },
        {
            "name":"Temperature",
            "value":"20"
        }
    ]
}
```

#### 请求示例

```javascript
{
    "header":{
        "sourceCode":"XXX",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "timestamp":1234567890123
    },
    "body":{
        "devices":[
            {
                "deviceId":"xxxxxxxxxxxxxxx",
                "properties":[
                    {
                        "name":"PowerState",
                        "value":"ON"
                    },
                    {
                        "name":"Temperature",
                        "value":"20"
                    }
                ]
            },
            {
                "deviceId":"xxxxxxxxxxxxxxx",
                "properties":[
                    {
                        "name":"PowerState",
                        "value":"ON"
                    },
                    {
                        "name":"Temperature",
                        "value":"20"
                    }
                ]
            }
        ]
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

