# RVIZ-Installation-



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

sudo apt-get install ros-kinetic-moveit

sudo apt-get install ros-kinetic-joint-state-publisher ros-kinetic-joint-state-publisher-gui

sudo apt-get install ros-kinetic-gazebo-ros-control joint-state-publisher

sudo apt-get install ros-kinetic-ros-controllers ros-kinetic-ros-control

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

