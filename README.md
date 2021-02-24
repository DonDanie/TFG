# TFG
Trabajo de fin de grado para Grado en Electrónica, Robótica y Mecatrónica de la Universidad de Sevilla realizado por Daniel Rosa Danta bajo la tutorización del profesor Manuel Vargas Villanueva
[@DonDanie](https://github.com/DonDanie)  

# Software necesario
Ubuntu 16.04
https://releases.ubuntu.com/16.04/

ROS Kinetic
http://wiki.ros.org/kinetic/Installation/Ubuntu

Instalamos e inicializamos ROS Kinetic desckop full, paquetes adicionales de ROS, catkin-tools y wstool:
```
$ sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu `lsb_release -sc` main" > /etc/apt/sources.list.d/ros-latest.list'
$ wget http://packages.ros.org/ros.key -O - | sudo apt-key add -
$ sudo apt-get update
$ sudo apt-get install ros-kinetic-desktop-full ros-kinetic-joy ros-kinetic-octomap-ros ros-kinetic-mavlink
$ sudo apt-get install python-wstool python-catkin-tools protobuf-compiler libgoogle-glog-dev ros-kinetic-control-toolbox
$ sudo rosdep init
$ rosdep update
$ echo "source /opt/ros/kinetic/setup.bash" >> ~/.bashrc
$ source ~/.bashrc
$ sudo apt-get install python-rosinstall python-rosinstall-generator build-essential
```
Creamos el espacio de trabajo:
```
$ mkdir -p ~/catkin_ws/src
$ cd ~/catkin_ws/src
$ catkin_init_workspace  # initialize your catkin workspace
$ cd ~/catkin_ws/
$ catkin init
$ cd ~/catkin_ws/src
$ git clone -b med18 https://github.com/gsilano/rotors_simulator.git
$ git clone -b med18 https://github.com/gsilano/mav_comm.git
$ git clone https://github.com/gsilano/BebopS.git
$ git clone https://github.com/AutonomyLab/bebop_autonomy.git
```

