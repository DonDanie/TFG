# TFG
Trabajo de fin de grado para Grado en Electrónica, Robótica y Mecatrónica de la Universidad de Sevilla realizado por Daniel Rosa Danta [@DonDanie](https://github.com/DonDanie) bajo la tutorización del profesor Manuel Vargas Villanueva


# Software necesario
Ubuntu 16.04
https://releases.ubuntu.com/16.04/

ROS Kinetic
http://wiki.ros.org/kinetic/Installation/Ubuntu

Instalamos BebopS siguiendo los pasos para nuestra versión de ROS, Ubuntu y Gazebo. 

A continuación, explicaremos los pasos para ROS Kinetic, Ubuntu 16.04 y Gazebo 7:
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
  Creamos el espacio de trabajo y clonamos los repositorios necesarios:
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
A continuación, clonamos el repositorio de nuestro proyecto:
```
$ cd ~/catkin_ws
$ git clone http://github.com/DonDanie/TFG.git
```
Construimos nuestro espacio de trabajo con python_catkin_tools 
```
$ cd ~/catkin_ws
$ rosdep install --from-paths src -i
$ catkin build 
```
Por último, agregamos nuestra ubicación a nuestro archivo .bashrc
```
$ echo "source ~/catkin_ws/devel/setup.bash" >> ~/.bashrc
$ source ~/.bashrc
```
Ahora vamos a correr nuestro proyecto, para ello, primero tendremos que abrir una terminal nueva e iniciar roscore:
```
$ roscore
```
A continuación, en una nueva consola, ejecutaremos nuestro proyecto.
```
$ roslaunch bebop_simulator task1_world.launch
```
Abriremos ahora en otra consola el programa rqt:
```
$ rqt
```
Y en la pestaña "plugins/Visualization/Image" View elegimos ver, en nuestro caso, "/bebop/camera1/image/raw". Aquí podremos ver, a tiempo real, la imagen que muestra la cámara del dron en la simulación.
