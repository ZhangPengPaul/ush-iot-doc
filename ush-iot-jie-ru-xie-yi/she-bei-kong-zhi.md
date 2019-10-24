---
description: 设备控制对智能家居设备进行控制
---

# 设备控制

## 开关控制

打开关闭设备包括打开设备、关闭设备、定时关闭设备、停止设备等操作。

### TurnOn请求

打开设备

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | TurnOn |

#### payload信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| accessToken | String | IoT厂商接口访问access token | true |
| deviceId | String | 设备唯一ID | true |

#### 请求示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"TurnOn",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "accessToken":"xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx"
    }
}
```

### TurnOn响应

打开设备的响应结果

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | TurnOnResponse |

#### payload正常响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |

#### payload异常响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |
| errorCode | String | 错误码，详见//TODO | true |
| errorMessage | String | 错误信息描述，详见//TODO | true |

#### 正常响应示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"TurnOnResponse",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx"
    }
}
```

#### 异常响应示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"TurnOnResponse",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx",
        "errorCode":"USH.ERROR.DEVICE_NOT_FOUND",
        "errorMessage":"device not found"
    }
}
```

### TurnOff请求

关闭设备

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | TurnOff |

#### payload信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| accessToken | String | IoT厂商接口访问access token | true |
| deviceId | String | 设备唯一ID | true |

#### 请求示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"TurnOff",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "accessToken":"xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx"
    }
}
```

### TurnOff响应

关闭设备响应

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | TurnOffResponse |

#### payload正常响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |

#### payload异常响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |
| errorCode | String | 错误码，详见//TODO | true |
| errorMessage | String | 错误信息描述，详见//TODO | true |

#### 正常响应示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"TurnOffResponse",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx"
    }
}
```

#### 异常响应示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"TurnOffResponse",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx",
        "errorCode":"USH.ERROR.DEVICE_NOT_FOUND",
        "errorMessage":"device not found"
    }
}
```

### Pause请求

暂停操作

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | Pause |

#### payload信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| accessToken | String | IoT厂商接口访问access token | true |
| deviceId | String | 设备唯一ID | true |

#### 请求示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"Pause",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "accessToken":"xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx"
    }
}
```

### Pause响应

暂停操作响应

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | PauseResponse |

#### payload正常响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |

#### payload异常响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |
| errorCode | String | 错误码，详见//TODO | true |
| errorMessage | String | 错误信息描述，详见//TODO | true |

#### 正常响应示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"PauseResponse",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx"
    }
}
```

#### 异常响应示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"PauseResponse",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx",
        "errorCode":"USH.ERROR.DEVICE_NOT_FOUND",
        "errorMessage":"device not found"
    }
}
```

## 亮度、颜色控制

可以控制灯光的亮度、控制灯光的颜色

### SetBrightness请求

设置亮度

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | SetBrightness |

#### payload信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| accessToken | String | IoT厂商接口访问access token | true |
| deviceId | String | 设备唯一ID | true |
| brightness | JSON Object | 亮度控制信息 | true |

brightness信息说明

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| value | String | 灯光亮度值，根据valueType不同，含义不同，//TODO，MAX，MIN等待定义 | true |
| valueType | String | value类型，有如下几种：int（整数类型），percent（百分比），//TODO，MAX，MIN等待定义 | true |

#### 请求示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"SetBrightness",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "accessToken":"xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx",
        "brightness":{
            "value":"100",
            "valueType":"int"
        }
    }
}
```

### SetBrightness响应

设置亮度响应

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | SetBrightnessResponse |

#### payload正常响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |

#### payload异常响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |
| errorCode | String | 错误码，详见//TODO | true |
| errorMessage | String | 错误信息描述，详见//TODO | true |

#### 正常响应示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"SetBrightnessResponse",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx"
    }
}
```

#### 异常响应示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"SetBrightnessResponse",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx",
        "errorCode":"USH.ERROR.DEVICE_NOT_FOUND",
        "errorMessage":"device not found"
    }
}
```

### IncreaseBrightness请求

增大亮度

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | IncreaseBrightness |

#### payload信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| accessToken | String | IoT厂商接口访问access token | true |
| deviceId | String | 设备唯一ID | true |
| deltaBrightness | JSON Object | 亮度变化信息，如用户输入不包含具体增大的数值，此字段为null，IoT厂商根据自身情况设置默认变化步长 | false |

deltaBrightness信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deltaValue | String | 变化的亮度值，根据deltaValueType不同，含义不同 | true |
| deltaValueType | String | deltaValue类型，有如下几种：int（整数类型），percent（百分比） | true |

#### 请求示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"IncreaseBrightness",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "accessToken":"xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx",
        "deltaBrightness":{
            "deltaValue":"100",
            "deltaValueType":"int"
        }
    }
}
```

### IncreaseBrightness响应

增大亮度响应

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | IncreaseBrightnessResponse |

#### payload正常响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |

#### payload异常响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |
| errorCode | String | 错误码，详见//TODO | true |
| errorMessage | String | 错误信息描述，详见//TODO | true |

#### 正常响应示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"IncreaseBrightnessResponse",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx"
    }
}
```

#### 异常响应示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"IncreaseBrightnessResponse",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx",
        "errorCode":"USH.ERROR.DEVICE_NOT_FOUND",
        "errorMessage":"device not found"
    }
}
```

### DecreaseBrightness请求

减小亮度

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | DecreaseBrightness |

#### payload信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| accessToken | String | IoT厂商接口访问access token | true |
| deviceId | String | 设备唯一ID | true |
| deltaBrightness | JSON Object | 亮度变化信息，如用户输入不包含具体增大的数值，此字段为null，IoT厂商根据自身情况设置默认变化步长 | false |

deltaBrightness信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deltaValue | String | 变化的亮度值，根据deltaValueType不同，含义不同 | true |
| deltaValueType | String | deltaValue类型，有如下几种：int（整数类型），percent（百分比） | true |

#### 请求示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"DecreaseBrightness",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "accessToken":"xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx",
        "deltaBrightness":{
            "deltaValue":"100",
            "deltaValueType":"int"
        }
    }
}
```

### DecreaseBrightness响应

减小亮度响应

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | DecreaseBrightnessResponse |

#### payload正常响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |

#### payload异常响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |
| errorCode | String | 错误码，详见//TODO | true |
| errorMessage | String | 错误信息描述，详见//TODO | true |

#### 正常响应示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"DecreaseBrightnessResponse",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx"
    }
}
```

#### 异常响应示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"DecreaseBrightnessResponse",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx",
        "errorCode":"USH.ERROR.DEVICE_NOT_FOUND",
        "errorMessage":"device not found"
    }
}
```

### SetColor请求

设置颜色

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | SetColor |

#### payload信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| accessToken | String | IoT厂商接口访问access token | true |
| deviceId | String | 设备唯一ID | true |
| color | JSON Object | 设置颜色信息 | true |

color信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| value | String | 具体颜色，支持的颜色见：[设备属性说明](she-bei-shu-xing-shuo-ming.md#yan-se-color) | true |

#### 请求示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"SetColor",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "accessToken":"xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx",
        "color":{
            "value":"RED"
        }
    }
}
```

### SetColor响应

设置颜色响应

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | SetColorResponse |

#### payload正常响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |

#### payload异常响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |
| errorCode | String | 错误码，详见//TODO | true |
| errorMessage | String | 错误信息描述，详见//TODO | true |

#### 正常响应示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"SetColorResponse",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx"
    }
}
```

#### 异常响应示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"SetColorResponse",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx",
        "errorCode":"USH.ERROR.DEVICE_NOT_FOUND",
        "errorMessage":"device not found"
    }
}
```

## 温度控制

升高或者降低设备的温度，也可以设定指定的温度。

### SetTemperature请求

设置指定温度

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | SetTemperature |

#### payload信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| accessToken | String | IoT厂商接口访问access token | true |
| deviceId | String | 设备唯一ID | true |
| temperature | JSON Object | 温度信息 | true |

temperature信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| value | String | 温度值，根据valueType不同，含义不同，//TODO，MAX，MIN等待定义 | true |
| valueType | String | value类型，有如下几种：int（整数类型），percent（百分比），//TODO，MAX，MIN等待定义 | true |

#### 请求示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"SetTemperature",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "accessToken":"xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx",
        "temperature":{
            "value":"20",
            "valueType":"int"
        }
    }
}
```

### SetTemperature响应

设置温度响应

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | SetTemperatureResponse |

#### payload正常响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |

#### payload异常响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |
| errorCode | String | 错误码，详见//TODO | true |
| errorMessage | String | 错误信息描述，详见//TODO | true |

#### 正常响应示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"SetTemperatureResponse",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx"
    }
}
```

#### 异常响应示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"SetTemperatureResponse",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx",
        "errorCode":"USH.ERROR.DEVICE_NOT_FOUND",
        "errorMessage":"device not found"
    }
}
```

### IncreaseTemperature请求

升高温度

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | IncreaseTemperature |

#### payload信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| accessToken | String | IoT厂商接口访问access token | true |
| deviceId | String | 设备唯一ID | true |
| deltaTemperature | JSON Object | 温度变化信息，如用户输入不包含具体增大的数值，此字段为null，IoT厂商根据自身情况设置默认变化步长 | false |

deltaTemperature信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deltaValue | String | 变化的温度值，根据deltaValueType不同，含义不同 | true |
| deltaValueType | String | deltaValue类型，有如下几种：int（整数类型），percent（百分比） | true |

#### 请求示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"IncreaseTemperature",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "accessToken":"xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx",
        "deltaTemperature":{
            "deltaValue":"5",
            "deltaValueType":"int"
        }
    }
}
```

### IncreaseTemperature响应

升高温度响应

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | IncreaseTemperatureResponse |

#### payload正常信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |

#### payload异常信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |
| errorCode | String | 错误码，详见//TODO | true |
| errorMessage | String | 错误信息描述，详见//TODO | true |

#### 正常响应示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"IncreaseTemperatureResponse",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx"
    }
}
```

#### 异常响应示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"IncreaseTemperatureResponse",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx",
        "errorCode":"USH.ERROR.DEVICE_NOT_FOUND",
        "errorMessage":"device not found"
    }
}
```

### DecreaseTemperature请求

降低温度

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | DecreaseTemperature |

#### payload信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| accessToken | String | IoT厂商接口访问access token | true |
| deviceId | String | 设备唯一ID | true |
| deltaTemperature | JSON Object | 温度变化信息，如用户输入不包含具体增大的数值，此字段为null，IoT厂商根据自身情况设置默认变化步长 | false |

deltaTemperature信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deltaValue | String | 变化的温度值，根据deltaValueType不同，含义不同 | true |
| deltaValueType | String | deltaValue类型，有如下几种：int（整数类型），percent（百分比） | true |

#### 请求示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"DecreaseTemperature",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "accessToken":"xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx",
        "deltaTemperature":{
            "deltaValue":"5",
            "deltaValueType":"int"
        }
    }
}
```

### DecreaseTemperature响应

降低温度响应

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | DecreaseTemperatureResponse |

#### payload正常信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |

#### payload异常信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |
| errorCode | String | 错误码，详见//TODO | true |
| errorMessage | String | 错误信息描述，详见//TODO | true |

#### 正常响应示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"DecreaseTemperatureResponse",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx"
    }
}
```

#### 异常响应示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"DecreaseTemperatureResponse",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx",
        "errorCode":"USH.ERROR.DEVICE_NOT_FOUND",
        "errorMessage":"device not found"
    }
}
```

## 模式控制

单设备模式或多设备联动模式的控制

### SetMode请求

模式设置

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | SetMode |

#### payload信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| accessToken | String | IoT厂商接口访问access token | true |
| deviceId | String | 设备唯一ID | true |
| mode | JSON Object | 模式信息 | true |

mode信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| value | String | 模式类型，支持的模式见[模式列表](she-bei-shu-xing-shuo-ming.md#mo-shi-mode) | true |

#### 请求示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"SetMode",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "accessToken":"xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx",
        "mode":{
            "value":"AUTO"
        }
    }
}
```

## 风速控制

用于控制设备风速

### SetWindSpeed请求

设置风速

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | SetWindSpeed |

#### payload信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| accessToken | String | IoT厂商接口访问access token | true |
| deviceId | String | 设备唯一ID | true |
| windSpeed | JSON Object | 风速信息 | true |

windSpeed信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| value | String | 风速值，根据valueType不同，含义不同，//TODO，HIGH，LOW等待定义 | true |
| valueType | String | value类型，有如下几种：int（整数类型），//TODO，HIGH，LOW等待定义 | true |

#### 请求示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"SetWindSpeed",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "accessToken":"xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx",
        "windSpeed":{
            "value":"10",
            "valueType":"int"
        }
    }
}
```

### SetWindSpeed响应

设置风速响应

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | SetWindSpeedResponse |

#### payload正常响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |

#### payload异常响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |
| errorCode | String | 错误码，详见//TODO | true |
| errorMessage | String | 错误信息描述，详见//TODO | true |

#### 正常响应示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"SetWindSpeedResponse",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx"
    }
}
```

#### 异常响应示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"SetWindSpeedResponse",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx",
        "errorCode":"USH.ERROR.DEVICE_NOT_FOUND",
        "errorMessage":"device not found"
    }
}
```

### IncreaseWindSpeed请求

增大风速

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | IncreaseWindSpeed |

#### payload信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| accessToken | String | IoT厂商接口访问access token | true |
| deviceId | String | 设备唯一ID | true |
| deltaWindSpeed | JSON Object | 风速变化信息，如用户输入不包含具体增大的数值，此字段为null，IoT厂商根据自身情况设置默认变化步长 | false |

deltaWindSpeed信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deltaValue | String | 变化的风速值，根据deltaValueType不同，含义不同 | true |
| deltaValueType | String | deltaValue类型，有如下几种：int（整数类型），percent（百分比） | true |

#### 请求示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"IncreaseWindSpeed",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "accessToken":"xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx",
        "deltaWindSpeed":{
            "deltaValue":"5",
            "deltaValueType":"int"
        }
    }
}
```

### IncreaseWindSpeed响应

增大风速响应

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | IncreaseWindSpeedResponse |

#### payload正常信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |

#### payload异常信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |
| errorCode | String | 错误码，详见//TODO | true |
| errorMessage | String | 错误信息描述，详见//TODO | true |

#### 正常响应示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"IncreaseWindSpeedResponse",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx"
    }
}
```

#### 异常响应示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"IncreaseWindSpeedResponse",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx",
        "errorCode":"USH.ERROR.DEVICE_NOT_FOUND",
        "errorMessage":"device not found"
    }
}
```

