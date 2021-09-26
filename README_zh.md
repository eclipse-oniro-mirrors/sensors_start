# Sensor组件<a name="ZH-CN_TOPIC_0000001148682248"></a>

-   [简介](#section11660541593)
-   [目录](#section44981327519)
-   [使用](#section1581412211528)
-   [相关仓](#section96071132185310)

## 简介<a name="section11660541593"></a>
启动sensor、马达等小器件服务。

## 目录<a name="section44981327519"></a>

sensor导入模块的示例代码如下：

```
/base/sensors/start
├── etc
    └── init                # 放置hsensor进程的启动文件
```

## 使用<a name="section1581412211528"></a>
该仓放置了hsensor进程的启动文件，hsensor进程会拉起sensor、马达等小器件服务。sensor、马达等小器件服务的启动配置文件分别在[sensors\_sensor](https://gitee.com/openharmony/sensors_sensor)和[sensors\_miscdevice](https://gitee.com/openharmony/sensors_miscdevice)部件仓的sa_profile目录下，因此该仓不能单独存在，需要搭配[sensors\_sensor](https://gitee.com/openharmony/sensors_sensor)或者[sensors\_miscdevice](https://gitee.com/openharmony/sensors_miscdevice)部件仓使用。否则，hsensor进程将不会拉起任何服务。

## 相关仓<a name="section96071132185310"></a>

泛Sensor服务子系统

[sensors\_sensor](https://gitee.com/openharmony/sensors_sensor)

[sensors\_miscdevice](https://gitee.com/openharmony/sensors_miscdevice)

**sensors\_start**

