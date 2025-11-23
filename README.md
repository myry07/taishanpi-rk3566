# taishanpi-rk3566

## sdk编译
sdk目录下创建dockerfile目录
```
vim dockerfile
```

dockerfile内容:  
https://wiki.lckfb.com/zh-hans/tspi-rk3566/sdk-compilation/docker-compiling-environment.html  

创建镜像
```
docker build -t my_docker_img .
```

查看镜像
```
docker images
```

创建容器  
```
docker run --privileged --mount type=bind,source=宿主容器同一目录 --name="容器id" -h lckfb -it 镜像id
```

查看可以运行的docker
```
docker ps -a
```

启动docker
```
docker start docker号
```

进入docker
```
docker attach docker号
```

## 运行

创建用户
```
sudo useradd -m myry
```

设置密码
```
sudo passwd 用户名
```

给管理员权限
```
sudo usermod -aG sudo myry
```


切换用户
```
su - myry
```

查看内存信息
```
lsblk
```



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
```


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
```


检查spi
```
ls /dev/spidev*
``` 


