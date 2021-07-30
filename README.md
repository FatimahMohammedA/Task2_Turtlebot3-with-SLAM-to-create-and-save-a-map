# Task2_Turtlebot3-with-SLAM-to-create-and-save-a-map
 How to launch a simulation of a Turtlebot3 inside a pre-made world.
and Launch mapping node with gmapping method on ros_onlin : 
 https://app.theconstructsim.com/#/

1- Open a new project 

On shell comand >>>

~$ ls        “ The list of the available workspaces”

“ We will save two of these repositories in the catkin workspace and one of them in the simulation workspace “

“ Go to access catkin workspace”

~$ cd catkin_ws/

“Go to access src folder on the catkin workspace “

~$ cd src/

“ Clone the repositories  https://github.com/ROBOTIS-GIT/turtlebot3.git and past it on the src folder “

~$ git clone  https://github.com/ROBOTIS-GIT/turtlebot3.git

“ Hit enter and you will see how it is cloning into the workspace “

“ We will do the same with messages repository https://github.com/ROBOTIS-GIT/turtlebot3_msgs.git “

~$ git clone  https://github.com/ROBOTIS-GIT/turtlebot3_msgs.git

“ Hit enter and you will see how it is cloning into the workspace “

“ Go back to the home “

~$ cd 

“ Go to Simulation workspace inside the src folder “

~$ cd simulation_ws/src/

“ Clone the repositories https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git “
 
~$ git clone https://github.com/ROBOTIS-GIT/turtlebot3_simulations.git

“ Hit enter and you will see how it is cloning into the workspace “

Start Map With Slam :

“ Go  from Simulation src folder to home”

~$ cd ..
~$ cd ..

“ Go to catkin workspace to launch the simulation and compile the code “

~$ cd catkin_ws/

~$ catkin_make

“ Go to simulation workspace  to launch the Simulation and compile the code “

~$ cd ..

~$ cd simulation_ws/

“ Specify what turtlebot3 model  we are using “

~$ export TURTLEBOT3_MODEL=burger

~$ roslaunch turtlebot3_gazebo turtlebot3_world.launch

“Open gazebo to see the simulation “

“ Launch the slam node arvis “

~$ export TURTLEBOT3_MODEL=burger

~$ roslaunch turtlebot3_slam turtlebot3_slam.launch slam_methods:=gmapping 

“ Open the graphical tools to see the arvis “

Move it with keyboard to complete the map “

~$ export TURTLEBOT3_MODEL=burger

~$ roslaunch turtlelbot3_teleop turtlelbot3_teleop_key.launch


“ Save the Map “

~$ rosrun map_server map_saver -f ~/map
