# taishanpi-rk3566


远程ssh
```
ssh myry@192.168.1.88
```

反编译设备树
```
sudo dtc -I dtb -O dts -o base.dts /boot/dtb/tspi-rk3566-user-v10-linux.dtb
```

编辑设备树
```
sudo nano base.dts
```

编译设备树
```
sudo dtc -I dts -O dtb -o new.dtb base.dts
```

备份设备树并替换
```
sudo cp /boot/dtb/tspi-rk3566-user-v10-linux.dtb /boot/dtb/tspi-rk3566-user-v10-linux.dtb.bak
sudo cp new.dtb /boot/dtb/tspi-rk3566-user-v10-linux.dtb
``

串口检查
```
dmesg | grep tty
```

查看串口设备
```
ls /dev/ttyUSB*
ls /dev/ttyACM*
```

串口登陆泰山派
```
sudo picocom -b 1500000 /dev/ttyUSB0
```


检查i2c
```
ls /dev/i2c-*
``

