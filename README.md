# Jetbot First Step

## 硬件准备

## 软件准备

### 系统安装

参考 https://developer.nvidia.com/embedded/learn/get-started-jetson-nano-devkit

[固件下载链接](https://developer.nvidia.com/embedded/dlc/jetson-nano-dev-kit-sd-card-image) 本文档开发板基于此固件

另可参考 https://github.com/dusty-nv/jetbot_ros.git

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

### 运行 python 程序

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

下载测试程序

```shell
mkdir ~/tmp
cd ~/tmp
wget https://raw.githubusercontent.com/felixqin/jetbot_first_step/master/motor/stepper_test.py
```

jetbot_ros 的电机控制代码: https://github.com/dusty-nv/jetbot_ros/blob/master/scripts/jetbot_motors.py

运行电机测试程序

```shell
cd ~/tmp
python stepper_test.py
```

如果一切顺利，此时电机可以转动！

运行OLED测试程序

<待补充>

### C++ 程序驱动电机

<待补充>

## 参考资料

- https://github.com/open-ai-robot/awesome-nvidia-jetbot.git
