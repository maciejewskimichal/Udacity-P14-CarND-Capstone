# CarND-Capstone

[Self-Driving Car Engineer Nanodegree Program Term 3 Project 14](https://eu.udacity.com/course/self-driving-car-engineer-nanodegree--nd013)

This project is submitted by one person as individual and run only on simulation.

![Running demo](https://github.com/maciejewskimichal/Udacity-P14-CarND-Capstone/blob/master/final_video.gif)

Full video:
https://github.com/maciejewskimichal/Udacity-P14-CarND-Capstone/blob/master/final_video.mp4


### For this demonstration
* Simulator was running on Windows 10
* ROS was running on Udacity VM with Ubuntu 16.04 created inside Oracle VM VirtualBox
* Video was captured by OBS Studio
* Parameters were tweaked to make possible to run such system on: 
  * Laptop: Dell Precision 5510 
  * CPU: Xeon 8 core E3-1505M 2.8 GHz
  * GPU: NVIDIA Quadro M1000M
* For running full speed demo one need to use fully installed Ubuntu system
* I managed to compile the projects inside Windows 10 Ubuntu 18.04 subsystem with newer ROS melodic subsystem, for this:
  * ROS melodic had to be installed
  * dbw_mkz_msgs module has to be installed, following advice from [link](https://github.com/Praveenraj49/CarND-Capstone/blob/master/README.md) following commands were set:
  
```sh 
sudo apt-get update
sudo apt-get install -y ros-melodic-dbw-mkz-msgs
cd /CarND-Capstone/ros
rosdep install --from-paths src --ignore-src --rosdistro=melodic -y
```
  * even after all this setup still Ubuntu 18.04 running ROS code could not see simulator as it was somehow blocked by firewall?
  * It was looking like ROS running in Ubuntu subsystem was slower from VM one
  * for this reason final test were run on VM

# Project Description

This is the project repo for the final project of the Udacity Self-Driving Car Nanodegree: Programming a Real Self-Driving Car. For more information about the project, see the project introduction [here](https://classroom.udacity.com/nanodegrees/nd013/parts/6047fe34-d93c-4f50-8336-b70ef10cb4b2/modules/e1a23b06-329a-4684-a717-ad476f0d8dff/lessons/462c933d-9f24-42d3-8bdc-a08a5fc866e4/concepts/5ab4b122-83e6-436d-850f-9f4d26627fd9).


Please use **one** of the two installation options, either native **or** docker installation.

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
* Download the [Udacity Simulator](https://github.com/udacity/CarND-Capstone/releases).

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

### Port Forwarding
To set up port forwarding, please refer to the "uWebSocketIO Starter Guide" found in the classroom (see Extended Kalman Filter Project lesson).

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
1. Download [training bag](https://s3-us-west-1.amazonaws.com/udacity-selfdrivingcar/traffic_light_bag_file.zip) that was recorded on the Udacity self-driving car.
2. Unzip the file
```bash
unzip traffic_light_bag_file.zip
```
3. Play the bag file
```bash
rosbag play -l traffic_light_bag_file/traffic_light_training.bag
```
4. Launch your project in site mode
```bash
cd CarND-Capstone/ros
roslaunch launch/site.launch
```
5. Confirm that traffic light detection works on real life images

### Other library/driver information
Outside of `requirements.txt`, here is information on other driver/library versions used in the simulator and Carla:

Specific to these libraries, the simulator grader and Carla use the following:

|        | Simulator | Carla  |
| :-----------: |:-------------:| :-----:|
| Nvidia driver | 384.130 | 384.130 |
| CUDA | 8.0.61 | 8.0.61 |
| cuDNN | 6.0.21 | 6.0.21 |
| TensorRT | N/A | N/A |
| OpenCV | 3.2.0-dev | 2.4.8 |
| OpenMP | N/A | N/A |

We are working on a fix to line up the OpenCV versions between the two.
