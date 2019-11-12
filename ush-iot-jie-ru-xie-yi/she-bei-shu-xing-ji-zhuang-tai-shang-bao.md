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
| devices | JSON Object Array | 设备列表 | true |

设备devices信息

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
      <td style="text-align:left">String</td>
      <td style="text-align:left">
        <p>&#x8FD4;&#x56DE;&#x72B6;&#x6001;&#x7801;&#xFF1A;</p>
        <p>200&#xFF1A;&#x6210;&#x529F;</p>
        <p>500&#xFF1A;&#x5931;&#x8D25;</p>
      </td>
      <td style="text-align:left">true</td>
    </tr>
    <tr>
      <td style="text-align:left">businessCode</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x4E1A;&#x52A1;&#x72B6;&#x6001;&#x7801;&#xFF0C;code=200&#x662F;&#x4E3A;&#x7A7A;</td>
      <td
      style="text-align:left">false</td>
    </tr>
    <tr>
      <td style="text-align:left">businessMessage</td>
      <td style="text-align:left">String</td>
      <td style="text-align:left">&#x4E1A;&#x52A1;&#x72B6;&#x6001;&#x8BF4;&#x660E;&#xFF0C;code=200&#x662F;&#x4E3A;&#x7A7A;</td>
      <td
      style="text-align:left">false</td>
    </tr>
  </tbody>
</table>#### 响应结果示例

```javascript
{
    "code":"200",
    "businessCode":null,
    "businessMessage":null
}
```

