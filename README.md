# Mapping-in-ROS
This file is going to walk you through few steps that will help you create a 2D Map in ROS using a 2D LiDAR and an odometry sensor.

You need to have the following packages in ROS: 

Hector Slam
Urg_node
Rosserial
gmapping
slam_gmapping

Documentation for using a Hokuyo LiDAR can be found here: https://github.com/biorobotics/RGBD_SLAM/tree/master/2D_lidar/hokuyo

Documentation for using Odometry sensor can be found here: https://github.com/Parva14/VOOF_Cam

In the file stfm.launch, You will have to add the static transorms between various frames of your robot as per your setup.

Step 1 : Connect your LiDAR and launch the file stfm.launch
          $roslaunch stfm.launch
          
Step 2 : Connect the odometry sensor and start publishing the transorm between base_link and odom on topic /tf

Step 3 : $rosrun gmapping slam_gmapping scan:=scan

Step 4 : Open rviz and add Map and tf

You will be now able to see a map being created as you move the robot.
