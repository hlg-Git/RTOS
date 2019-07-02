# RT-THREAD PIN设备应用

rt-thread version：4.0.1
硬件平台：STM32F4IGT6

## PIN设备的操作方法
应用程序通过RT-Thred提供的pin设备管理接口来操作GPIO，函数接口如下表:
<center><font face="黑体">表1.pin设备管理接口API</font></center>

|      方法名称       |       方法描述       |
| :-----------------: | :------------------: |
|    rt_pin_mode()    |     设置引脚模式     |
|   rt_pin_write()    |     设置引脚电平     |
|    rt_pin_read()    |     读取引脚电平     |
| rt_pin_attach_irq() | 绑定引脚中断回调函数 |
| rt_pin_detach_irq() | 脱离引脚中断回调函数 |
| rt_pin_irq_enable() |     使能引脚中断     |

### 1.设置引脚模式
```c
void rt_pin_mode(rt_base_t pin, rt_base_t mode);
```
<center><font face="黑体">表2.rt_pin_mode()的输入参数与返回值</font></center>

| 参数  |     描述     |
| :---: | :----------: |
|  pin  |   引脚编号   |
| mode  | 引脚工作模式 |
| 返回  |     描述     |
|  无   |      无      |

#### 引脚编号获取
引脚编号是由rt-thread的pin设备管理驱动程序定义的，并不是芯片的引脚号。有2种方式可以获取引脚编号：使用宏定义`GET_PIN(port, pin)`或者查看PIN 驱动文件`drv_gpio.c`。
使用宏定义比较方便。比如要获取ledR的引脚编号，硬件图如`图1.led原理图`：
![led_pin](https://github.com/hlg-Git/RTOS/blob/master/rt-thread/device/pin/picture/led_pin.png?raw=true#pic_ceter)
<center><font face="黑体">图1.led原理图</font></center>
代码如下：
```c
#define LEDR_PIN    GET_PIN(H, 10)
```

