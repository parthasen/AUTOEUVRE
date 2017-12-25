# Capstone project @SDCND 
Project introduction [here](https://classroom.udacity.com/nanodegrees/nd013/parts/6047fe34-d93c-4f50-8336-b70ef10cb4b2/modules/e1a23b06-329a-4684-a717-ad476f0d8dff/lessons/462c933d-9f24-42d3-8bdc-a08a5fc866e4/concepts/5ab4b122-83e6-436d-850f-9f4d26627fd9).

**This project was started by end of November, 2017, we formally teamed up on 4th December, 2017 and first submission was made on 26th Decmeber by distributed participation of five members**

**Team: AUTOEUVRE**
    
    Name                email@                              Role
    Attila Babo         attila.babo@gmail.com               Testing
    Isabella Johansson  isabellamariaellinor@gmail.com      DBW
    Partha Sen          research@parthasen.net              Traffic Light Detection
    Seunghun Lee        waydi1@gmail.com                    Waypoints
    Vinit Muchhala      vinitmuchhala@gmail.com             Traffic Light Classification
    
    
    
![ros-graph](https://github.com/parthasen/autoeuvre.com/blob/master/imgs/final-project-ros-graph-v2.png)

#### Important Intel
1. Robot Operating System (ROS) that will first steer a virtual car in the simulator, and later on the code will be run on an actual car 'Carla'. 
2. ROS can be installed in Ubuntu, VM or Docker file
3. Better to use NVIDIA GPU for the traffic light recognition.
4. ROS and simulator connection is bit  flaky.

#### Nodes
##### Waypoint Node
        T1: roscore
        T2: cd CarND-Capstone/ros
            student@udacity:~/CarND-Capstone/ros$ roslaunch launch/styx.launch
        T3: rostopic list,rostopic info /final_waypoints,
        ** use source devel/setup.bash

##### DBW Node

        T4: student@udacity:~/CarND-Capstone/ros/src/twist_controller$

##### TLD Node

#### ROS
        T5: rosbag play -l <path_to_your.bag>
        T6: @udacity:~$ rviz
File > Open Config in RViz from Desktop...       


#### Testing:

        T1: roscore
        T2: student@udacity:~/CarND-Capstone/ros$ roslaunch launch/styx.launch
        T3: student@udacity:~/CarND-Capstone/ros$ rosmsg info styx_msgs/Lane


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
