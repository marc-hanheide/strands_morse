strands_morse
=============

A MORSE-based simulation for the STRANDS project

Prerequisites
-------------

For running the simulation you would need:

* [MORSE](http://www.openrobots.org/morse/doc/latest/user/installation.html) 
* [Blender](http://www.blender.org/download/get-blender/)
* [ROS](http://www.ros.org/wiki/ROS/Installation)

Please refer to the respective installation guides to install them on your system. 

The current software has been tested under the following configuration:

* MORSE (latest)
* Blender 2.63a
* ROS Groovy
* Python 3.2.3 (3.3.0)
* Ubuntu 12.04 LTS

Getting Started
---------------

Start four terminals and run the commands below

1. Fire up roscore:
   
        $ roscore
       
2. Run the MORSE simulation:
      
        $ rosrun strands_morse <environment.launch>
   
   Please note: Using a depth camera requires Python 3.3 and a corresponding
   Blender version. For example:
   
        $ rosrun strands_morse bham_cs.launch
       
  For simulating a different level of the CS building run:

        $ rosrun strands_morse bham_cs.launch env:=cs_1 

  The lower ground floor is the default floor. Available environments are:
  cs_lg, cs_ug, cs_1, cs_2, cs (for the whole building)
       
3. (optional) Launch the 2D navigation:

        $ roslaunch strands_morse bham_cs_nav2d.launch

4. (optional) To visualize the the environment model in RVIZ run 

        $ roslaunch strands_morse bham_cs_rviz.launch
        
   and add a new display of type `RobotModel` in RVIZ. Set the topic to
   `/env/env_description` and TF prefix to `env`. (requires [strands_utils](https://github.com/strands-project/strands_utils))


-----------------

To start run the MORSE simulation of the TUM kitchen with a ScitosA5:
      
       $ rosrun strands_morse tum_kitchen.launch


