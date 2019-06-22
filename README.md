# Jetbot First Step

## 参考资料

https://github.com/open-ai-robot/awesome-nvidia-jetbot.git

## 硬件准备

## 软件准备

### 系统安装

https://github.com/dusty-nv/jetbot_ros.git

### 开发环境

开启 samba 服务

```shell
sudo apt-get install samba
```

编辑 /etc/samba/smb.conf

```conf
[homes]
comment = Home Directories
browseable = no
writable = yes
create mask = 0644
directory mask = 0755
valid users = %S
force create mode = 0644
force directory mode = 0755
```

添加密码

```shell
sudo smbpasswd -a $USER
```

重启服务

```shell
sudo service smbd restart
```

mac 打开远程目录 smb://192.168.31.117/qfl

## 电机驱动

### 驱动源码

python 电机驱动程序

https://github.com/adafruit/Adafruit-Motor-HAT-Python-Library.git

c++ 电机驱动程序

https://github.com/threebrooks/AdafruitStepperMotorHAT_CPP.git

### 运行 python 驱动

将用户添加到I2C组

```shell
sudo usermod -aG i2c $USER
```

安装依赖包

```shell
# pip should be installed
sudo apt-get install python-pip

# install Adafruit libraries
pip install Adafruit-MotorHAT
pip install Adafruit-SSD1306
```
