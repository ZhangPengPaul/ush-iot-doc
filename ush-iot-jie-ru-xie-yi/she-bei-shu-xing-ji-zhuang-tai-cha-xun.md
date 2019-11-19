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
| namespace | UniOS.IoT.Device.Query |
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
        "namespace":"UniOS.IoT.Device.Query",
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
| namespace | UniOS.IoT.Device.Query |
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
        "namespace":"UniOS.IoT.Device.Query",
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

## 查询单个属性（以温度为例）

查询设备的指定属性

### 查询请求

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | UniOS.IoT.Device.Query |
| name | Temperature，其他属性查询参考：[name说明](namespace-ji-name-xiang-xi-shuo-ming.md#she-bei-shu-xing-ji-zhuang-tai-cha-xun-dui-ying-ushiotdevicequery) |

#### payload信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| accessToken | String | IoT厂商接口访问access token | true |
| deviceId | String | 设备唯一ID | true |

#### 请求示例

```javascript
{
    "header":{
        "namespace":"UniOS.IoT.Device.Query",
        "name":"Temperature",
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
| namespace | UniOS.IoT.Device.Query |
| name | TemperatureResponse，（其他属性查询响应name一律为“请求name值+Response”，如：查询颜色，请求name=Color，则响应name=ColorResponse） |

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
        "namespace":"UniOS.IoT.Device.Query",
        "name":"TemperatureResponse",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "deviceId":"xxxxxxxxxxxxxxxx",
        "properties":[
            {
                "name":"Temperature",
                "value":"20"
            }
        ]
    }
}
```

## 错误响应信息

异常错误响应信息，错误情况下返回此响应内容

### 错误响应

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | UniOS.IoT.Device.Query |
| name | ErrorResponse |

#### payload信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |
| errorCode | String | 错误码，详见：错误码 | true |
| errorMessage | String | 错误信息，详见：错误码 | true |

#### 响应示例

```javascript
{
    "header":{
        "namespace":"UniOS.IoT.Device.Query",
        "name":"ErrorResponse",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx",
        "errorCode":"DEVICE_NOT_FOUND",
        "errorMessage":"device not found"
    }
}
```

### 错误码

| errorCode | errorMessage | 说明 |
| :--- | :--- | :--- |
| ILLEGAL\_PROPERTY | illegal property | 非法的属性参数或设备不支持此属性 |
| ILLEGAL\_PARAMS | illegal  params | 请求参数非法 |
| DEVICE\_NOT\_FOUND | device not found | IoT设备不存在 |
| ILLEGAL\_ACCESS\_TOKEN | illegal access token | access token失效或不存在 |
| SERVICE\_ERROR | 具体错误信息 | IoT云服务异常信息 |

