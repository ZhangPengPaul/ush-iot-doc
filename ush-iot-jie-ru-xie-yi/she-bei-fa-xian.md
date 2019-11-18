---
description: 用于查找用户可用的设备、可以使用的场景模式等信息
---

# 设备发现

## 设备发现

### 设备发现请求

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | UniOS.IoT.Device.Discovery |
| name | DiscoveryDevices |

#### payload信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| gatewayId | String | IoT网关唯一ID，即在USH酒店管家绑定到房间的网关ID | true |
| accessToken | String | IoT厂商接口访问access token | true |

#### 请求示例

```javascript
{
    "header":{
        "namespace":"UniOS.IoT.Device.Discovery",
        "name":"DiscoveryDevices",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "gatewayId":"xxxxxxxxxxxxxxxxxxxxxxxx",
        "accessToken":"xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
    }
}
```

### 设备发现响应

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | UniOS.IoT.Device.Discovery |
| name | DiscoveryDevicesResponse |

#### payload信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| devices | JSON Object Array | 设备列表 | true |

设备device信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |
| deviceType | String | 设备类型，详见：[设备列表](zhi-chi-de-she-bei-lie-biao.md) | true |
| deviceName | String | 设备名称 | true |
| brand | String | 设备品牌 | true |
| model | String | 设备型号 | true |
| zone | String | 所在位置，详见：[设备属性说明](she-bei-shu-xing-shuo-ming.md#qu-yu-zone) | false |
| icon | String | 设备图标URL | true |
| properties | JSON Object Array | 设备支持的属性状态列表，详见：[设备属性说明](she-bei-shu-xing-shuo-ming.md) | true |
| actions | JSON String Array | 设备支持的操作，详见：[设备操作说明](namespace-ji-name-xiang-xi-shuo-ming.md#she-bei-kong-zhi-dui-ying-ushiotdevicecontrol) | true |

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
        "namespace":"UniOS.IoT.Device.Discovery",
        "name":"DiscoveryDevicesResponse",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "devices":[
            {
                "deviceId":"xxxxxxxxxxxxxxxx",
                "deviceType":"",
                "deviceName":"空调",
                "brand":"",
                "model":"",
                "zone":"",
                "icon":"",
                "properties":[
                    {
                        "name":"PowerState",
                        "value":"ON"
                    },
                    {
                        "name":"Temperature",
                        "value":"20"
                    }
                ],
                "actions":[
                    "TurnOn",
                    "TurnOff",
                    "SetTemperature"
                ]
            },
            {
                "deviceId":"xxxxxxxxxxxxxxxx",
                "deviceType":"",
                "deviceName":"空调",
                "brand":"",
                "model":"",
                "zone":"",
                "icon":"",
                "properties":[
                    {
                        "name":"PowerState",
                        "value":"ON"
                    },
                    {
                        "name":"Temperature",
                        "value":"20"
                    }
                ],
                "actions":[
                    "TurnOn",
                    "TurnOff",
                    "SetTemperature"
                ]
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
| namespace | UniOS.IoT.Device.Discovery |
| name | ErrorResponse |

#### payload信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| gatewayId | String | IoT网关唯一ID，即在USH酒店管家绑定到房间的网关ID | true |
| errorCode | String | 错误码，详见：[错误码](she-bei-fa-xian.md#cuo-wu-ma) | true |
| errorMessage | String | 错误信息，详见：[错误码](she-bei-fa-xian.md#cuo-wu-ma) | true |

#### 响应示例

```javascript
{
    "header":{
        "namespace":"UniOS.IoT.Device.Discovery",
        "name":"ErrorResponse",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "gatewayId":"xxxxxxxxxxxxxxxxxxxxxx",
        "errorCode":"GATEWAY_NOT_FOUND",
        "errorMessage":"gateway not found"
    }
}
```

### 错误码

| errorCode | errorMessage | 说明 |
| :--- | :--- | :--- |
| ILLEGAL\_PARAMS | illegal  params | 请求参数非法 |
| GATEWAY\_NOT\_FOUND | gateway not found | 网关设备不存在 |
| ILLEGAL\_ACCESS\_TOKEN | illegal access token | access token失效或不存在 |
| SERVICE\_ERROR | 具体错误信息 | IoT云服务异常信息 |

