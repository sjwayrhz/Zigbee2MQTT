# 自定义的文件

 还有就是推送到gateway的地址不一样，改在flow.json



## docker-compose.yml

不同的zigbee设备，ID可能不一样，通过以下命令来确定ID.

```
ls /dev/serial/by-id/
usb-1a86_USB_Serial-if00-port0
```

然后把ID写入docker-compose.yml

```
devices:
  - /dev/serial/by-id/usb-1a86_USB_Serial-if00-port0:/dev/ttyUSB0
```

这样，USB设备就对应上了。

## flow.json

flow.json是导入到Node-RED的dashboard里面的，其中

```
http://192.168.157.131:9091/metrics/job/zigbee/instance/gateway_01
```

这个URL需要根据实际来修改，gateway_01例如可以改为25-ups，也就是25楼的UPS室的意思。