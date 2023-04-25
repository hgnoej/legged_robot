# legged_robot

## Install (ROS melodic)[http://wiki.ros.org/melodic/Installation/Ubuntu]

Setup your sources.list
```
$ sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
```

Set up your keys
```
$ sudo apt install curl
$ curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
```

Installation
```
$ sudo apt update
$ sudo apt install ros-melodic-desktop-full
```

Environment setup
```
$ echo "source /opt/ros/melodic/setup.bash" >> ~/.bashrc
$ source ~/.bashrc
```

Dependencies for building packages
```
$ sudo apt install python-rosdep python-rosinstall python-rosinstall-generator python-wstool build-essential
$ sudo apt install python-rosdep
$ rosdep update
```
