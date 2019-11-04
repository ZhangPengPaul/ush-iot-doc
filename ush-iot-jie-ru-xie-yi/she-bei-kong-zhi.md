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

#### payload响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |

#### 响应示例

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

#### payload响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |

#### 响应示例

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

#### payload响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |

#### 响应示例

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
| value | String | 灯光亮度值，根据valueType不同，含义不同 | true |
| valueType | String | value类型，有如下几种：int（整数类型），percent（百分比），string（字符串类型） | true |

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

#### payload响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |

#### 响应示例

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

#### payload响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |

#### 响应示例

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

#### payload响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |

#### 响应示例

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

#### payload响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |

#### 响应示例

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
| value | String | 温度值，根据valueType不同，含义不同 | true |
| valueType | String | value类型，有如下几种：int（整数类型），percent（百分比），string（字符串类型） | true |

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

#### payload响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |

#### 响应示例

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

#### payload响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |

#### 响应示例

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

#### payload响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |

#### 响应示例

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

### SetMode响应

设置模式响应

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | SetModeResponse |

#### payload响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |

#### 响应示例

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
| value | String | 风速值，根据valueType不同，含义不同 | true |
| valueType | String | value类型，有如下几种：int（整数类型），string（字符串类型） | true |

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

#### payload响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |

#### 响应示例

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

#### payload响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |

#### 响应示例

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

### DecreaseWindSpeed请求

减小风速

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | DecreaseWindSpeed |

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
        "name":"DecreaseWindSpeed",
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

### DecreaseWindSpeed响应

减小风速响应

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | DecreaseWindSpeedResponse |

#### payload响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |

#### 响应示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"DecreaseWindSpeedResponse",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx"
    }
}
```

## 音量控制

用于控制设备音量

### SetVolume请求

设置音量

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | SetVolume |

#### payload信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| accessToken | String | IoT厂商接口访问access token | true |
| deviceId | String | 设备唯一ID | true |
| volume | JSON Object | 音量信息 | true |

volume信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| value | String | 音量值，根据valueType不同 | true |
| valueType | String | value类型，有如下几种：int（整数类型），string（字符串类型） | true |

#### 请求示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"SetVolume",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "accessToken":"xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx",
        "volum":{
            "value":"10",
            "valueType":"int"
        }
    }
}
```

### SetVolume响应

设置音量响应

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | SetVolumeResponse |

#### payload响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |

#### 响应示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"SetVolumeResponse",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx"
    }
}
```

### IncreaseVolume请求

增大音量

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | IncreaseVolume |

#### payload信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| accessToken | String | IoT厂商接口访问access token | true |
| deviceId | String | 设备唯一ID | true |
| deltaVolume | JSON Object | 音量变化信息，如用户输入不包含具体增大的数值，此字段为null，IoT厂商根据自身情况设置默认变化步长 | false |

deltaVolume信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deltaValue | String | 变化的音量值，根据deltaValueType不同，含义不同 | true |
| deltaValueType | String | deltaValue类型，有如下几种：int（整数类型），percent（百分比） | true |

#### 请求示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"IncreaseVolume",
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

### IncreaseVolume响应

增大音量响应

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | IncreaseVolumeResponse |

#### payload响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |

#### 响应示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"IncreaseVolumeResponse",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx"
    }
}
```

### DecreaseVolume请求

减小音量

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | DecreaseVolume |

#### payload信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| accessToken | String | IoT厂商接口访问access token | true |
| deviceId | String | 设备唯一ID | true |
| deltaVolume | JSON Object | 音量变化信息，如用户输入不包含具体增大的数值，此字段为null，IoT厂商根据自身情况设置默认变化步长 | false |

deltaVolume信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deltaValue | String | 变化的音量值，根据deltaValueType不同，含义不同 | true |
| deltaValueType | String | deltaValue类型，有如下几种：int（整数类型），percent（百分比） | true |

#### 请求示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"DecreaseVolume",
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

### DecreaseVolume响应

减小音量响应

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | DecreaseVolumeResponse |

#### payload响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |

#### 响应示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"DecreaseVolumeResponse",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx"
    }
}
```

## 频道控制

用于控制设备频道

### SetChannel请求

设置频道

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | SetChannel |

#### payload信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| accessToken | String | IoT厂商接口访问access token | true |
| deviceId | String | 设备唯一ID | true |
| channel | JSON Object | 频道信息 | true |

channel信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| value | String | 音量值，根据valueType不同，含义不同 | true |
| valueType | String | value类型，有如下几种：int（整数类型），string（字符串类型，如：频道名） | true |

#### 请求示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"SetChannel",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "accessToken":"xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx",
        "channel":{
            "value":"10",
            "valueType":"int"
        }
    }
}
```

### SetChannel响应

设置频道响应

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | SetChannelResponse |

#### payload响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |

#### 响应示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"SetChannelResponse",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx"
    }
}
```

### IncreaseChannel请求

增大频道

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | IncreaseChannel |

#### payload信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| accessToken | String | IoT厂商接口访问access token | true |
| deviceId | String | 设备唯一ID | true |
| deltaChannel | JSON Object | 频道变化信息，如用户输入不包含具体增大的数值，此字段为null，IoT厂商根据自身情况设置默认变化步长 | false |

deltaChannel信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deltaValue | String | 变化的频道值，根据deltaValueType不同，含义不同 | true |
| deltaValueType | String | deltaValue类型，有如下几种：int（整数类型） | true |

#### 请求示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"IncreaseChannel",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "accessToken":"xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx",
        "deltaChannel":{
            "deltaValue":"5",
            "deltaValueType":"int"
        }
    }
}
```

### IncreaseChannel响应

增大频道响应

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | IncreaseChannelResponse |

#### payload响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |

#### 响应示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"IncreaseChannelResponse",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx"
    }
}
```

### DecreaseChannel请求

减小频道

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | DecreaseChannel |

#### payload信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| accessToken | String | IoT厂商接口访问access token | true |
| deviceId | String | 设备唯一ID | true |
| deltaChannel | JSON Object | 频道变化信息，如用户输入不包含具体增大的数值，此字段为null，IoT厂商根据自身情况设置默认变化步长 | false |

deltaChannel信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deltaValue | String | 变化的频道值，根据deltaValueType不同，含义不同 | true |
| deltaValueType | String | deltaValue类型，有如下几种：int（整数类型），percent（百分比） | true |

#### 请求示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"DecreaseChannel",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "accessToken":"xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx",
        "deltaChannel":{
            "deltaValue":"5",
            "deltaValueType":"int"
        }
    }
}
```

### DecreaseVolume响应

减小音量响应

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | DecreaseChannelResponse |

#### payload响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |

#### 响应示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"DecreaseChannelResponse",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx"
    }
}
```

## 异步模式

异步请求参数同上方协议文档，响应结果不含控制结果，仅表示IoT云接收到控制请求

### 响应结果

#### header信息

同上方控制协议中的header信息

#### payload响应信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |
| async | boolean | 是否异步模式 | true |

#### 响应示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"DecreaseChannelResponse",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx",
        "async":true
    }
}
```

### 控制结果上报API

异步模式下，IoT云完成设备控制后，需通过此接口上报控制结果

#### Http Method

POST

#### URL

http://gw-std.hivoice.cn/v2/iot/control-report

#### 请求参数

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |
| controlResult | boolean | 控制是否成功 | true |
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
    "deviceId":"xxxxxxxxxxxxxxx",
    "controlResult":true,
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

## 错误响应信息

异常错误响应信息，错误情况下返回此响应内容

### 错误响应

#### header信息

| 参数名 | 参数值 |
| :--- | :--- |
| namespace | USH.IoT.Device.Control |
| name | ErrorResponse |

#### payload信息

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| deviceId | String | 设备唯一ID | true |
| errorCode | String | 错误码，详见：[错误码](she-bei-kong-zhi.md#cuo-wu-ma) | true |
| errorMessage | String | 错误信息，详见：[错误码](she-bei-kong-zhi.md#cuo-wu-ma) | true |

#### 响应示例

```javascript
{
    "header":{
        "namespace":"USH.IoT.Device.Control",
        "name":"DecreaseChannelResponse",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":"1"
    },
    "payload":{
        "deviceId":"xxxxxxxxxxxxxxxxxxxxxx",
        "errorCode":"DEVICE_NOT_FOUND",
        "errorMessage":"device not exists"
    }
}
```

### 错误码

| errorCode | errorMessage | 说明 |
| :--- | :--- | :--- |
| ILLEGAL\_CONTROL\_ORDER | illegal device order | 非法的控制命令，命令不存在或设备不支持此功能 |
| ILLEGAL\_PARAMS | illegal  params | 请求参数非法 |
| DEVICE\_NOT\_FOUND | device not found | IoT设备不存在 |
| DEVICE\_OFFLINE | device off line | 设备不在线 |
| ILLEGAL\_ACCESS\_TOKEN | illegal access token | access token失效或不存在 |
| SERVICE\_ERROR | 具体错误信息 | IoT云服务异常信息 |

