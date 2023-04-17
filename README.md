# uia_husky_vx300
This repository can be used to set up an Interbotix vx300 manipulator with moveit configuration for collision avoidance with a Clearpath Husky UGV.

<p align="center">
<img src="husky_initiated.png" width=500 >
</p>

## Installation
Open terminal.

Clone this repo

~~~bash
git clone https://github.com/orjano-max/uia_husky_vx300
~~~

Go into cloned git folder

~~~bash
cd ORJANOS_MASTER_REPO
~~~

Update the submodules of this repo, there are alot of them
~~~bash
git submodule update --init --recursive
~~~

Run the following commands:

~~~bash
cd code/src/interbotix_ros_core/interbotix_ros_xseries/interbotix_xs_sdk
sudo cp 99-interbotix-udev.rules /etc/udev/rules.d/
sudo udevadm control --reload-rules && sudo udevadm trigger
~~~

Go back to the root folder of the git repository

~~~bash
cd ORJANOS_MASTER_REPO
~~~

Run rosdep

~~~bash
rosdep install --from-path code/src --ignore-src --rosdistro galactic -y
~~~

Install python-modern-robotics, somehow, this package is not a part of the interbotix rosdep

~~~bash
pip install modern-robotics
~~~

Build

~~~bash
colcon build
~~~
