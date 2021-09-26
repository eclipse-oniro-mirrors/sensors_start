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
该仓放置了hsensors进程的启动文件，用来启动sensor和马达等小器件服务。sensor和马达等小器件服务共享hsensors进程。<br>
sensor和马达等小器件的服务代码分别在[sensors\_sensor](https://gitee.com/openharmony/sensors_sensor)和[sensors\_miscdevice](https://gitee.com/openharmony/sensors_miscdevice)部件仓，产品在选择部件时根据需要可能选择其中一个部件或者两个部件都选择。这就需要将hsensors进程的启动文件放在单独的启动部件仓，由这两个部件共享，这样任何一个部件仓搭配启动部件就可以启动hsensors进程，防止重复启动进程。<br>
sensor和马达等小器件的服务启动配置文件分别在[sensors\_sensor](https://gitee.com/openharmony/sensors_sensor)和[sensors\_miscdevice](https://gitee.com/openharmony/sensors_miscdevice)部件仓的sa_profile目录下，会编译生成system/profile/hsensors.xml文件。其中3601和3602分别为sensor和马达服务。若仅编译[sensors\_sensor](https://gitee.com/openharmony/sensors_sensor)仓代码，hsensors.xml文件中则仅包含3601服务的配置项。启动hsensors进程时会加载hsensors.xml文件启动服务。<br>
```
<?xml version="1.0" encoding="utf-8"?>
<info>
    <process>hsensors</process>
    <loadlibs>
        <libpath>libmiscdevice_service.z.so</libpath>
        <libpath>libsensor_service.z.so</libpath>
    </loadlibs>
    <systemability>
        <name>3602</name>
        <libpath>libmiscdevice_service.z.so</libpath>
        <run-on-create>true</run-on-create>
        <distributed>false</distributed>
        <dump-level>1</dump-level>
    </systemability>
    <systemability>
        <name>3601</name>
        <libpath>libsensor_service.z.so</libpath>
        <run-on-create>true</run-on-create>
        <distributed>false</distributed>
        <dump-level>1</dump-level>
    </systemability>
</info>
```

## 相关仓<a name="section96071132185310"></a>

泛Sensor服务子系统

[sensors\_sensor](https://gitee.com/openharmony/sensors_sensor)

[sensors\_miscdevice](https://gitee.com/openharmony/sensors_miscdevice)

**sensors\_start**

