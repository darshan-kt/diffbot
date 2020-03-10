### 2WD Robot Description

The description of the 2WD robot will be created in its own package. The description uses URDF and xacro. 
The `2wd_robot_description` package can be with [`catkin create pkg PKG_NAME [--catkin-deps [DEP [DEP ...]]]`](https://catkin-tools.readthedocs.io/en/latest/verbs/catkin_create.html#catkin-create-pkg):

```bash
fjp@ubuntu:~/git/2wd-robot/ros/src$ catkin create pkg robot_description --catkin-deps roscpp tf geometry_msgs urdf rviz xacro
Creating package "robot_description" in "/home/fjp/git/2wd-robot/ros/src"...
Created file robot_description/package.xml
Created file robot_description/CMakeLists.txt
Created folder robot_description/include/robot_description
Created folder robot_description/src
Successfully created package files in /home/fjp/git/2wd-robot/ros/src/robot_description.
```

The package depends on the ROS [client library](http://wiki.ros.org/Client%20Libraries) [`roscpp`](http://wiki.ros.org/roscpp).

According to ROS conventions we create the following folders where the individual files realted to the robot description will be placed:

```bash
fjp@ubuntu:~/git/2wd-robot/ros/src/robot_description$ mkdir urdf meshes launch
``` 

The `urdf` folder will be used to keep the `urdf` and `xacro` files. 
The `meshes` folder keeps the `meshes` that are included in the `urdf` file, and the `launch` folder keeps the ROS launch files.


### Tools

To check a urdf file we can make use of the tool `check_urdf` in the `liburdfdom-tools` debian package. 
Install it with the following command:

```bash
sudo apt install liburdfdom-tools
```

Then it is possible to check urdf files for errors:

```bash
fjp@ubuntu:~/git/2wd-robot/ros/src/robot_description/urdf$ check_urdf robot.urdf
```