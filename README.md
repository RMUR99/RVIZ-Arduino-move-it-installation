# RVIZ + GAZEBO  + Arduino + Rosserial Arduino + Ros_lib + Arduino upload installation 

* Running RVIZ + Controlling the motors in sumulation + Move it in RVIZ + GAZEBO launch 

How to start up RVIZ 

1)	Create the catkin work space and specify the type in our case it is melodic
sudo apt-get install ros-melodic-catkin

2)	Creating a directory called catkin in the source file 
mkdir -p ~/catkin_ws/src

3)	Name it as catkin work
cd ~/catkin_ws/

4)	Installing the arm package by using this command 
catkin_make

5)	Enter the source folder by this command 
cd ~/catkin_ws/src

6)	Enter the robotic arm package by using this command 
git clone https://github.com/smart-methods/arduino_robot_arm.git 

7)	Go to the catkin_ws folder 
cd ~/catkin_ws

8)	All the commands below are the commands needed from ROS
rosdep install --from-paths src --ignore-src -r -y

sudo apt-get install ros-melodic-moveit

sudo apt-get install ros-melodic-joint-state-publisher ros-kinetic-joint-state-publisher-gui

sudo apt-get install ros-melodicc-gazebo-ros-control joint-state-publisher

sudo apt-get install ros-melodic-ros-controllers ros-kinetic-ros-control

9)	Enter the bashrc file and enter the following text below
sudo nano ~/.bashrc

at the end of the (bashrc) file add the follwing line
(source /home/reemaalmurayshid/catkin_ws/devel/setup.bash)
then 
ctrl + o

10)	Update the sources of bashrc using this command 
source ~/.bashrc

11)	Launch the RVIZ using this command 
roslaunch robot_arm_pkg check_motors.launch


------------------------------------------------------------------------------------------------------------------------------------------
How to install Arduino IDE 

1)	Enter the website from the link 
https://www.arduino.cc/en/software

2)	Choose the download option that is suitable I have chosen LINUX 64 


3)	Extract the file downloaded  


4)	Open in terminal 


5)	Type the command ./install.sh in terminal 


6)	Check if the program is here 


7)	Open the program 


8)	A new folder called Arduino will appear after opening the program 


---------------------------------------------------------------------------------------------------------------------------------
How to  install Rosserial 

1)	Use these two commands below 

$ sudo apt-get install ros-melodic-rosserial-arduino
$ sudo apt-get install ros-melodic-rosserial


-----------------------------------------------------------------------------------------------------------------------------
Install Ros_lib 

To install you must type these commands : 
$cd <sketchbook>/libraries 
 $rm -rf ros_lib
rosrun rosserial_arduino make_libraries.py

-------------------------------------------------------------------------------------------------------------------------------

How to upload the Arduino code 
- select the Arduino port to be used on Ubuntu system 
- change the permissions (it might be ttyACM) 
$ ls -l /dev |grep ttyUSB 
$ sudo chmod -R 777 /dev/ttyUSB0 
- upload the code from Arduino IDE 
----------------------------------------------------------------------------------------------------------------------------- 
 
Run Rviz 
1) $ roslaunch robot_arm_pkg check_motors.launch 
2) $ rosrun rosserial_python serial_node.py _port:=/dev/ttyUSB0 _baud:=115200 
----------------------------------------------------------------------------------------------------------------------------- 
 
 
Controlling the motors in simulation 
1) $ roslaunch robot_arm_pkg check_motors.launch 
2) $ roslaunch robot_arm_pkg check_motors_gazebo.launch 
3) $ rosrun robot_arm_pkg joint_states_to_gazebo.py 
You may need to change the permission 
4) $ cd catkin/src/arduino_robot_arm/robot_arm_pkg/scripts 
7) $ sudo chmod +x joint_states_to_gazebo.py  
-------------------------------------------------------------------------------------------------------------------------- 
 
 
Moveit in rviz  
1) $ roslaunch moveit_pkg demo.launch $ 
 
--------------------------------------------------------------------------------------------------------------------------- 
 
Gazebo launch  
1) $roslaunch moveit_pkg demo_gazebo.launch $
