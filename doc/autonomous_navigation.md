## Move Autonomously While Extracting Map of the Environment with SLAM

# How to run?
* First start the simulation environment.
```
$ roslaunch kamu_robotu_gazebo kamu_map.launch
```
* Start SLAM process.
```
$ roslaunch kamu_robotu_launch oko_slam.launch
```
* Start move_base node which takes goals to navigate the robot
to a desired point
```
$ roslaunch kamu_robotu_navigation move_base.launch
```
* Run frontier_exploration which creates goals for move_base automatically to navigate autonomously
```
$ roslaunch kamu_robotu_navigation frontier.launch
```
* In Rviz window:
```
* Add Marker
* Choose marker topic: /exploration_polygon_marker
* Click publish point at the top of rviz window and 
select a point.
* Repeat above step to create a closed polygon.
* After your closed polygon becomes red color, click 
publish point button again to give an initial exploration point
to the robot.
```
After all these steps, robot will autonomously navigate and try to 
extract map of the overall environment inside the given polygon.
