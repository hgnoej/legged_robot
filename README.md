# legged_robot

<details>
    <summary> Install ROS Melodic </summary>
    
## Install [ROS Melodic](http://wiki.ros.org/melodic/Installation/Ubuntu)

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

★★★ Connect IP ★★★

1. HIGHLEVEL control mode

Terminal 1
```
$ roslaunch unitree_legged_real real.launch ctrl_level:=highlevel
```

Terminal 2
```
$ rosrun unitree_legged_real example_walk
```

2. LOWLEVEL control mode

Terminal 1
```
$ roslaunch unitree_legged_real real.launch ctrl_level:=lowlevel
```

Terminal 2
```
$ rosrun unitree_legged_real example_position
```

---

You can also run the node state_sub to subscribe the feedback information from robot
```
$ rosrun unitree_legged_real state_sub
```

You can also run the launch file that enables you control robot via keyboard like you can do in turtlesim package
```
$ roslaunch unitree_legged_real keyboard_control.launch
```

And before you do the low-level control, please press L2+A to sit the robot down and then press L1+L2+start to make the robot into mode in which you can do joint-level control, finally make sure you hang the robot up before you run low-level control.
