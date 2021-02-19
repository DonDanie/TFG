# TFG
Trabajo de fin de grado para Grado en Electrónica, Robótica y Mecatrónica de la Universidad de Sevilla realizado por Daniel Rosa Danta bajo la tutorización del profesor Manuel Vargas Villanueva
[@DonDanie](https://github.com/DonDanie)  

# Software necesario
Ubuntu 16.04
https://releases.ubuntu.com/16.04/

ROS Kinetic
http://wiki.ros.org/kinetic/Installation/Ubuntu

Ros Kinetic Catkin
```
$ sudo apt-get install ros-kinetic-catkin
$ source /opt/ros/indigo/setup.bash
$ echo "source /opt/ros/indigo/setup.bash" >> ~/.bashrc
$ source ~/.bashrc
```
Pip
https://www.rosehosting.com/blog/how-to-install-pip-on-ubuntu-16-04/
sudo apt-get install python-pip

Catkin-tools
https://catkin-tools.readthedocs.io/en/latest/installing.html

Copiar repositorio:
```
$ sudo apt-get install build-essential python-rosdep python-catkin-tools
$ git clone --recurse-submodules https://github.com/MikeMakes/bebop.git  
$ pushd bebop/src/BebopS
$ git checkout -b dev/sphinx
$ popd
```
