# Programming a Real Self-Driving Car:
## System Integration Project

[image1]: ./imgs/Carla.png "Image 1"   
[image2]: ./imgs/project-rosgraph.png "Image 2"   

This is the project repo of team Laters for the final project of the Udacity Self-Driving Car Nanodegree: Programming a Real Self-Driving Car. 

The goal of the project is to fully implement with ROS the main modules of an autonomous vehicle: Perception, Planning and Control, which will be tested on Udacity´s Self Driving Car _´Carla´_ around a test track using waypoint navigation. 

For validation the code was tested using a simulator where the car drives around a highway test track with traffic lights.

## Carla: The Test Car
![alt text][image1]

The project will be evaluated on Carla, an autonomous Lincoln MKZ, at Udacity´s test site in Palo Alto, California. The operating system Carla runs on is Ubuntu Linux. 

Udacity Self-Driving Car Harware Specs:
* 31.4 GiB Memory
* Intel Core i7-6700K CPU @ 4 GHz x 8
* TITAN X Graphics
* 64-bit OS

## The Team: Laters

|           | Name                     |            GitHub                         |
| --------- | -------------------------| :----------------------------------------:|
| Team Lead | Andrii Cherniak          |            https://github.com/d2macster   |
|           | Tharatch Sirinukulwattana|            https://github.com/TharatchSiri|
|           | Melanie Plaza            |            https://github.com/mplaza      |
|           | Alexander Epifanov       |                                           |
|           | Igor Molina              |            https://github.com/igolas0     |

## Project Overview

![alt text][image2]

The submitted code is implemented in ROS. For this project we mainly use __rospy__, which is a pure Python client library for ROS and enables Python programmers to interface with ROS Topics, Services and Parameters.


### Native Installation

* Be sure that your workstation is running Ubuntu 16.04 Xenial Xerus or Ubuntu 14.04 Trusty Tahir. [Ubuntu downloads can be found here](https://www.ubuntu.com/download/desktop).
* If using a Virtual Machine to install Ubuntu, use the following configuration as minimum:
  * 2 CPU
  * 2 GB system memory
  * 25 GB of free hard drive space

  The Udacity provided virtual machine has ROS and Dataspeed DBW already installed, so you can skip the next two steps if you are using this.

* Follow these instructions to install ROS
  * [ROS Kinetic](http://wiki.ros.org/kinetic/Installation/Ubuntu) if you have Ubuntu 16.04.
  * [ROS Indigo](http://wiki.ros.org/indigo/Installation/Ubuntu) if you have Ubuntu 14.04.
* [Dataspeed DBW](https://bitbucket.org/DataspeedInc/dbw_mkz_ros)
  * Use this option to install the SDK on a workstation that already has ROS installed: [One Line SDK Install (binary)](https://bitbucket.org/DataspeedInc/dbw_mkz_ros/src/81e63fcc335d7b64139d7482017d6a97b405e250/ROS_SETUP.md?fileviewer=file-view-default)
* Download the [Udacity Simulator](https://github.com/udacity/CarND-Capstone/releases/tag/v1.2).

### Docker Installation
[Install Docker](https://docs.docker.com/engine/installation/)

Build the docker container
```bash
docker build . -t capstone
```

Run the docker file
```bash
docker run -p 4567:4567 -v $PWD:/capstone -v /tmp/log:/root/.ros/ --rm -it capstone
```

### Usage

1. Clone the project repository
```bash
git clone https://github.com/udacity/CarND-Capstone.git
```

2. Install python dependencies
```bash
cd CarND-Capstone
pip install -r requirements.txt
```
3. Make and run styx
```bash
cd ros
catkin_make
source devel/setup.sh
roslaunch launch/styx.launch
```
4. Run the simulator

### Real world testing
1. Download [training bag](https://drive.google.com/file/d/0B2_h37bMVw3iYkdJTlRSUlJIamM/view?usp=sharing) that was recorded on the Udacity self-driving car (a bag demonstraing the correct predictions in autonomous mode can be found [here](https://drive.google.com/open?id=0B2_h37bMVw3iT0ZEdlF4N01QbHc))
2. Unzip the file
```bash
unzip traffic_light_bag_files.zip
```
3. Play the bag file
```bash
rosbag play -l traffic_light_bag_files/loop_with_traffic_light.bag
```
4. Launch your project in site mode
```bash
cd CarND-Capstone/ros
roslaunch launch/site.launch
```
5. Confirm that traffic light detection works on real life images
