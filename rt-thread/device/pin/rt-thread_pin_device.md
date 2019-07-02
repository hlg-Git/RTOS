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


