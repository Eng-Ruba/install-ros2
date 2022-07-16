# install-ros2
#instal xubuntu 20.04
#Add the ROS 2 apt repository
$ sudo apt update && sudo apt install curl gnupg2 lsb-release curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -

Unpack it:
$ mkdir -p ~/ros2_crystal
cd ~/ros2_crystal
tar xf ~/Downloads/ros2-crystal-linux-x86_64.tar.bz2

#Installing and initializing rosdep
$sudo apt update

#Installing the missing dependencies
$=crystal # or bouncy
rosdep install --from-paths ros2-linux/share --ignore-src --rosdistro $CHOOSE_ROS_DISTRO -y --skip-keys "console_bridge fastcdr fastrtps libopensplice67 libopensplice69 osrf_testing_tools_cpp poco_vendor rmw_connext_cpp rosidl_typesupport_connext_c rosidl_typesupport_connext_cpp rti-connext-dds-5.3.1 tinyxml_vendor tinyxml2_vendor urdfdom urdfdom_headers"

#Sourcing the setup script
$. ~/ros2_crystal/ros2-linux/setup.bash

#In another terminal, start the bridge:
$. /opt/ros/melodic/setup.bash
. ~/ros2_crystal/ros2-linux/setup.bash
ros2 run ros1_bridge dynamic_bridge

#Uninstall
If you installed your workspace with colcon as instructed above, “uninstalling” could be just a matter of opening a new terminal and not sourcing the workspace’s setup file. This way, your environment will behave as though there is no Crystal install on your system.

If you’re also trying to free up space, you can delete the entire workspace directory with:

$rm -rf ~/ros2_crystal
