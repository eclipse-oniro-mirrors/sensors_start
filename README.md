# Sensor<a name="EN-US_TOPIC_0000001148682248"></a>

-   [Introduction](#section11660541593)
-   [Directory Structure](#section44981327519)
-   [Usage](#section1581412211528)
-   [Repositories Involved](#section96071132185310)

## Introduction<a name="section11660541593"></a>

Start sensor, vibrator and other small device services.

## Directory Structure<a name="section44981327519"></a>

The sample code for importing the start module is as follows:

```
/base/sensors/start
├── etc
    └── init                # Place the service startup file
```

## Usage<a name="section1581412211528"></a>
The warehouse places the start file of the hsensor process, which pulls up the small device services such as sensor and vibrator. Start-up profiles for sensors and small device services such as vibrator, etc. are in [sensors\_sensor](https://gitee.com/openharmony/sensors_sensor)  and [sensors\_miscdevice](https://gitee.com/openharmony/sensors_miscdevice) parts compartments, respectively, so the silos cannot exist alone and need to be used with [sensors\_sensor](https://gitee.com/openharmony/sensors_sensor) or [sensors\_miscdevice](https://gitee.com/openharmony/sensors_miscdevice). Otherwise, the hsensor process will not pull up any services.

### Available APIs<a name="section15684191115524"></a>

## Repositories Involved<a name="section96071132185310"></a>

Pan-sensor subsystem

[sensors\_sensor](https://gitee.com/openharmony/sensors_sensor)

[sensors\_miscdevice](https://gitee.com/openharmony/sensors_miscdevice)

**sensors\_start**
