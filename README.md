# legged_robot

<details>
    <summary> Install ros melodic </summary>
    
## Install [ROS melodic](http://wiki.ros.org/melodic/Installation/Ubuntu)

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
</details>


<details>
    <summary> Simulation </summary>
    
## Simulation

Make workspace
```
$ mkdir -p ~/legged_ws/src
```

*You have to install three packages!*
*Please open a new terminal for each package you install*

Install and build package 1
```
$ cd legged_ws/src
$ git clone https://github.com/unitreerobotics/unitree_legged_sdk.git
$ cd unitree_legged_sdk
$ mkdir build
$ cd build
$ cmake ..
$ make
```

Install and build package 2
```
$ cd legged_ws/src
$ git clone https://github.com/unitreerobotics/unitree_ros_to_real.git
```

Install and build package 3
```
$ cd legged_ws/src
$ git clone https://github.com/unitreerobotics/unitree_ros.git
$ sudo apt-get install ros-melodic-controller-interface  ros-melodic-gazebo-ros-control ros-melodic-joint-state-controller ros-melodic-effort-controllers ros-melodic-joint-trajectory-controller
```

open the new termial
```
$ cd legged_ws
$ catkin_make
```

Now start simulation!
</details>

## Real robot
