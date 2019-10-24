---
description: 查询设备的属性及状态信息
---

# 设备属性及状态查询

## 所有属性查询

查询设备所支持的所有属性及状态

### 查询请求

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Query |
| name | All |

#### payload信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| accessToken | String | IoT厂商接口访问access token | true |
| deviceId | String | 设备唯一ID | true |

#### 请求示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Query",
        "name":"All",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "accessToken":"xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx"
    }
}
```

### 查询响应

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Query |
| name | AllResponse |

#### payload响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |
| properties | JSON Object Array | 设备支持的属性状态列表，详见：[设备属性说明](she-bei-shu-xing-shuo-ming.md) | true |

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

#### 响应示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Query",
        "name":"AllResponse",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "deviceId":"xxxxxxxxxxxxxxxx",
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
}
```

