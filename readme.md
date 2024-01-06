# Autonomous Mobile Robot with RealSense D455 Camera for 3D Navigation

## Table of Contents
- [Description](#description)
- [Dependencies](#dependencies)
- [Robot Configuration]( #robot-configuration)
- [Usage](#usage)
- [Refrances](#refrances)

## Description

This project involves the creation of an autonomous mobile robot equipped with a RealSense camera for advanced 3D navigation capabilities. The robot is built using URDF  and incorporates a differential drive system. The entire simulation and implementation take place in Gazebo, a powerful robot simulation environment.

### URDF Model
The robot's physical characteristics and geometry are described using URDF(Unified Robot Description Format), allowing for a detailed and accurate representation in the simulation environment.

### SLAM and Mapping
The `gmapping` package is utilized for laser-based Simultaneous Localization and Mapping (SLAM), enabling the robot to generate a 2D occupancy grid map of its surroundings. This technology is crucial for the robot's understanding and mapping of the environment.

### Localization
The robot's localization within the mapped environment is achieved through the implementation of the Adaptive Monte Carlo Localization `AMCL` algorithm. This ensures precise tracking of the robot's position as it moves through the environment.

### Navigation Stack
To enable autonomous navigation, the Navigation Stack is employed. This sophisticated software stack facilitates the robot in autonomously navigating through its surroundings, avoiding obstacles, and reaching predefined target locations. The core of this stack is the `move_base` package, which integrates with the `A*` algorithm for path planning.

###  Voxel Layer
To enhance the perception of the environment, the project incorporates the use of a Spatio-Temporal Voxel Layer. This layer enables the representation of both spatial and temporal aspects of the environment in voxel form, providing a richer understanding of the surroundings.

## Dependencies
- ROS (Robot Operating System)
- Gazebo
- skid steer drive
- hokuyo lidar
- RealSense camera drivers
- gmapping package
- AMCL package
- Navigation Stack
- A* algorithm implementation
- Voxel Layer

## Robot Configuration

To use these robots, follow these installation steps:

1. Creating a workspace:

```
$ mkdir -p ~/robot_ws/src
$ cd ~/robot_ws/src 
```

2. Clone this repository to your local machine:

```bash
  git clone https://github.com/sherif1152/Autonomous_3DNavigation.git
```
3. Install Intel RealSense Gazebo ROS plugin and model
```bash
  git clone https://github.com/SyrianSpock/realsense_gazebo_plugin.git
```
4. Install Spatio-Temporal Voxel Layer
```
sudo apt-get install ros-noetic-spatio-temporal-voxel-layer
```
5. Build and Setup
```
$ cd ..
$ catkin_make
$ source devel/setup.bash 
```

## Usage
 1. Run robots in gazebo :
```bash
  roslaunch description_pkg robot.launch 
```
 2. Run Nav in RVIZ
```bash
  roslaunch navigtion_pkg navigation.launch 
```

## Refrances
- [realsense_gazebo_plugin](https://github.com/SyrianSpock/realsense_gazebo_plugin)

- [Voxel Layer](https://github.com/SteveMacenski/spatio_temporal_voxel_layer)
