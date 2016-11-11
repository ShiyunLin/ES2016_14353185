# 安装ros

（根据教程http://wiki.ros.org/jade/Installation/Ubuntu安装）

## 1. 添加 sources.list

```
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
```



## 2.添加 keys

```
sudo apt-key adv --keyserver hkp://pool.sks-keyservers.net --recv-key 0xB01FA116
```



## 3.安装桌面完整版

```
sudo apt-get install ros-jade-desktop-full
```



## 4.初始化 rosdep

```
echo "source /opt/ros/jade/setup.bash" >> ~/.bashrc
source ~/.bashrc
```



## 5.安装 rosinstall

```
sudo apt-get install python-rosinstall
```



## 6.检查安装成功

```
roscore
```



### 安装成功截图

 ![屏幕快照 2016-11-10 下午10.48.38](/Users/shiyunlin/Desktop/ros/屏幕快照 2016-11-10 下午10.48.38.png)

