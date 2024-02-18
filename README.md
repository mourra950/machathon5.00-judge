## Description
### The Machathon 5.00 repository provides all the required tools and utilities for the Machathon 5.00 simulation phase

## Requirements
* ROS2 installation using any of the following options
  * Using ROS2 humble(Ubuntu 22.04) installation: 
      * [Install ROS2 humble](https://docs.ros.org/en/humble/Installation/Ubuntu-Install-Debians.html)
  * Using ROS2 foxy(Ubuntu 20.04) installation:
      * [Install ROS2 foxy](https://docs.ros.org/en/foxy/Installation/Ubuntu-Install-Debians.html)
* Gazebo and ROS-Gazebo packages Installation
```bash
$ sudo apt update
$ sudo apt -y install gazebo
$ sudo apt install ros-humble-gazebo-ros-pkgs
$ sudo apt install ros-humble-xacro
```
## Setting up the environment
#### 1. Create a workspace
 ```bash
$ mkdir workspace_name
```
#### 2. Create src folder inside workspace
 ```bash
$ cd workspace_name
$ mkdir src
```
#### 3. Clone the repository inside the src folder
 ```bash
# cd src
$ git clone https://github.com/Apolo151/machathon5.00.git
```
#### 4. Build the workspace
```bash
$ cd ..
$ colcon build --symlink-install
```
## To run the scene 
#### 1. Open Gazebo Scene
```bash
$ cd workspace_name
$ source install/setup.bash
$ source ~/.bashrc
$ ros2 launch car_demo demo.launch.py
```
#### 2. Run ROS2 python code to control the car via the keyboard
1. open another terminal and run the following commands
 ```bash
$ sudo su
$ source ~/.bashrc
$ source install/setup.bash
$ ros2 run car_demo prius_teleop_keyboard.py
```
## Simulation Scene Description
* You are provided with a gazebo world that contains the competition vehicle and the track.
* The car navigates it in one direction, followed by navigating it in the opposite direction. The time taken to complete each run, known as the lap time, is recorded.
* After completing the track in both directions, the lap time for both runs is sent via HTTP request to the leaderboard.
* The starting navigation direction of the track for the first run, the car is moving clockwise, and for the second run, the car is moving anti-clockwise along the full track.
