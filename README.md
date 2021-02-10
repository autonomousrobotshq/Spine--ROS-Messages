# Spine--ROS-Messages
[![build](https://github.com/autonomousrobotshq/Spine--ROS-Messages/workflows/Build/badge.svg)](https://github.com/autonomousrobotshq/Spine--ROS-Messages/actions?workflow=Build)
## All ROS packages containing .msg files for use between Spine <--> Brain

### Quickstart

* Make sure you have git submodules installed as dependencies:

    git submodule init && git submodule update --recursive

* Get [ROS-Docker](https://github.com/autonomousrobotshq/ROS-Docker.git)
* To develop: [path-to-ROS-Docker]/ros-docker.sh -r package [path to this repo] bash
* To compile: [path-to-ROS-Docker]/ros-docker.sh -r package [path to this repo] catkin_make
* To compile cleanly (verify CMakeLists.txt): [path-to-ROS-Docker]/ros-docker.sh -c -r package [path to this repo] catkin_make

### Features
* Contains submodules of all relevant ROS packages for connecting an Arduino to ROS
* Contains 'spine_msg' folder which contains all message files to communicate between Spine <--> Brain over ROS
