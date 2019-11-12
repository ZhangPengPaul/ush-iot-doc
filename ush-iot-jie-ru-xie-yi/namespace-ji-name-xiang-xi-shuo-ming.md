---
description: namespace及name详细说明
---

# namespace及name详细说明

## name信息说明

### 设备发现（对应UniOS.IoT.Device.Discovery）

| name | 说明 |
| :--- | :--- |
| [DiscoveryDevices](she-bei-fa-xian.md#she-bei-fa-xian) | 设备发现，获取设备列表 |

### 设备控制（对应USH.IoT.Device.Control）

| name | 说明 |
| :--- | :--- |
| [TurnOn](she-bei-kong-zhi.md#turnon-qing-qiu) | 打开 |
| [TurnOff](she-bei-kong-zhi.md#turnoff-qing-qiu) | 关闭 |
| [Pause](she-bei-kong-zhi.md#pause-qing-qiu) | 停止 |
| [SetBrightness](she-bei-kong-zhi.md#setbrightness-qing-qiu) | 设置亮度 |
| [IncreaseBrightness](she-bei-kong-zhi.md#increasebrightness-qing-qiu) | 增大亮度 |
| [DecreaseBrightness](she-bei-kong-zhi.md#decreasebrightness-qing-qiu) | 调小亮度 |
| [SetColor](she-bei-kong-zhi.md#setcolor-qing-qiu) | 设置颜色 |
| [SetTemperature](she-bei-kong-zhi.md#settemperature-qing-qiu) | 设置温度 |
| [IncreaseTemperature](she-bei-kong-zhi.md#increasetemperature-qing-qiu) | 调高温度 |
| [DecreaseTemperature](she-bei-kong-zhi.md#decreasetemperature-qing-qiu) | 调低温度 |
| [SetMode](she-bei-kong-zhi.md#setmode-qing-qiu) | 设置模式 |
| [SetWindSpeed](she-bei-kong-zhi.md#setwindspeed-qing-qiu) | 设置风速 |
| [IncreaseWindSpeed](she-bei-kong-zhi.md#increasewindspeed-qing-qiu) | 调大风速 |
| [DecreaseWindSpeed](she-bei-kong-zhi.md#decreasewindspeed-qing-qiu) | 调小风速 |
| [SetVolume](she-bei-kong-zhi.md#setvolume-qing-qiu) | 设置音量 |
| [IncreaseVolume](she-bei-kong-zhi.md#increasevolume-qing-qiu) | 调大音量 |
| [DecreaseVolume](she-bei-kong-zhi.md#decreasevolume-qing-qiu) | 调小音量 |
| [SetChannel](she-bei-kong-zhi.md#setchannel-qing-qiu) | 设置频道 |
| [IncreaseChannel](she-bei-kong-zhi.md#increasechannel-qing-qiu) | 下一个频道 |
| [DecreaseChannel](she-bei-kong-zhi.md#decreasechannel-qing-qiu) | 上一个频道 |

### 设备属性及状态查询（对应UniOS.IoT.Device.Query）

| name | 说明 | 返回结果说明 |
| :--- | :--- | :--- |
| All | 查询设备所有支持的属性 | 详见各个属性说明 |
| Color | 查询颜色 | 详见[Color](she-bei-shu-xing-shuo-ming.md#yan-se-color) |
| PowerState | 查询电源开关 | 详见[PowerState](she-bei-shu-xing-shuo-ming.md#dian-yuan-kai-guan-powerstate) |
| Temperature | 查询温度 | 数值 |
| WindSpeed | 查询风速 | 详见[WindSpeed](she-bei-shu-xing-shuo-ming.md#feng-su-windspeed) |
| Brightness | 查询亮度 | 数值 |
| Mode | 查询模式 | 详见[Mode](she-bei-shu-xing-shuo-ming.md#mo-shi-mode) |
| Direction | 查询方向 | 详见[Direction](she-bei-shu-xing-shuo-ming.md#fang-xiang-direction) |

