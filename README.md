# Map-My-World-Project
Using the RTAB-Map database to generate a 3D model of a ROS Gazebo environment
![RTab-Map Database Visualisation of Gazebo Simulation](/photos/third-rviz.jpeg)
![Gazebo Simulation of a Kitchen](/photos/kitchen-world.png)
![2D Occupancy Grid generated from robot](/photos/third-occ-grid.jpeg)

# Description

By manually driving the robot within the environment (using the keyboard), the robot is able to generate an RTab-Map database such as the one in the Image XXX. Furthermore through the RTab-Map database-Viewer the 2D graph and occupancy grid maps are generated in Image xxx and xxx. 
The last Image (xxx) contains a screenshot of how the features of the environment were captured to provide the map generation with the imperative loop closures. 
# Before you run the code

## Install ROS (skip this step if ROS is already installed)

(I am using Ubuntu 16.04 with the ROS Kinetic version below)

    sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list' && sudo apt-key adv --keyserver hkp://ha.pool.sks-keyservers.net:80 --recv-key 421C365BD9FF1F717815A3895523BAEEB01FA116 && sudo apt-get update && sudo apt-get install ros-kinetic-desktop-full && sudo rosdep init && rosdep update && echo "source /opt/ros/kinetic/setup.bash" >> ~/.bashrc && source ~/.bashrc

## Install Dependencies

    sudo apt-get install ros-kinetic-rtabmap ros-kinetic-rtabmap-ros && sudo apt-get remove ros-kinetic-rtabmap ros-kinetic-rtabmap-ros

## Install RTab-Map

    cd ~ && git clone https://github.com/introlab/rtabmap.git rtabmap && cd rtabmap/build && cmake .. && make && sudo make install

## Create .gazebo folder

    mkdir ~/.gazebo

## Add model collision adjustments

    curl -L https://s3-us-west-1.amazonaws.com/udacity-robotics/Term+2+Resources/P3+Resources/models.tar.gz | tar zx -C ~/.gazebo/

## Then download this repository

    git clone https://github.com/DannyRyanFisher/Map-My-World-Project

# How to run code

