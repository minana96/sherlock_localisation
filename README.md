# *sherlock_localisation* ROS package

This repository represents the *sherlock_localisation* ROS pacakge that configures and launches localisation task via [amcl](http://wiki.ros.org/amcl) ROS package. The *sherlock_localisation* package is intended for ROS Melodic. The repository needs to be cloned to the catkin workspace on the robot (no need to clone it to the PC) and compiled with following commands:
```bash
cd <catkin_ws_dir>/src
git clone git@github.com:minana96/sherlock_localisation.git
cd ..
catkin_make
```

## Dependencies

The package is dependent on [amcl](http://wiki.ros.org/amcl) ROS package which can be installed with the following command:
```bash
sudo apt install ros-melodic-amcl
```

## Package content

The package consists of two directories, namely, *config* and *launch*.

### config

The direcotry contains parameter configuration for *amcl* ROS node in *yaml* format, which is passed as an argument when the node is launched:
- **amcl_params.yaml**: the configuration parameters for *amcl* ROS node. The definitions of parameters are available in *amcl* [ROS wiki page](http://wiki.ros.org/amcl);

### launch

The localisation task is configured and launched via two launch files:
- **sherlock_localisation.launch**: localisation is launched on the local machine, with the possibility of visualisation in [Rviz](http://wiki.ros.org/rviz) tool. If this option is used, both Rviz and *turtlebot3_navigation* ROS package need to be installed with following commands:
```bash
sudo apt install ros-melodic-rviz
sudo apt install ros-melodic-turtlebot3-navigation
```
- **sherlock_localisation_remote.launch**: localisation is launched on the remote machine that is passed as a parameter. If this launch file is used, it is important that the *amcl* ROS package is also installed on the target remote machine.
