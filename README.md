# Jetbot First Step

## 参考资料

https://github.com/open-ai-robot/awesome-nvidia-jetbot.git

## 硬件准备

## 系统安装

https://github.com/dusty-nv/jetbot_ros.git

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
