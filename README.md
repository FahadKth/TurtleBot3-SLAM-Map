# TurtleBot3-SLAM-Map
**SLAM "Simultaneous Localization And Mapping"**

***
## TurtleBot3 "Burger"
![TurtleBot3_Burger-removebg-preview](https://user-images.githubusercontent.com/108236308/184157531-e6512432-c05c-4881-960f-ad26bcdbcb69.png)

***

### Step 1 : Install ROS 1 
> Type in the terminal
```
sudo apt update
```
```
sudo apt upgrade
```
```
wget https://raw.githubusercontent.com/ROBOTIS-GIT/robotis_tools/master/install_ros_noetic.sh
```
```
chmod 755 ./install_ros_noetic.sh 
```
```
bash ./install_ros_noetic.sh
```
### Step 2 : Install ROS 1 Packages
```
 sudo apt-get install ros-noetic-joy ros-noetic-teleop-twist-joy \
  ros-noetic-teleop-twist-keyboard ros-noetic-laser-proc \
  ros-noetic-rgbd-launch ros-noetic-depthimage-to-laserscan \
  ros-noetic-rosserial-arduino ros-noetic-rosserial-python \
  ros-noetic-rosserial-server ros-noetic-rosserial-client \
  ros-noetic-rosserial-msgs ros-noetic-amcl ros-noetic-map-server \
  ros-noetic-move-base ros-noetic-urdf ros-noetic-xacro \
  ros-noetic-compressed-image-transport ros-noetic-rqt* \
  ros-noetic-gmapping ros-noetic-navigation ros-noetic-interactive-markers
```
### Step 3 : Install TurtleBot3 Packages
```
sudo apt-get install ros-noetic-dynamixel-sdk
```
```
sudo apt-get install ros-noetic-turtlebot3-msgs
```
```
sudo apt-get install ros-noetic-turtlebot3
```

***

### Step 4 : install Simulation packages
```
cd ~/catkin_ws/src/
```
```
git clone -b noetic-devel https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git
```
```
cd ~/catkin_ws && catkin_make
```
### Step 5 
> open new terminal
```
source ~/catkin_ws/devel/setup.bash
```

***
### Launch the Simulation 
```
export TURTLEBOT3_MODEL=burger
```
```
roslaunch turtlebot3_gazebo turtlebot3_world.launch

```
### Step 6 : Run SLAM Node
> open new terminal
```
export TURTLEBOT3_MODEL=burger
```
```
roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping
```
### Step 7 : interact and control the robot
> open new terminal
```
export TURTLEBOT3_MODEL=burger
```
```
roslaunch turtlebot3_teleop turtlebot3_teleop_key.launch
```
>**You should be able to control the robot now by using W,A,S,D,X and SPACE to stop.**

***

<img width="960" alt="Screenshot 2022-08-11 154537 1285" src="https://user-images.githubusercontent.com/108236308/184168309-8d9fb095-c995-4d52-bcab-2bbbdb4af6a0.png">


<img width="960" alt="Screenshot 2022-08-11 154749 1284" src="https://user-images.githubusercontent.com/108236308/184168206-7d404afe-a05c-46f7-9b56-4725ff151c02.png">

> **Before moving the robot**

<img width="960" alt="Screenshot 2022-08-11 165828 1283" src="https://user-images.githubusercontent.com/108236308/184168413-7c837ad2-9a80-4ef7-8a5d-ae0e7f596840.png">

> **After moving the robot**

***
### To save the map
```
rosrun map_server map_saver -f ~/map
```

***
