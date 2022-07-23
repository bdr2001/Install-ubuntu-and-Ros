# Install-ubuntu-and-Ros
task 1
Installation
Configure your Ubuntu repositories
Setup your sources.list
Setup your computer to accept software from packages.ros.org.
Set up your keys
sudo apt install curl # if you haven't already installed curl
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
Installation
First, make sure your Debian package index is up-to-date:

sudo apt update
Now pick how much of ROS you would like to install.

Desktop-Full Install: (Recommended) : Everything in Desktop plus 2D/3D simulators and 2D/3D perception packages

sudo apt install ros-noetic-desktop-full
or click here

Desktop Install: Everything in ROS-Base plus tools like rqt and rviz

sudo apt install ros-noetic-desktop
or click here

ROS-Base: (Bare Bones) ROS packaging, build, and communication libraries. No GUI tools.

sudo apt install ros-noetic-ros-base
or click here

There are even more packages available in ROS. You can always install a specific package directly.

sudo apt install ros-noetic-PACKAGE
e.g.
sudo apt install ros-noetic-slam-gmapping
To find available packages, see ROS Index or use:

apt search ros-noetic
Environment setup
You must source this script in every bash terminal you use ROS in.


source /opt/ros/noetic/setup.bash
It can be convenient to automatically source this script every time a new shell is launched. These commands will do that for you.

Bash


If you have more than one ROS distribution installed, ~/.bashrc must only source the setup.bash for the version you are currently using.


echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc
zsh

echo "source /opt/ros/noetic/setup.zsh" >> ~/.zshrc
source ~/.zshrc
Dependencies for building packages
Up to now you have installed what you need to run the core ROS packages. To create and manage your own ROS workspaces, there are various tools and requirements that are distributed separately. For example, rosinstall is a frequently used command-line tool that enables you to easily download many source trees for ROS packages with one command.

To install this tool and other dependencies for building ROS packages, run:


sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential
