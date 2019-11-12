---
description: 协议简介
---

# 协议简介

## 协议概述

协议总体分为两个部分：`header`及`payload`

### 协议总体结构

```javascript
{
    "header":{

    },
    "payload":{

    }
}
```

#### header信息

`header`信息包含命名空间，指令名称，请求标识符和payload版本信息

示例：

```javascript
{
    "header":{
        "namespace":"UniOS.IoT.Device.Control",
        "name":"TurnOn",
        "requestId":"xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
        "payloadVersion":1
    }
}
```

header参数协议说明

| 参数名 | 参数类型 | 参数说明 | 是否必填 |
| :--- | :--- | :--- | :--- |
| namespace | String | 请求命名空间，详见下方_**namespace参数说明**_ | true |
| name | String | 指令名称，详见[namespace及name详细说明](namespace-ji-name-xiang-xi-shuo-ming.md) | true |
| requestId | String | 请求唯一ID，用户跟踪请求，使用UUID | true |
| payloadVersion | int | payload版本号，当前默认为1 | true |

namespace参数说明

| namespace | 说明 |
| :--- | :--- |
| UniOS.IoT.Device.Control | 设备控制 |
| UniOS.IoT.Device.Discovery | 设备发现 |
| UniOS.IoT.Device.Query | 设备属性、状态查询 |

name参数说明

详见[namespace及name详细说明](namespace-ji-name-xiang-xi-shuo-ming.md)

#### payload信息

payload根据namespace分为设备发现、设备控制、设备属性查询三类，指令不同payload内容不同，详见[设备发现](she-bei-fa-xian.md)，[设备控制](she-bei-kong-zhi.md)，[设备属性及状态查询](she-bei-shu-xing-ji-zhuang-tai-cha-xun.md)。

